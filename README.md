
![Logo](https://upload.wikimedia.org/wikipedia/commons/8/82/Sign_Language_Interpretation_2.JPG)

# Sign-Language-Alphabet-Recognizer-Prototype
Sign Language Alphabet recognizer prototype app for Android.



The project consists in three components organized in the respective folders.

- Datasets for the models
- Models used 
- Android app prototype







## Datasets

There are two datasets. First one is a mix of American Sign Language (ASL) datasets, second one is a little Spanish Sign Language (LSE) dataset made by me.

The Datasets can be accessed via Kaggle:

- ASL Dataset (https://www.kaggle.com/datasets/kirlelea/asl-dataset-mix-static)
- LSE Dataset (https://www.kaggle.com/datasets/kirlelea/spanish-sign-language-alphabet-static)



## Models

The models can be found in `trained_models` folder in `.h5` and `.tflite` format.
The first model was made applying fine-tunning on top of VGG-19 network. Second one was made using MediaPipe Hands Solution,
extracting the relative coordinates of the landmarks captured by this pipeline and using that coordinates to train the model. 
To train again the second model you need to pass to the `mediapipe_dataset_generator.py` the dataset with images and use the generated csv file to feed the model described in `mediapipe_model` file.


## Android app

The mobile application was developed using Java over Android Studio, TensorFlow Lite and OpenCV.

The application uses the first model (ASL Model) imported in the `ml`folder. 
The `core` folder contains the `Classificator.java` file that manages the preprocessing and classification of the images and the `SharedPrefManager.java` file for preferences management.
On the other side, the `ui` folder contains the main logic of the app on the `MainActivity.java` file that allows the user to load images from gallery, capture photos or access to the options menu. Moreover, the `recordActivity.java` manages the interaction with the devices cameras using the Camera2 API and captures a video rendering it over a layout to take snapshots and classify them. 

At last, you will need to give some permissions to the app, collected in the manifest file.


## Installation

To use the android app, clone the repository and open the `android` folder inside `Aplicación móvil` with Android Studio.

To execute the models, you will need to following external libraries with the recommended versions:
 - Tensorflow (2.9 or higher) `pip3 install --upgrade tensorflow`
 - Keras (2.9 or higher) `pip3 install keras`
 - Sklearn (1.0.2 or higher) `pip3 install -U scikit--learn`
 - Matplotlib (3.5.1 or higher) `sudo apt-get install python3-matplotlib`
 - Numpy (1.22.3 or higher) `pip3 install numpy`
 - OpenCV2 (4.5 or higher) `pip3 install opencv-python`

If you want to modify the mediapipe model, you will also need mediapipe (`pip3 install mediapipe`) and python-csv (`pip3 install python-csv`)
    
## Authors
- [@kirle](https://github.com/kirle)
- [@fribadas](https://github.com/fribadas)

