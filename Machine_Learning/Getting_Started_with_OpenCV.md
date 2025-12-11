<h1> Getting Started with OpenCV </h1>
<h2> Basic OpenCV Features </h2>
Here are some important concepts and features of OpenCV that beginners should know:

<h3> Image Channels </h3>

- **Grayscale images** have 1 channel that represents the intensity level
   - <img src='./Machine_Vision/images/gray_scale.png' height=200>
   - the smaller the number is, the darker the pixel

- **Colour images** have 3 channels (Red, Green, Blue)
   - <img src='./Machine_Vision/images/rgb_wheel.png' width=450>

<h3> BGR vs RGB Colour Format </h3>

- OpenCV processes images in **BGR** format, not the typical **RGB** format used in other image processing libraries. The difference is in the order of the colour channels
- This means that when OpenCV reads an image, the pixel values will be ordered as BGR. If you need to convert from BGR to RGB, you can do so like this:
    ```
    # Convert BGR image to RGB
    rgb_image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
    ```
<h3> Working with Arrays </h3>

- OpenCV images are stored as **NumPy arrays**. This means you can use NumPy's powerful indexing and slicing features to manipulate image data directly:
    ```
    # Access the pixel at row 50, column 100
    pixel = image[50, 100]

    # Modify the pixel value (in BGR format)
    image[50, 100] = [255, 0, 0]  # Set to blue
    ```

<h2> OpenCV Basic Implementations </h2>

### [Read and Display an Image](./Machine_Vision/cv_examples/read_show_image.py)
 - Using the [```cv2.imread()```](https://www.geeksforgeeks.org/python-opencv-cv2-imread-method/) and [```cv2.imshow()```](https://www.geeksforgeeks.org/python-opencv-cv2-imshow-method/) method.
 - Your first place to start! Now you can display an image from a file with OpenCV!

### [Convert Image to Grayscale](./Machine_Vision/cv_examples/convert_to_grayscale.py)
 - Using the [```cv2.cvtColor()```](https://www.geeksforgeeks.org/python-opencv-cv2-cvtcolor-method/) method to convert a BGR coloured image to grayscale.
 - Since grayscale images have only one colour channel, their file size is much smaller than coloured images. This is a great option when you want to optimize the computation efficiency of an image/video where you don't need the colour information. 

### [Resize Image](./Machine_Vision/cv_examples/resize_image.py)
 - Using the [```cv2.resize()```](https://www.geeksforgeeks.org/image-resizing-using-opencv-python/) method.

### [Capture Video from Webcam](./Machine_Vision/cv_examples/capture_from_webcam.py)
 - Use the [```cv2.VideoCapture()```](https://www.geeksforgeeks.org/python-opencv-capture-video-from-camera/) method with parameter 0 to open the built-in webcam of your laptop
 - Call the ```read()``` method on the VideoCapture object in a loop to process it frame by frame

### [Read Video from File](./Machine_Vision/cv_examples/read_video_from_file.py)
 - Same as the above, but replace the parameter in the ```VideoCapture()``` method with the path to the file.

### [Edge Detection](./Machine_Vision/cv_examples/detect_edge.py)
 - Edge detection highlights boundaries within an image where there is a sharp change in brightness. This is used in various applications such as object recognition, image segmentation, motion detection, etc.
 - This code demonstrates the most popular edge detection algorithm, the Canny algorithm with the [```cv2.Canny()```](https://docs.opencv.org/4.x/da/d22/tutorial_py_canny.html) method. 

**For more tutorials, check out the [official OpenCV-Python Tutorials page](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html).**
