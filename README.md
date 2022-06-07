# Peer-graded-Assignment-Getting-and-Cleaning-Data-Course-Project

Step 1: Merges the training and the test sets to create one data set.
X <- rbind(x_train, x_test)
Y <- rbind(y_train, y_test)
Subject <- rbind(subject_train, subject_test)
Merged_Data <- cbind(Subject, Y, X)

Step 2: Extracts only the measurements on the mean and standard deviation for each measurement.
TidyData <- Merged_Data %>% select(subject, code, contains("mean"), contains("std"))

Step 3: Uses descriptive activity names to name the activities in the data set.
TidyData$code <- activities[TidyData$code, 2]
