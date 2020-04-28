# Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM

# Link: http://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones

# Abstract: 
Human Activity Recognition database built from the recordings of 30 subjects performing activities of daily living (ADL) while carrying a waist-mounted smartphone with embedded inertial sensors.

# Data Set Information:

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

# Attribute Information:

For each record in the dataset it is provided:
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope.
- A 561-feature vector with time and frequency domain variables.
- Its activity label.
- An identifier of the subject who carried out the experiment.

# Number of Data points per Subject.
![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/Data_points_per_Subject.png)


# Number of Data points per Activity.
![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/Points_per_activity.png)
# TSNE Plot:

Here, Features: 561 are converted into 2 (Dimensionality Reduction).

![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/TSNE.png)

# Model Build:
**Model Peformance:**
*   Logistic Regression: Train_F1_score = 0.99, Test_F1_score = 0.96
*   SVC                : Train_F1_score = 0.98, Test_F1_score = 0.95
*   SVC_Grid           : Train_F1_score = 0.99, Test_F1_score = 0.96

All the Machine Learning models have nearby scores on Train and Test

![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/Test_Train_Learning_Curve.png)

# MLP_Sigmoid:
**Accuracy of 0.87 on Train and 0.85 on Test**
* Features  : 561
* Rows      : 7352
* Classes   : 6
* Layers    : 2- Hidden Layes([512,256], Dropout = 0.5,Activation = sigmoid), Kernel Regulizer = l2 and Batch Normalized
* Output    : Activation = Softmax
* Epochs    : 20
* Batch Size: 128
![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/MLP_Sigmoid.png)
# LSTM_Softmax(Output):
**Accuracy of 0.95 on Train and 0.92 on Test**
**Accuracy of 0.87 on Train and 0.85 on Test**
* Features/Input  : 9
* Rows            : 7352
* Classes         : 6
* Layers          : 2-  Hidden Layes([64,32,16], Dropout = abs(np.random.normal(0,1)), Activation = sigmoid) and Batch Normalized,
* Output          : Activation = Softmax
* Epochs          : 30
Batch Size      : 128
![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/LSTM_Softmax.png)
# LSTM_Sigmoid(Output):
Here, I have divided the activities into two: 
*     Dynamic: Walking, Walking_Upstairs, Walking_Downstairs, Marked class = 1.
*     Static : Sitting, Sleeping, Standing, Marked class = 0.
Ultimately, I have converted 6 class classification to 2 class classification and Model has performed pretty well.
**Accuracy of 0. on Train and 0.85 on Test**
* Features/Input  : 9
* Rows            : 7352
* Classes         : 2
* Layers          : 2-  Hidden Layes([64,32,16], Dropout = abs(np.random.normal(0,1)), Activation = sigmoid) and Batch Normalized,
* Output          : Activation = Sigmoid
* Epochs          : 10
* Batch Size      : 128
![](https://github.com/VinayPrasad1394/Human-Activity-Recognition---Machine-Learnind-MLP-and-LSTM/blob/master/Images/LSTM_2_Class.png)

**Model Performance**
* Logistic Regression : Train_F1_score = 0.99, Test_F1_score = 0.96
* SVC                 : Train_F1_score = 0.98, Test_F1_score = 0.95
* SVC_Grid            : Train_F1_score = 0.99, Test_F1_score = 0.96
* MLP_Sigmoid         : Train_Accuracy = 0.87, Test_Accuracy = 0.85
* LSTM_SoftMax        : Train_Accuracy = 0.95, Test_Accuracy = 0.92 (6 Class)
* LSTM_Sigmoid        : Train_Accuracy = 0.98, Test_Accuracy = 0.99 (2 Class)


*Thanks UCI Machine Learning Repository for collecting the data,we were able to build a model and predict the outcome based on the data.*
