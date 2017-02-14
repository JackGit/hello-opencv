This is the demo QT project with OPENCV

### environment

window 10 (64bit), QT 5.8.0 minGW (32bit), opencv 2.4.13

### build opencv with cmake for minGW

1. download [opencv 2.4.13](https://sourceforge.net/projects/opencvlibrary/files/opencv-win/2.4.13/opencv-2.4.13.exe/download), you will have opencv-2.4.13.exe

2. install opencv-2.4.13, my install directory is `d:\opencv`

3. download [cmake-gui](https://cmake.org/files/v3.7/cmake-3.7.2-win64-x64.msi) for win64 and install it

4. make sure you have `D:\Qt\Qt5.8.0\Tools\mingw530_32\bin` in your windows environment path, this is required when you make file for mingw in cmake

5. open cmake-gui, select `D:/opencv/sources` as source code, create a directory, which I created `D:/opencv/mingw-build`, as build directory

6. click CMake Configure button

7. then click CMake Generate button

8. open terminal under `D:/opencv/mingw-build`, execute `mingw32-make`, this takes about half an hour in my machine

9. then execute `mingw32-make install`, this would take seconds

10. done

### Qt .pro files

```
INCLUDEPATH += D:\opencv\mingw-build\install\include
LIBS += -L"D:\opencv\mingw-build\install\x86\mingw\bin"
LIBS += -lopencv_core2413 -lopencv_highgui2413 -lopencv_imgproc2413 -lopencv_features2d2413 -lopencv_objdetect2413
```

`2413` is the version of my opencv. Actually you can find these libs in `D:\opencv\mingw-build\lib`

### other

write demo opencv code as in `main.cpp`, and you are ready to go.

![screenshot](http://ofkyhrvda.bkt.clouddn.com/post/image/1487044716%281.png)

### references

https://zahidhasan.wordpress.com/2014/08/19/qt-5-3-1-64-bit-mingw-windows/
