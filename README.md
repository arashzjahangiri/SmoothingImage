# Smoothing Image
# OpenCV and C++
Smoothing, also called blurring, is a simple and frequently used image processing operation.
In this repo I apply 'Homogeneous' and 'Gaussian' filter on an image.

# OpenCV not installed on my MAC OS
<i><b>
1- Install Homebrew <br>
2- Install OpenCV </i></b>
```
brew install opencv
```
<i><b> 3- Install pkg-config.</i></b><br> pkg-config is a helper tool used when compiling applications and libraries. It helps you insert the correct compiler options on the command line rather than hard-coding values. This will be helpful for finding the correct linker flags for OpenCV. This will be more clear in the subsequent steps.
To install pkg-config using brew, open a terminal and paste:
```
brew install pkg-config
```
<i><b> 4- View OpenCV linker flags.</i></b><br>To view the linker flags for OpenCV, run:
```
pkg-config --cflags --libs path_to_opencv.pc (My is /usr/local/Cellar/opencv/4.1.2/lib/pkgconfig/opencv4.pc)
```
The output looks like:
```
-I/usr/local/Cellar/opencv/3.3.1_1/include/opencv -I/usr/local/Cellar/opencv/3.3.1_1/include -L/usr/local/Cellar/opencv/3.3.1_1/lib -lopencv_stitching -lopencv_superres -lopencv_videostab -lopencv_photo -lopencv_aruco -lopencv_bgsegm -lopencv_bioinspired -lopencv_ccalib -lopencv_dpm -lopencv_face -lopencv_fuzzy -lopencv_img_hash -lopencv_line_descriptor -lopencv_optflow -lopencv_reg -lopencv_rgbd -lopencv_saliency -lopencv_stereo -lopencv_structured_light -lopencv_phase_unwrapping -lopencv_surface_matching -lopencv_tracking -lopencv_datasets -lopencv_text -lopencv_dnn -lopencv_plot -lopencv_xfeatures2d -lopencv_shape -lopencv_video -lopencv_ml -lopencv_ximgproc -lopencv_calib3d -lopencv_features2d -lopencv_highgui -lopencv_videoio -lopencv_flann -lopencv_xobjdetect -lopencv_imgcodecs -lopencv_objdetect -lopencv_xphoto -lopencv_imgproc -lopencv_core
```
The above shows you the includes and the libraries for OpenCV.<br><br>
<i><b> 5- Compile the C++ code: </i></b>
```
g++ -ggdb $(pkg-config --cflags --libs path_to_opencv4.pc) -std=c++11 filters.cpp -o filters
```
<i><b> 6- Run the execution file to show filters. </i></b><br>
```
./filters
```
This will use default image `nature.jpg`, but you can give another image like this:
```
./filters path_to_your_image
```

# Future work:
1- Add more filters to cover all types of filters.<br>
2- Add better GUI to enable user to select image and desired filter as well.

<br><br>If you have any questions, don't hesitate to contact me via: arashzjahangiri@gmail.com
