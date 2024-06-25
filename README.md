# DEEPFAKE_DETECTION_MODEL
deepfake detection model using machine learning 
# 1. INTRODUCTION
The increasing computational power has significantly enhanced deep learning algorithms, making it easy to create realistic human-synthesized videos, commonly known as deepfakes. To counteract this, we are leveraging Artificial Intelligence to combat the misuse of Artificial Intelligence. Our approach employs a ResNext Convolutional Neural Network to extract frame-level features, which are then used to train a Long Short Term Memory (LSTM)-based Recurrent Neural Network. This network classifies whether a video has been manipulated or is authentic, distinguishing deepfakes from real videos.

To ensure our model performs effectively in real-time scenarios, we evaluate it using a substantial, balanced, and diverse dataset. This dataset is created by combining various available datasets such as FaceForensics++, the Deepfake Detection Challenge, and Celeb-DF. Our results demonstrate that our straightforward yet robust method can achieve competitive performance in detecting deepfakes.
# 2.  SYSTEM ARCHITECTURE

![System Architecture (1)](https://github.com/Abbishek01/deep_fake-detection_model-/assets/93364595/1213ab6c-8d2b-401a-b095-969045ace63e)
# 3. DATASET
To enhance the model's efficiency for real-time prediction, we have compiled data from various sources, including FaceForensics++, the Deepfake Detection Challenge (DFDC), and Celeb-DF. By combining these datasets, we created a new, diverse dataset designed for accurate and real-time detection of various video types. To prevent training bias, our dataset consists of an equal distribution of 50% real and 50% fake videos.

The DFDC dataset includes some videos with altered audio, which are outside the scope of this project. Therefore, we preprocessed the DFDC dataset to exclude audio-altered videos using a Python script.

After preprocessing, we selected 1,500 real and 1,500 fake videos from the DFDC dataset, 1,000 real and 1,000 fake videos from the FaceForensics++ (FF) dataset, and 500 real and 500 fake videos from the Celeb-DF dataset. This process resulted in a balanced dataset comprising 3,000 real and 3,000 fake videos, totaling 6,000 videos.
![Screenshot (8)](https://github.com/Abbishek01/deep_fake-detection_model-/assets/93364595/4f3e5754-341c-43c1-9d34-4f435b6744fd)

# 4.DATA PROCESSING 

In this step, we preprocess videos to remove unnecessary elements and noise, focusing only on the face. 
First, we split each video into frames. We then detect and crop the face in each frame, ignoring frames without faces. The cropped frames are recombined into new, face-only videos.To maintain uniformity and manage computational limits, we selected a threshold of 150 frames based on the average frame count per video. Processing more than 150 frames per video is computationally challenging, so we save only the first 150 frames for each new video. Frames are considered sequentially, not randomly, to effectively use Long Short-Term Memory (LSTM) networks. The final processed videos are saved at 30 fps with a resolution of 112 x 112.


# 5. DATA SPLIT
The dataset is divided into training and testing sets with a 70:30 ratio, resulting in 4,200 training videos and 1,800 testing videos. Both the training and testing sets are balanced, each containing 50% real and 50% fake videos.

# 6. HYPERPARAMETER TUNING 
To enable the adaptive learning rate Adam[21] optimizer with the model parameters is used. The learning rate is tuned to 1e-5 (0.00001) to achieve a better global minimum of gradient descent. The weight decay used is 1e-3.As this is a classification problem so to calculate the loss cross-entropy approach is used.

# 7. RESULT 


![image](https://github.com/Abbishek01/deep_fake-detection_model-/assets/93364595/a05cf93e-1d49-4790-8d1a-0207b76c50f3)


The above image represents the results achieved on our dataset by the model. The accuracy in the image depicts the test accuracy.

As we can observe in our results that the accuracy of the model is increasing with the increasing number of sequence lengths.

Based on our results we can say that, our model is able to predict whether the video is a deepfake or real by seeing just 10 frames i.e. less than 1 second (considering 30 frames per second video) with a decent accuracy of 84%.

I hope you have liked your research on Deepfake detection using LSTM. We have a prototype project here hosted on Github. Soon I will be back with a step by step installation of the project.

