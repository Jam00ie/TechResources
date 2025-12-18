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
### 4. [Machine Learning](#4)
   - 4.1 [Running the Model](#4.1)
     - 4.1.1 [Data Collection](#4.1.1)
     - 4.1.2 [Data Cleaning and Preprocessing](#4.1.2)
     - 4.1.3 [Model Selection](#4.1.3)
     - 4.1.4 [Model Training](#4.1.4)
     - 4.1.5 [Model Evaluation and Tuning](#4.1.5)
     - 4.1.6 [Model Deployment](#4.1.6)

<h2 id = '1'> 1. Introduction</h2>

This guide will walk you through a machine learning (ML) model that you can train to identify exercises in combination with Google's Mediapipe and OpenCV. This ML model is an LSTM (long short-term memory) model, which can make predictions from sequences of data. 

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


<h2 id = '4'> 4. Machine Learning</h2>
Machine Learning (ML) is a branch of Artificial Intelligence (AI) that enables systems to learn patterns from data and make predictions or decisions without being explicitly programmed.

Once an ML model is trained, it must be integrated into an application so its predictions can be accessed and used in real-world scenarios.

The following sections outline the general ML workflow involved in developing and deploying this type of model.

<h3 id = '4.1'> 4.1 Runing the Model</h3>
Machine learning development typically follows a structured workflow consisting of several key stages. The steps below describe the stages relevant to this project.

<h4 id = '4.1.1'> Data Collection</h4>
Data collection involves gathering raw data that represents the classes or categories you want the model to recognize.
- You define your own categories
- When selecting your own data, ensure the following:
  - Videos are in .mp4 format
  - Each video contains at least two clear repetitions of the action
  - Data includes recordings from multiple angles to improve model robustness

<h4 id = '4.1.2'>Data Cleaning and Preprocessing</h4>
This step prepares raw data for training by improving consistency and usability.
- Data cleaning includes handling missing values, removing corrupted frames, and correcting inconsistencies.
- Data preprocessing involves:
  - Standardizing formats
  - Scaling numerical values
  - Encoding categorical labels

<h4 id = '4.1.3'>Model Selection</h4>
Model selection involves choosing an appropriate algorithm based on the type of data, the structure of the problem, and the desired output. Different models are suited to different tasks, and understanding their strengths and limitations helps guide this decision.

<h5>Traditional Machine Learning Models</h5>
These models typically rely on handcrafted features extracted from the data.

- Logistic Regression / Linear Models:
Useful for simple classification problems with well-separated features. They are easy to interpret but may struggle with complex, non-linear patterns.

- Support Vector Machines (SVMs):
Effective for high-dimensional data and smaller datasets. SVMs can handle non-linear decision boundaries using kernel functions but may become computationally expensive with large datasets.

- Decision Trees and Random Forests:
These models are good at capturing non-linear relationships and interactions between features. Random forests improve robustness by combining multiple trees but may require feature engineering for sequential data

There are more models to choose from and information about this can be found at this [website made by IBM](https://www.ibm.com/think/topics/model-selection)

<h4 id = '4.1.4'>Model Training</h4>
During training, the model learns patterns from labeled data. Within this process, the following will occur:

- Build the model architecture
- Train the model on processed sequences
- Adjust training parameters as needed

<h4 id = '4.1.5'>Model Evaluation and Tuning</h4>
Model evaluation measures how well the trained model performs on unseen data.

- Predictions are made on a test dataset
- Performance metrics such as accuracy and loss are analyzed
- Refer to Section 9 of the notebook for evaluation steps
- Hyperparameters may be adjusted to improve performance

<h4 id = '4.1.6'>Model Deployment</h4>
Once trained and evaluated, the model can be deployed in several ways:

<h5>Offline Deployment</h5>

- Suitable for running predictions on pre-recorded videos
- Save the trained model as a .h5 file
- Create a script or function to load the model and run inference
- Ensure preprocessing and sequence formatting match the training setup

<h5>Web or Desktop Applications</h5>

- Useful for interactive or user-facing applications
- The model can be integrated into:
   - Streamlit applications
   - Flask or FastAPI backends
- These frameworks allow real-time predictions through a graphical interface or API

There are many additional deployment approaches depending on project requirements so feel free to explore creative implementations
