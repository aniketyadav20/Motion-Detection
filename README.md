
[![LinkedIn][linkedin-shield]][linkedin-url]

# Motion Detection

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project
      </a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
Videos can be treated as stack of pictures called frames. Here I am comparing different frames(pictures) to the first frame which should be static(No movements initially). We compare two images by comparing the intensity value of each pixels. In python we can do it easily as you can see in code.

<p align="center">
<img src="https://pyimagesearch.com/wp-content/uploads/2015/05/animated_motion_02.gif"
 alt="Logo" width="500" height="400">
</p>


### Built With

We use opencv to accomplish this task.
you must know about these terms also:
* [Grayscaling](https://www.geeksforgeeks.org/python-grayscaling-of-images-using-opencv/) : it is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white. Importance of Grayscaling is 
-> Dimension reduction: For e.g. In RGB images there are three color channels and has three dimensions while grayscaled images are single dimensional.
-> Reduces model complexity: Consider training neural article on RGB images of 10x10x3 pixel.The input layer will have 300 input nodes. On the other hand, the same neural network will need only 100 input node for grayscaled images.
-> For other algorithms to work: There are many algorithms that are customized to work only on grayscaled images e.g. Canny edge detection function pre-implemented in OpenCV library works on Grayscaled images only.

<p align="center">
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRcxlaavHWVYhlLbtAgz9shUIgYbG1vkvKurA&usqp=CAUhttps://i.redd.it/vl8nmx8drhh31.jpg"
 alt="Logo" width="400" height="200">
</p>

* [GaussianBlur](https://docs.opencv.org/master/d4/d13/tutorial_py_filtering.html): In this method, instead of a box filter, a Gaussian kernel is used. It is done with the function, cv.GaussianBlur(). We should specify the width and height of the kernel which should be positive and odd. We also should specify the standard deviation in the X and Y directions, sigmaX and sigmaY respectively. If only sigmaX is specified, sigmaY is taken as the same as sigmaX. If both are given as zeros, they are calculated from the kernel size. Gaussian blurring is highly effective in removing Gaussian noise from an image.


<p align="center">
<img src="https://docs.opencv.org/master/gaussian.jpg"
 alt="Logo" width="400" height="250">
</p>

* [Image Thresholding](https://docs.opencv.org/master/d7/d4d/tutorial_py_thresholding.html): For every pixel, the same threshold value is applied. If the pixel value is smaller than the threshold, it is set to 0, otherwise it is set to a maximum value. The function cv.threshold is used to apply the thresholding. The first argument is the source image, which should be a grayscale image. The second argument is the threshold value which is used to classify the pixel values. The third argument is the maximum value which is assigned to pixel values exceeding the threshold. OpenCV provides different types of thresholding which is given by the fourth parameter of the function. Basic thresholding as described above is done by using the type cv.THRESH_BINARY. All simple thresholding types are: cv.THRESH_BINARY, 
cv.THRESH_BINARY_INV, 
cv.THRESH_TRUNC, 
cv.THRESH_TOZERO, 
cv.THRESH_TOZERO_INV

* [Dilate](https://appdividend.com/2020/09/22/python-cv2-dilate-dilation-of-images-using-opencv/): Dilation and Erosion are two primary image operations in the area of Mathematical Morphology.  Dilation is applied to binary images. The main effect of the dilation on a binary image is to continuously increase the boundaries of regions of foreground pixels (for example, white pixels, typically). Thus areas of foreground pixels expand in size while holes within those regions become smaller.To apply a morphological filter to images in Python using OpenCV, use the cv2 dilate() method. The dilate() method takes two inputs in which one is our input image; the second is called the structuring element or kernel, which decides the nature of the operation. Image dilation Increases the object area.
* [Contours](https://docs.opencv.org/master/d4/d73/tutorial_py_contours_begin.html): Contours can be explained simply as a curve joining all the continuous points (along the boundary), having same color or intensity. The contours are a useful tool for shape analysis and object detection and recognition.


<!-- GETTING STARTED -->
## Getting Started

### Prerequisites
* Any python Compiler (except google colab)

### Installation

1. Install packages
   ```sh
   pip install opencv-python
   ```



<!-- USAGE EXAMPLES -->
## Usage
A motion sensor (or motion detector) is an electronic device that is designed to detect and measure movement. Motion sensors are used primarily in home and business security systems, but they can also be found in phones, paper towel dispensers, game consoles, and virtual reality systems.



<!-- ROADMAP -->
## Roadmap

1. In this AI world, opencv library is must to learn about AI. 
2. The main goal of this repository is to detect the motion. We only require opencv library for this.
3. First a fall, we import opencv library.
4. Start the camera and use live camera using videocapture(0), if you want to perforn on any video then simply change 0 to the address of video in videocapture.
5. Now we capture 2 frames at a time, frame1 and frame2.
6. We use the while loop to perform this task on full video.
7. now first of all we find the difference between both the frames, frame1 and frame2.
8. Then, convert it to the gray scale.
9. To Smoothen the image we use the Gaussian blur.
10. Now to get the only required part we miplement thresholding.
11. Now, we perform dilation to our image.
12. To draw the boundary we using contours that detect the boundary. Then we get the four points and draw rectangle if the contour area is less than 700.
13. Show the final result using the final frame.
14. Frame is changing continuously so when we show output frame, it is like a video.

Here you go! This was a simple way to detect faces, eyes, and happiness.
<p align="center">
<img src="https://media4.giphy.com/media/xT5LMpZ7qbNJNFRvck/giphy.gif"
 alt="Logo" width="350" height="300">
</p>

## Contact

Aniket Yadav - [Medium](https://aniketyadavv.medium.com/) - [Gmail](https://yadavaniket0820gmail.com/)
<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/aniket-yadav-2008/
