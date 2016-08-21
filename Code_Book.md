# CodeBook


### Data
### Variables
### Transformation


## The data

* Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
* Original description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

Check the README.txt file for further details about this dataset. 

A video of the experiment including an example of the 6 recorded activities with one of the participants can be seen in the following link: https://www.youtube.com/watch?v=XOEN9W05_4A

An updated version of this dataset can be found at http://archive.ics.uci.edu/ml/datasets/Smartphone-Based+Recognition+of+Human+Activities+and+Postural+Transitions. It includes labels of postural transitions between activities and also the full raw inertial signals instead of the ones pre-processed into windows.

For each record in the dataset it is provided: 
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. 
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

## Variables

The dataset includes the following files:

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

### Inside Test and Train files are:

subject                    1..2
Subject number
 1..30 .Unique identifier assigned to each subject

label                      6..18
Acitivity label
 "WALKING"
 "WALKING_UPSTAIRS"
 "WALKING_DOWNSTAIRS"
 "SITTING"
 "STANDING"
 "LAYING"

tbodyaccmeanx              12

tbodyaccmeany              12

tbodyaccmeanz              12

tbodyaccstdx               12

tbodyaccstdy               12

tbodyaccstdz               12

tgravityaccmeanx           12

tgravityaccmeany           12

tgravityaccmeanz           12

tgravityaccstdx            12

tgravityaccstdy            12

tgravityaccstdz            12

tbodyaccjerkmeanx          12

tbodyaccjerkmeany          12

tbodyaccjerkmeanz          12

tbodyaccjerkstdx           12

tbodyaccjerkstdy           12

tbodyaccjerkstdz           12

tbodygyromeanx             12

tbodygyromeany             12

tbodygyromeanz             12

tbodygyrostdx              12

tbodygyrostdy              12

tbodygyrostdz              12

tbodygyrojerkmeanx         12

tbodygyrojerkmeany         12

tbodygyrojerkmeanz         12

tbodygyrojerkstdx          12

tbodygyrojerkstdy          12

tbodygyrojerkstdz          12

tbodyaccmagmean            12

tbodyaccmagstd             12

tgravityaccmagmean         12

tgravityaccmagstd          12

tbodyaccjerkmagmean        12

tbodyaccjerkmagstd         12

tbodygyromagmean           12

tbodygyromagstd            12

tbodygyrojerkmagmean       12

tbodygyrojerkmagstd        12

fbodyaccmeanx              12

fbodyaccmeany              12

fbodyaccmeanz              12

fbodyaccstdx               12

fbodyaccstdy               12

fbodyaccstdz               12

fbodyaccjerkmeanx          12

fbodyaccjerkmeany          12

fbodyaccjerkmeanz          12

fbodyaccjerkstdx           12

fbodyaccjerkstdy           12

fbodyaccjerkstdz           12

fbodygyromeanx             12

fbodygyromeany             12

fbodygyromeanz             12

fbodygyrostdx              12

fbodygyrostdy              12

fbodygyrostdz              12

fbodyaccmagmean            12

fbodyaccmagstd             12

fbodybodyaccjerkmagmean    12

fbodybodyaccjerkmagstd     12

fbodybodygyromagmean       12

fbodybodygyromagstd        12

fbodybodygyrojerkmagmean   12

fbodybodygyrojerkmagstd    12


### The following files are available for the train and test data. Please follow the descriptions.

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30.

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis.

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.


## Transformation 

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names.
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

### In further detail the transformation:

* Require ```reshapre2``` and ```data.table``` librareis.
* Load both test and train data
* Load the features and activity labels.
* Extract the mean and standard deviation column names and data.
* Process the data. There are two parts processing test and train data respectively.
* Merge data set.
* Write table into tidy data text file.
