# opencv_image_searcher  

OpenCV's matchTemplate() code example with some very minor modifications, and build-project-file handling to get started quickly for Visual Studio projects; only requires Visual Studio and OpenCV to build with, and a base image sample as your first command line argument, and the image pattern as your second command line argument. 

## Quick-Start  
1. If Visual Studio 2017 or 2015 isn't installed, you probably don't need this repo, as it is meant for Visual Studio projects. If you don't know how to build projects and also don't have Visual Studio, head on over to their website to grab a free copy if appropriate  
2. If OpenCV isn't installed, install it  
3. If the environment variable of `OPENCV_DIR` isn't set, set that. For example, mine is set to `C:\OpenCV_3.4.1\build`  
4. Grab a base image you want to have scanned and name it `image_base.png` and place it at the base directory for this repo  
5. Set the pattern image you want to have located and name it `image_pattern.png` and place it at the base directory for this repo  
6. Build, launch a console and change directories to your build output folder, and run `opencv_matchtemplate.exe image_base.png image_pattern.png`  

## Extras needed for Visual Studio 2015  
 
None of these changes affect `Source.cpp`  

If you're not using Visual C++ 2017, you will also need to edit the post-build event commands to copy the dependencies from the correct location within your `opencv_matchtemplate.vcxproj` file. For example, this line uses VC++2017 paths: 

`<Command>xcopy image_*.png bin\$(Platform)\$(Configuration) /y&amp;xcopy $(OPENCV_DIR)\x64\vc15\bin\*.dll bin\$(Platform)\$(Configuration) /y</Command>` 

If you're using VC++2015, you would change that line to: 

`<Command>xcopy image_*.png bin\$(Platform)\$(Configuration) /y&amp;xcopy $(OPENCV_DIR)\x64\vc14\bin\*.dll bin\$(Platform)\$(Configuration) /y</Command>` 

where `vc14` was the change from `vc15`.

You'll also likely have to change this line: `<PlatformToolset>v141</PlatformToolset>`  
To this line: `<PlatformToolset>v140</PlatformToolset>`

Basically, anywhere you see it set to `141` it will need to be changed to `140`  
