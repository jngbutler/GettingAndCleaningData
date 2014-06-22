Codebook for J.Butler's Tidy Data Set
========================================================
(Coursera "Getting and Cleaning Data", June 2014)
--------------------------------------------------------

### The Human Activity Recognition Using Smartphones Dataset (UCI HAR Dataset)
The UCI HAR Dataset was developed by researchers at the Smartlab - Non Linear Complex Systems Laboratory in Genoa, Italy [1].  It consists of recorded measurements from a Samsung Galaxy S II smartphone worn on the waist by 30 volunteers aged 19-48 years as they performed the 6 activities of laying, sitting, standing, walking, walking down, and walking up.  

Using an embedded accelerometer and gyroscope that captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz, the smartphone device acts as an inertial sensor that measures a person's movements in terms of the body'slinear acceleration (a change in inertia in at least one plane of movement, along with a gravitational component that determines orientation with respect to earth's gravity) and angular velocity (rotation).  These recordings allow body motion to be analyzed in 3 dimensions - vertically (up/down), medio-laterally (side-to-side), and anterio-posteriorly (forwards/backwards). [2]

As described on UCI Machine Learning Repository website [3], "the sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain."

The UCI HAR Dataset was partitioned into two sets with 70% of the subjects in the training data and 30% in the test data. 

### Coursera Data Files
The following data files, available through the Coursera "Getting and Cleaning Data" course, were downloaded from 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip on June 21, 2014.

* The "subject_train.txt" and "subject_test.txt" files contained the training subject ID's and the test subject ID's respectively.
* The "X_train.txt"" and "X_test.txt" files contained the study data in the form of 7352 observations (training subjects) and 2947 observations (test subjects) on 561 variables V1 through V561 (which were the data derived from the sensor signals).
* The "y_train.txt"" and "y_test.txt" files contained the activity code (what each subject was doing at the data collection timepoint)
* The "activity_labels.txt" and "features.txt" provided the description labels for the 6 activity codes and the 561 variable codes respectively.

Additional files "README.txt" and "features_info.txt" provided information the research and about the selected variables in the UCI HAR Dataset.
  
### J.Butler's Tidy Data Set

#### Methodology
The course project [4] required that students
   
1. Merge the training and the test sets to create one data set
2. Extract only the measurements on the mean and standard deviation for each measurement  
3. Uses descriptive activity names to name the activities in the data set  
4. Appropriately label the data set with descriptive variable names  
5. Create a tidy data set with the average of each variable for each activity and each subject  

#### Final Tidy Data Set
The final "tidy data" set consists of 180 rows (6 activities x 30 subjects) and 81 columns.  For each subjectid and activitylabel (LAYING, SITTING, STANDING, WALKING, WALKING_DOWNSTAIRS, WALKING_UPSTAIRS), there are 79 variables containing the averages of the measurements.

subjectid                     
activitylabel                 
AvgOf_tBodyAccMean_X          
AvgOf_tBodyAccMean_Y          
AvgOf_tBodyAccMean_Z          
AvgOf_tBodyAccSTD_X           
AvgOf_tBodyAccSTD_Y           
AvgOf_tBodyAccSTD_Z           
AvgOf_tGravityAccMean_X       
AvgOf_tGravityAccMean_Y       
AvgOf_tGravityAccMean_Z       
AvgOf_tGravityAccSTD_X        
AvgOf_tGravityAccSTD_Y        
AvgOf_tGravityAccSTD_Z        
AvgOf_tBodyAccJerkMean_X      
AvgOf_tBodyAccJerkMean_Y      
AvgOf_tBodyAccJerkMean_Z      
AvgOf_tBodyAccJerkSTD_X       
AvgOf_tBodyAccJerkSTD_Y       
AvgOf_tBodyAccJerkSTD_Z       
AvgOf_tBodyGyroMean_X         
AvgOf_tBodyGyroMean_Y        
AvgOf_tBodyGyroMean_Z         
AvgOf_tBodyGyroSTD_X          
AvgOf_tBodyGyroSTD_Y         
AvgOf_tBodyGyroSTD_Z          
AvgOf_tBodyGyroJerkMean_X     
AvgOf_tBodyGyroJerkMean_Y    
AvgOf_tBodyGyroJerkMean_Z     
AvgOf_tBodyGyroJerkSTD_X      
AvgOf_tBodyGyroJerkSTD_Y      
AvgOf_tBodyGyroJerkSTD_Z     
AvgOf_tBodyAccMagMean         
AvgOf_tBodyAccMagSTD         
AvgOf_tGravityAccMagMean      
AvgOf_tGravityAccMagSTD       
AvgOf_tBodyAccJerkMagMean     
AvgOf_tBodyAccJerkMagSTD      
AvgOf_tBodyGyroMagMean        
AvgOf_tBodyGyroMagSTD        
AvgOf_tBodyGyroJerkMagMean    
AvgOf_tBodyGyroJerkMagSTD     
AvgOf_fBodyAccMean_X          
AvgOf_fBodyAccMean_Y         
AvgOf_fBodyAccMean_Z          
AvgOf_fBodyAccSTD_X           
AvgOf_fBodyAccSTD_Y           
AvgOf_fBodyAccSTD_Z           
AvgOf_fBodyAccMeanFreq_X      
AvgOf_fBodyAccMeanFreq_Y      
AvgOf_fBodyAccMeanFreq_Z      
AvgOf_fBodyAccJerkMean_X      
AvgOf_fBodyAccJerkMean_Y      
AvgOf_fBodyAccJerkMean_Z     
AvgOf_fBodyAccJerkSTD_X       
AvgOf_fBodyAccJerkSTD_Y     
AvgOf_fBodyAccJerkSTD_Z       
AvgOf_fBodyAccJerkMeanFreq_X  
AvgOf_fBodyAccJerkMeanFreq_Y  
AvgOf_fBodyAccJerkMeanFreq_Z  
AvgOf_fBodyGyroMean_X         
AvgOf_fBodyGyroMean_Y         
AvgOf_fBodyGyroMean_Z         
AvgOf_fBodyGyroSTD_X          
AvgOf_fBodyGyroSTD_Y          
AvgOf_fBodyGyroSTD_Z          
AvgOf_fBodyGyroMeanFreq_X     
AvgOf_fBodyGyroMeanFreq_Y     
AvgOf_fBodyGyroMeanFreq_Z     
AvgOf_fBodyAccMagMean         
AvgOf_fBodyAccMagSTD          
AvgOf_fBodyAccMagMeanFreq     
AvgOf_fBodyAccJerkMagMean     
AvgOf_fBodyAccJerkMagSTD      
AvgOf_fBodyAccJerkMagMeanFreq 
AvgOf_fBodyGyroMagMean        
AvgOf_fBodyGyroMagSTD         
AvgOf_fBodyGyroMagMeanFreq    
AvgOf_fBodyGyroJerkMagMean    
AvgOf_fBodyGyroJerkMagSTD     
AvgOf_fBodyGyroJerkMagMeanFreq

**Notes on variable names:**    

variable name element | description   
------------- | -------------   
t             | this prefix denotes a time domain signal    
f             | this prefix denotes a frequency domain signal
_X, _Y, _Z    | these suffixes indicates one of the triaxial planes
Mag           | magnitude of the signals calculated using the Euclidian norm
BodyAcc       | body acceleration signal   
BodyAccJerk   | body linear acceleration signal  
GravityAcc    | gravity acceleration signal  
std           | standard deviation

### References
1. Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

2. Queensland Sports Technology Cluster "Inertial Sensors in Sports (accelerometers and gyroscopes)" Page. URL: http://www.qsportstechnology.com/sports-engineering/inertial-sensors-in-sports.  Accessed 6/20/2014. Queensland Sports Technology Cluster, Griffith University, Brisbane Australia.

3. UCI HAR Dataset webiste on the UCI Machine Learning Repository.  URL: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones.  Accessed 6/21/2014. 

4. Coursera "Getting and Cleaning Data" website. URL: https://class.coursera.org/getdata-004/human_grading/view/courses/972137/assessments/3/submissions.  Accessed 6/21/2014.
