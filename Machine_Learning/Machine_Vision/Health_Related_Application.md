<h1> MediaPipe -- Pose Detection Demonstrations </h1>

 - Mediapipe provides libraries for a great variety of tasks that you can choose from depending on the goal of your project. You can find a web-based demo of these library utilities on the [MediaPipe Studio site](https://mediapipe-studio.webapps.google.com/demo/pose_landmarker).

    - Use your webcam as the input and tweak the parameter values to have some fun with it!

 - This guide will only go over the basics of the **Pose Detection** library, as it may be the most relevant to your problem space.

 <h2> 1: Library Features </h2>

 - The Mediapipe Pose Detection library tracks the location of 33 body landmarks.
    - <img src='https://ai.google.dev/static/mediapipe/images/solutions/pose_landmarks_index.png' height=500px>

 - Each landmark contains the x, y, and z coordinates, as well as the visibility of the landmark
    ```bash
        # print an example landmark

        x: 0.401668698
        y: 0.664962471
        z: -0.16625689
        visibility: 0.998352528
    ```
    - ```x``` and ```y``` are normalized coordinates representing the 2D position of the landmark in the image 
        - Ranging from 0 to 1, relative to the image dimensions.
    - ```z``` is a **relative** depth coordinate representing the distance of the landmark from the camera.
        - You are likely not working with a depth camera here, so the ```z``` value is not a real "measured" value. It is rather estimated by the Mediapipe model. 
    - ```visibility``` is a confidence score indicating how likely it is that the landmark is visible or correctly detected. 
        - Ranges from 0.0 to 1.0. 
            - 1.0 == high confidence
            - 0.0 == low confidence
    - Let's say the program can only view the upper body of a person to detect their pose, like this:

        <img src='images/upper_body_pose.png' height=200px>\
    The pose detection method will still, by default, return the ```x y z``` coordinates of the lower body landmarks.
        - The visible upper body landmarks will have very **high** ```visibility``` values
        - The knee joints and ankle joint will have extremely **low** ```visibility``` values.
        - The hip joints will each have a **median** ```visibility```value because the model can estimate the hip joint coordinates with higher confidence based on the visible upper body landmarks.

 <h2> 2: Library Basic Implementations </h2>

### [Pose Detection on an Image](mp_examples/draw_landmarks_on_image.py)
 - Visit this code snippet for the simplest implementation that detects and draws the landmarks on an image. 
 - Think about how you would:
    1. Get the ```x y z``` coordinates and the ```visibility``` value of a specific landmark.
    2. Change the colour and thickness of the landmark labels and the connection lines.
    3. Calculate the angle at the left elbow joint.

### [Pose Detection on LiveStream](mp_examples/draw_landmarks_on_live_stream.py)
 - Now that you know how to process one image, processing a video or livestream is easy since a video is just numerous frames of an image. 
 - Check out this code on how that is done, then you are ready to start your own journey of using CV and Mediapipe to complete your own project!
