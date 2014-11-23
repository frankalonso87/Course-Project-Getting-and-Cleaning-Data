CODE BOOK

This code book  describes the data, the variables, and any transformations or work that  performed in order to clean up the data.

DATA INFORMATION

Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers were selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

The variables that were estimated from these signals are:

- mean(): Mean value
- std(): Standard deviation
- mad(): Median absolute deviation
- max(): Largest value in array
- min(): Smallest value in array
- sma(): Signal magnitude area
- energy(): Energy measure. Sum of the squares divided by the number of values.
- iqr(): Interquartile range
- entropy(): Signal entropy
- arCoeff(): Autoregression coefficients with Burg order equal to 4
- correlation(): Correlation coefficient between two signals
maxInds(): Index of the frequency component with largest magnitude
- meanFreq(): Weighted average of the frequency components to obtain a mean frequency
- skewness(): Skewness of the frequency domain signal
- kurtosis(): Kurtosis of the frequency domain signal
- bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
- angle(): Angle between some vectors.

All variables  were normalized and bounded within [-1,1].

The UCI HAR DATASET

The UCI HAR Dataset includes:

- README.txt

- features_info.txt: Information about the variables used on the feature vector.

- features.txt: List of all features.

- activity_labels.txt: Links the class labels with their activity name.

- train/X_train.txt: Training set.

- train/y_train.txt: Training labels.

- test/X_test.txt: Test set.

- test/y_test.txt: Test labels.

The following files are available for both the train and test data.Thus descriptions are equivalent.

- train/subject_train.txt: Each row refers to the subject who performed the activity for each window sample. Its range is from 1 to 30.

- train/Inertial Signals/total_acc_x_train.txt: The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis.

- train/Inertial Signals/body_acc_x_train.txt: Body acceleration signal obtained by subtracting the gravity from the total acceleration.

- train/Inertial Signals/body_gyro_x_train.txt: Angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.

HOW TO TRANSFORM THE RAW DATASET INTO A TIDY DATASET
(explained also in the README.md file):

a) clone the following repository: git clone https://github.com/frankalonso87/Course-Project-Getting-and-Cleaning-Data.git

b) download compressed raw data using the link provided at the beginning of this file.

c) unzip raw data and copy the resulting directory UCI HAR Dataset to the  repository you just cloned.

d) open a R console and set the working directory (setwd())to be the directory containing the repo you cloned.
e) source the run_analisys.R script (pay attention as you will be required to load the plyr package) source('run_analysis.R')

f) Finally you will find  the file tidydata.txt which contains the tidy data asked in this Project.

WHAT ARE WE REALLY DOING WHEN CREATING THE TIDY DATASET


a) We begin by merging Test and training data (X_train.txt, X_test.txt), subject ids (subject_train.txt, subject_test.txt) and activity ids (y_train.txt, y_test.txt) in order  to obtain a single data set. Variables are labelled with the names assigned originally  (features.txt).

b) From the merged data resulting in a) we obtain another dataset wich contains  only the values of estimated mean (variables with labels that contain "mean") and standard deviation (variables with labels that contain "std").

c) We add a new column to dataset resulting in b) with the activity description. Activity id column is used to look up descriptions in activity_labels.txt.

d) Original Labels were changed (without parentheses, dashes and commas) to obtain more descriptive labels.

e) We finally build up a tidy dataset from the dataset we are working with.In this final dataset  numeric variables are averaged for each activity and each subject.

The final tidy data set contains the observations with 81 variables divided into:

 - an activity label (Activity): WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING
 
- an identifier of the subject who carried out the experiment.

 -a 79-feature vector with time and frequency domain signal variables (numeric)

The data set is written to the file tidydata.txt.