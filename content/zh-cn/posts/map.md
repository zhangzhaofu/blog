+++ 
date = "2022-02-17"
title = "20220217"
slug = "20220217" 
tags = ["20220217", "day"]
categories = ["blog"]
+++

## 2022-07-17

在按键有改变的时候发送modbus消息
```
func readSerial() {
	conf := &serial.Config{Name: "COM4", Baud: 115200}
	s, err := serial.OpenPort(conf)
	if err != nil {
		log.Fatal(err)
	}

	buf := make([]byte, 1024)
	msg := make([]byte, 32)
	var arr [32]byte
	c := make(chan [32]byte)

	go handleKeyMsg(c)

	for {
		n, err := s.Read(buf)
		if err != nil {
			log.Println(err)
		}
		for i := 0; i < n; i++ {
			if n > 1 && buf[i] == 0xAA && buf[i+1] == 0x55 {
				if len(msg) == 32 {
					//fmt.Printf("%X\n", msg)
					copy(arr[:], msg[:])
					c <- arr
				}
				msg = msg[:0]
			}
			msg = append(msg, buf[i])
		}
		time.Sleep(time.Duration(50) * time.Millisecond)
	}
}

func handleKeyMsg(c chan [32]byte) {
	handler := modbus.NewRTUClientHandler("COM1")
	handler.BaudRate = 115200
	handler.DataBits = 8
	handler.Parity = "N"
	handler.StopBits = 1
	handler.SlaveId = 1
	handler.Timeout = 50 * time.Millisecond
	err := handler.Connect()
	if err != nil {
		log.Println(err)
	}
	defer handler.Close()
	client := modbus.NewClient(handler)

	keys := make(map[string]uint16)

	for {
		msg := <-c
		fmt.Printf("%X\n", msg)
		leftJoystickY := int16(msg[9])<<8 | int16(msg[8])
		//fmt.Printf("%d\n", leftJoystickY)
		leftJoystickX := int16(msg[11])<<8 | int16(msg[10])
		//fmt.Printf("%d\n", leftJoystickX)
		//rightJoystickY := int16(msg[13]) << 8 | int16(msg[12])
		//fmt.Printf("%d\n", rightJoystickY)
		//rightJoystickX := int16(msg[15]) << 8 | int16(msg[14])
		//fmt.Printf("%d\n", rightJoystickX)

		var direction uint16 = 0
		if leftJoystickY > -300 && leftJoystickY < 300 {
			if leftJoystickX < -300 {
				direction = 3
			} else if leftJoystickX > 300 {
				direction = 4
			} else {
				direction = 0
			}

		} else if leftJoystickY >= 300 {
			direction = 1
		} else {
			direction = 2
		}
		fmt.Println(direction)

		oldDir, ok := keys["direction"]
		if ok && oldDir != direction {
			_, err = client.WriteSingleRegister(40000+0x800, direction)
			if err != nil {
				log.Println(err)
			}
		}
		keys["direction"] = direction

	}

}

```
