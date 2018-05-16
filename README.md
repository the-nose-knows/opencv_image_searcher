# opencv_image_searcher
OpenCV's matchTemplate code example with minor modifications and build-project-file handling to get started quickly; only requires Visual Studio and OpenCV to build with, and a base image sample as your first command line argument, and the image pattern as your second command line argument. By default, they're named `image_base.png` and `image_pattern.png`

In addition to having Visual Studio and OpenCV installed, you will need to set the environment variable, `OPENCV_DIR`, for example, mine is set to `C:\OpenCV_3.4.1\build`

## Extras needed Visual Studio 2015 

If you're not using Visual C++ 2017, you will also need to edit the post-build event commands to copy the dependencies from the correct location. For example, this line uses VC++2017 paths: 

`<Command>xcopy image_*.png bin\$(Platform)\$(Configuration) /y&amp;xcopy $(OPENCV_DIR)\x64\vc15\bin\*.dll bin\$(Platform)\$(Configuration) /y</Command>` 

If you're using VC++2015, you would change that line to: 

`<Command>xcopy image_*.png bin\$(Platform)\$(Configuration) /y&amp;xcopy $(OPENCV_DIR)\x64\vc14\bin\*.dll bin\$(Platform)\$(Configuration) /y</Command>` 

where `vc14` was the change from `vc15`.

You'll also likely have to change this line: `<PlatformToolset>v141</PlatformToolset>`  
To this line: `<PlatformToolset>v140</PlatformToolset>`

Basically, anywhere you see it set to `141` it will need to be changed to `140`  
