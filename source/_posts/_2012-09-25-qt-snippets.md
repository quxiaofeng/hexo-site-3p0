---
layout: post
tags: [c++, gui, qt]
title: Qt Snippets
description: Useful qt snippets in the gui and image processing.
category: coding
date: 2012-09-25 19:36:38
comments: true
mathjax: false
---

Useful qt snippets in the gui and image processing.

<!--more-->

## Pro File

### Configure the Lib

+ MATLAB

    MATLABDIR = "C:/Program Files/MATLAB/R2012a"

    exists($$MATLABDIR) {
        DEFINES += USEMATLAB
        INCLUDEPATH += $${MATLABDIR}/extern/include $${MATLABDIR}/extern/include/win32
        LIBS += -L$${MATLABDIR}/extern/lib/win32/microsoft -llibmx -lmclmcr -lmclmcrrt
        message("MATLAB libraries found in $${MATLABDIR}")
    } else {
        message("MATLAB libraries not found.")
    }

+ OpenCV (OpenCV 2.4.0 32bit dll for win32)

    win32 {
        OPENCVDIR = "C:/code/opencvrt"
        exists($$OPENCVDIR) {
            DEFINES += USEOPENCV
            INCLUDEPATH += \
                $${OPENCVDIR}/include
            DEPENDPATH += \
                $${OPENCVDIR}/include
            CONFIG(release, debug|release) {
                LIBS += -L$${OPENCVDIR}/lib \
                    -lopencv_calib3d240 \
                    -lopencv_contrib240 \
                    -lopencv_core240 \
                    -lopencv_features2d240 \
                    -lopencv_flann240 \
                    -lopencv_gpu240 \
                    -lopencv_highgui240 \
                    -lopencv_imgproc240 \
                    -lopencv_legacy240 \
                    -lopencv_ml240 \
                    -lopencv_nonfree240 \
                    -lopencv_objdetect240 \
                    -lopencv_photo240 \
                    -lopencv_stitching240 \
                    -lopencv_ts240 \
                    -lopencv_video240 \
                    -lopencv_videostab240
            }
            CONFIG(debug, debug|release) {
                LIBS += -L$${OPENCVDIR}/lib \
                    -lopencv_calib3d240d \
                    -lopencv_contrib240d \
                    -lopencv_core240d \
                    -lopencv_features2d240d \
                    -lopencv_flann240d \
                    -lopencv_gpu240d \
                    -lopencv_highgui240d \
                    -lopencv_imgproc240d \
                    -lopencv_legacy240d \
                    -lopencv_ml240d \
                    -lopencv_nonfree240d \
                    -lopencv_objdetect240d \
                    -lopencv_photo240d \
                    -lopencv_stitching240d \
                    -lopencv_ts240d \
                    -lopencv_video240d \
                    -lopencv_videostab240d
            }
            message("OpenCV libraries found in $${OPENCVDIR}")
        } else {
            message("OpenCV libraries not found.")
        }
    }


