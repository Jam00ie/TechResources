# Machine Vision: Integrating Machine Learning with OpenCV and MediaPipe
## Table of Contents
### 1. [Introduction](#1)
### 2. [Installation](#2)
   - 2.1. [Download Python](#2.1)
   - 2.2. [Creating Virtual Environments](#2.2)
   - 2.3. [Install Python Libraries](#2.3)
   - 2.4. [Jupyter Notebook](#2.4)
### 3. [Computer Vision Basics](#3)
   - 3.1. [Basic OpenCV Features](#3.1)
   - 3.2. [OpenCV Basic Implementations](#3.2)

<h2 id = '1'> 1. Introduction</h2>

This guide will walk you through a machine learning (ML) model that you can train to identify exercises in combination with Google's Mediapipe and OpenCV. This ML model is an LSTM (long short-term memory) model, which can make predictions from sequences of data.
If you've never worked with machine learning before, check out this [Getting_Started_with_Machine_Learning.md](Machine_Learning/Getting_Started_with_Machine_Learning.md) guide. It will introduce you to machine learning (ML) and explain the workflow that guides development and deployment of ML models.

<h2 id = '2'> 2. Installation</h2>

<h3 id = '2.1'> 2.1 Download Python (version 3.9 - 3.11)</h3>

* Currently, Mediapipe is only supported on python versions 3.9 to 3.12.
* You can download a compatible version of python [here](https://www.python.org/downloads/).

<h3 id = '2.2'> 2.2 Creating Virtual Environments</h3>
A Python virtual environment (.venv) is a self-contained directory that allows you to install packages and dependencies for a specific project without affecting the global Python installation or other projects.

1. Download the starter code contained in this folder (it is recommended you use git to download and share these files)
2. Open a terminal in vscode and use `cd *directory*` to navigate to the directory where you stored the code you downloaded in step 1
3. Create a venv:
   - Enter `python -m venv *name-of-your-venv*` in the same terminal. This should create a new folder with the name of your venv under the "Computer Vision" directory
5. Activate the venv:
   - You might get a prompt in VSCode after creating the venv, asking if you want to use the new venv for your project. If you select yes, you don't need to do the following.
   - for Mac/Linux users: `source ./name-of-your-venv/bin/activate`
   - for Windows users: `name-of-your-venv/Scripts/activate`
   - When prompted, type R and then enter to run once
   - you should now see `(name-of-your-venv)` being appended to your input prompt, indicating that you have activated your venv

<h3 id = '2.3'> 2.3 Install Python Libraries</h3>

- **OpenCV**: For handling image and video processing.
- **MediaPipe Solutions**: For real-time computer vision tasks.
- **Numpy**: For matrix and array operations.
- **Tensorflow**: For building and training machine learning models (specifically deep learning).

You can use the `requirements.txt` file in this folder and run this one-line command in the terminal: `pip install -r requirements.txt`

<h3 id = '2.4'> 2.4 Jupyter Notebook</h3>

Jupyter Notebook is used for machine learning because it provides an interactive environment where you can write and run code in small chunks, visualize data and document your process all in one location.
- Follow this guide for using [Jupyter Notebook](https://code.visualstudio.com/docs/datascience/jupyter-notebooks) in VSCode

<h2 id = '3'> 3. Computer Vision Basics</h2>
<h3 id='3.1'> 3.1 Basic OpenCV Features</h3>
Here are some important concepts and features of OpenCV that beginners should know:

**Image Channels**
- **Grayscale images** have 1 channel that represents the intensity level
   - <img src='./Machine_Vision/images/gray_scale.png' height=200>
   - the smaller the number is, the darker the pixel

- **Colour images** have 3 channels (Red, Green, Blue)
   - <img src='./Machine_Vision/images/rgb_wheel.png' width=450>

**BGR vs RGB Colour Format**
- OpenCV processes images in **BGR** format, not the typical **RGB** format used in other image processing libraries. The difference is in the order of the colour channels
- This means that when OpenCV reads an image, the pixel values will be ordered as BGR. If you need to convert from BGR to RGB, you can do so like this:
    ```
    # Convert BGR image to RGB
    rgb_image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
    ```
**Working with Arrays**
- OpenCV images are stored as **NumPy arrays**. This means you can use NumPy's powerful indexing and slicing features to manipulate image data directly:
    ```
    # Access the pixel at row 50, column 100
    pixel = image[50, 100]

    # Modify the pixel value (in BGR format)
    image[50, 100] = [255, 0, 0]  # Set to blue
    ```

<h3 id='3.2'> 3.2 OpenCV Basic Implementations</h3>

**[Reading and Displaying an Image](./Machine_Vision/cv_examples/read_show_image.py)**

 - Using the [```cv2.imread()```](https://www.geeksforgeeks.org/python-opencv-cv2-imread-method/) and [```cv2.imshow()```](https://www.geeksforgeeks.org/python-opencv-cv2-imshow-method/) method.
 - Your first place to start! Now you can display an image from a file with OpenCV!

**[Converting Image to Grayscale](./Machine_Vision/cv_examples/convert_to_grayscale.py)**
 - Using the [```cv2.cvtColor()```](https://www.geeksforgeeks.org/python-opencv-cv2-cvtcolor-method/) method to convert a BGR coloured image to grayscale.
 - Since grayscale images have only one colour channel, their file size is much smaller than coloured images. This is a great option when you want to optimize the computation efficiency of an image/video where you don't need the colour information. 

**[Resize Image](./Machine_Vision/cv_examples/resize_image.py)**
 - Using the [```cv2.resize()```](https://www.geeksforgeeks.org/image-resizing-using-opencv-python/) method.

**[Capture Video from Webcam](./Machine_Vision/cv_examples/capture_from_webcam.py)**
 - Use the [```cv2.VideoCapture()```](https://www.geeksforgeeks.org/python-opencv-capture-video-from-camera/) method with parameter 0 to open the built-in webcam of your laptop
 - Call the ```read()``` method on the VideoCapture object in a loop to process it frame by frame

 **[Read Video from File](./Machine_Vision/cv_examples/read_video_from_file.py)**
 - Same as the above, but replace the parameter in the ```VideoCapture()``` method with the path to the file.

**[Edge Detection](./Machine_Vision/cv_examples/detect_edge.py)**
 - Edge detection highlights boundaries within an image where there is a sharp change in brightness. This is used in various applications such as object recognition, image segmentation, motion detection, etc.
 - This code demonstrates the most popular edge detection algorithm, the Canny algorithm with the [```cv2.Canny()```](https://docs.opencv.org/4.x/da/d22/tutorial_py_canny.html) method. 

**For more tutorials, check out the [official OpenCV-Python Tutorials page](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html).**
