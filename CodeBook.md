The `run_analysis.R` script performs the data preparation and then followed
by the 5 steps required as described in the course project’s definition.

1. Download the dataset
* Dataset downloaded and extracted under the folder called `UCI HAR Dataset`
within folder `data` in currently work directory

2. REading all data to variables
    * `features`
    * `activities`
    * `subject_test`
    * `x_test`
    * `y_test`
    * `subject_train`
    * `x_train`
    * `y_train`

3. Merges the training and the test sets to create one data set
`x` is created by merging `x_train` and `x_test` using `rbind()` function
`y` is created by merging `y_train` and `y_test` using `rbind()` function
`subject` is created by merging `subject_train` and `subject_test` using 
`rbind()` function
Finally, `mergedData` is created by merging `subject`, `y` and `x` using 
`cbind()` function

4. Extracts only the measurements on the mean and standard deviation for each
measurement
`tidyData` is created by subsetting mergedData, selecting only columns: subject,
code and the measurements on the mean and standard deviation for each
measurement

Uses descriptive activity names to name the activities in the data set
Entire numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable

Appropriately labels the data set with descriptive variable names
code column in TidyData renamed into activities
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns) is created by sumarizing TidyData taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export FinalData into FinalData.txt file.