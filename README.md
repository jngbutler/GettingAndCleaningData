README
========================================================
(Coursera "Getting and Cleaning Data" Course Project, June 2014)
--------------------------------------------------------
### Data Files
The following data files, available through the Coursera "Getting and Cleaning Data" course, were downloaded from 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip on June 21, 2014.

* Train (folder)
  * subject_train.txt
  * X_train.txt
  * y_train.txt
* Test (folder)
  * subject_test.txt
  * X_test.txt
  * y_test.txt
* activity_labels.txt
* features.txt

The "subject_train.txt" and "subject_test.txt" files contained the training subject ID's and the test subject ID's respectively.
The "X_train.txt"" and "X_test.txt" files contained the study data in the form of 7352 observations (training subjects) and 2947 observations (test subjects) on 561 variables V1 through V561 (which were the data derived from the sensor signals).
The "y_train.txt"" and "y_test.txt" files contained the activity code (what each subject was doing at the data collection timepoint)
The "activity_labels.txt" and "features.txt" provided the description labels for the 6 activity codes and the 561 variable codes respectively.

Additional files "README.txt" and "features_info.txt" provided information the research and about the selected variables in the UCI HAR Dataset.

### Data Processing Steps
1. Read into R the training data files and concatenate (using cbind) them into one training dataframe "train"
2. Read into R the test data files and concatenate (using cbind) them into one test dataframe "test"
3. Combine (using rbind) the training and test dataframes into a single dataframe "data"
4. Rename variables V1 through V561 using description labels from "features.txt"
5. Extracted (using grepl) those variables containing measurements for "mean" or "std" (standard deviation) and subsetting the dataframe to only include those columns
6. Identify the activity code with its activity label (using the merge function)
7. Clean up the variable names to remove illegal characters such as parentheses() and typos (e.g. BodyBody)
8. Calculate the average of each variable for each activity and each subject (using the aggregate function to compute summary means by subject ID and activity label)

### Variable Selection 
The assignment asks us to extract variables that contain the mean and std of each measurement.  Some may argue that this only includes variables that contain "mean()" or "std()".  

For purposes of this assignment, I **include** the 7 **mean** variables such as "fBodyAcc-meanFreq()-Z" which is the MEAN of the Frequency of the Body Acceleration signal.  

However, I do **exclude** the 7 **angle** variables such as "angle(tBodyAccMean,gravity)" which although it contains the string "mean", is defined in the "features_info.txt"" file as the "ANGLE between [the two] vectors" for Body Acceleration Mean and gravity.

### Tidying Up Variable Names
1. Use make.names function to transform variable names into legal names (remove illegal characters)
2. Use gsub function to remove extra periods (.) produced by make.names and to remove the typo "BodyBody" 
3. Use a combination of lower case and capital letters (e.g. tBodyAccSTD ) to make longer strings easier to read
4. Use underscore (_) to separate the triaxial notation from the rest of the string (e.g. tBodyAccSTD_Z) for easier identification

### Final Tidy Data Set
The final "tidy data" set consists of 180 rows (6 activities x 30 subjects) and 81 columns (subjectid, activitylabel, and 79 measurement averages).


**_Note: This is a text file with comma-separated values, please use read.table with sep = "," or read.csv with default arguments to read the file into R._**

```{r}
read.table("./tidy_data.txt", sep=",")
read.csv("./tidy_data.txt")
```
