# Getting Started with Machine Learning
### Machine Learning
   - 1 [Running the Model](#1)
     - 1.1 [Data Collection](#1.1)
     - 1.2 [Data Cleaning and Preprocessing](#1.2)
     - 1.3 [Model Selection](#1.3)
     - 1.4 [Model Training](#1.4)
     - 1.5 [Model Evaluation and Tuning](#1.5)
     - 1.6 [Model Deployment](#1.6)
    
<h2 id = '1'> Machine Learning</h2>
Machine Learning (ML) is a branch of Artificial Intelligence (AI) that enables systems to learn patterns from data and make predictions or decisions without being explicitly programmed.

Once an ML model is trained, it must be integrated into an application so its predictions can be accessed and used in real-world scenarios.

The following sections outline the general ML workflow involved in developing and deploying this type of model.

<h3 id = '1'> 1 Runing the Model</h3>
Machine learning development typically follows a structured workflow consisting of several key stages. The steps below describe the stages relevant to this project.

<h4 id = '1.1'> Data Collection</h4>
Data collection involves gathering raw data that represents the classes or categories you want the model to recognize.
- You define your own categories
- When selecting your own data, ensure the following:
  - Videos are in .mp4 format
  - Each video contains at least two clear repetitions of the action
  - Data includes recordings from multiple angles to improve model robustness

<h4 id = '1.2'>Data Cleaning and Preprocessing</h4>
This step prepares raw data for training by improving consistency and usability.
- Data cleaning includes handling missing values, removing corrupted frames, and correcting inconsistencies.
- Data preprocessing involves:
  - Standardizing formats
  - Scaling numerical values
  - Encoding categorical labels

<h4 id = '1.3'>Model Selection</h4>
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

<h4 id = '1.4'>Model Training</h4>
During training, the model learns patterns from labeled data. Within this process, the following will occur:

- Build the model architecture
- Train the model on processed sequences
- Adjust training parameters as needed

<h4 id = '1.5'>Model Evaluation and Tuning</h4>
Model evaluation measures how well the trained model performs on unseen data.

- Predictions are made on a test dataset
- Performance metrics such as accuracy and loss are analyzed
- Refer to Section 9 of the notebook for evaluation steps
- Hyperparameters may be adjusted to improve performance

<h4 id = '1.6'>Model Deployment</h4>
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
