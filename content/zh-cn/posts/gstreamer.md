+++ 
date = "2022-09-05"
title = "GStreamer"
slug = "gstreamer" 
tags = ["gstreamer", "video"]
categories = ["blog"]
+++

# GStreamer
```
# If it's found it sets LIBGSTREAMER_FOUND to TRUE
# and following variables are set:
#  LIBGSTREAMER_INCLUDE_DIRS
#  LIBGSTREAMER_LIBRARIES

# FIND_PATH and FIND_LIBRARY normally search standard locations
# before the specified paths. To search non-standard paths first,
# FIND_* is invoked first with specified paths and NO_DEFAULT_PATH
# and then again with no specified paths to search the default
# locations. When an earlier FIND_* succeeds, subsequent FIND_*s
# searching for the same item do nothing.

# Include dir
SET(LIBGSTREAMER_INCLUDE_DIRS)
IF(MINGW OR MSVC)
    list(APPEND LIBGSTREAMER_INCLUDE_DIRS
        c:/gstreamer/1.0/mingw_x86_64/include
        c:/gstreamer/1.0/mingw_x86_64/include/gstreamer-1.0
        c:/gstreamer/1.0/mingw_x86_64/include/glib-2.0
        c:/gstreamer/1.0/mingw_x86_64/lib/gstreamer-1.0/include
        c:/gstreamer/1.0/mingw_x86_64/lib/glib-2.0/include
    )
ELSEIF(${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    find_path(LIBGSTREAMER_INCLUDE_DIRS version.h
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Headers
        NO_DEFAULT_PATH
    )
ELSE()
    include(FindPkgConfig)
    pkg_check_modules(LIBGSTREAMER REQUIRED gstreamer-1.0 gstreamer-video-1.0 gstreamer-gl-1.0 gstreamer-base-1.0 gobject-2.0 glib-2.0)
endif ()


# Library
IF(MINGW OR MSVC OR ${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    SET(LIBGSTREAMER_LIBRARIES)
    find_library(LIBGSTREAMER_1.0_LIBRARY NAMES gstreamer-1.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGSTREAMER_1.0_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGSTREAMER_1.0_LIBRARY}
        )
    ENDIF()

    find_library(LIBGSTREAMER_VIDEO_LIBRARY NAMES gstvideo-1.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGSTREAMER_VIDEO_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGSTREAMER_VIDEO_LIBRARY}
        )
    ENDIF()

    find_library(LIBGSTREAMER_GL_LIBRARY NAMES gstgl-1.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGSTREAMER_GL_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGSTREAMER_GL_LIBRARY}
        )
    ENDIF()

    find_library(LIBGSTREAMER_BASE_LIBRARY NAMES gstbase-1.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGSTREAMER_BASE_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGSTREAMER_BASE_LIBRARY}
        )
    ENDIF()

    find_library(LIBGOBJECT_LIBRARY NAMES gobject-2.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGOBJECT_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGOBJECT_LIBRARY}
        )
    ENDIF()

    find_library(LIBGLIB_LIBRARY NAMES glib-2.0 PATHS
        c:/gstreamer/1.0/mingw_x86_64/lib
        /Library/Frameworks/GStreamer.framework/Versions/1.0/Libraries
        NO_DEFAULT_PATH
    )
    IF(LIBGLIB_LIBRARY)
        list(APPEND LIBGSTREAMER_LIBRARIES
            ${LIBGLIB_LIBRARY}
        )
    ENDIF()
ENDIF()


IF(LIBGSTREAMER_LIBRARIES)
    SET(LIBGSTREAMER_FOUND TRUE)
ENDIF()


IF(LIBGSTREAMER_FOUND)
    IF(NOT LIBGSTREAMER_FOUND_QUIETLY)
        MESSAGE(STATUS "Found gstreamer include-dir path: ${LIBGSTREAMER_INCLUDE_DIRS}")
        MESSAGE(STATUS "Found gstreamer libs: ${LIBGSTREAMER_LIBRARIES}")
    ENDIF(NOT LIBGSTREAMER_FOUND_QUIETLY)
ELSE()
    IF(LIBGSTREAMER_FIND_REQUIRED)
        MESSAGE(FATAL_ERROR "Could not find gstreamer")
    ENDIF()
ENDIF()
```
