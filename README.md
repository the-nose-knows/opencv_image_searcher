# opencv_image_searcher
OpenCV's matchTemplate code example with minor modifications and build-project-file handling to get started quickly; only requires Visual Studio and OpenCV to build with, and a base image sample as your first command line argument, and the image pattern as your second command line argument. By default, they're named `image_base.png` and `image_pattern.png`

In addition to having Visual Studio and OpenCV installed, you will need to set the environment variable, `OPENCV_DIR`, for example, mine is set to `C:\OpenCV_3.4.1\build`

If you're not using Visual C++ 2017, you will also need to edit the post-build event commands to copy the dependencies from the correct location. For example, this line uses VC++2017 paths: 

`<Command>xcopy image_*.png bin\$(Platform)\$(Configuration) /y&amp;xcopy $(OPENCV_DIR)\x64\vc15\bin\*.dll bin\$(Platform)\$(Configuration) /y</Command>` 
