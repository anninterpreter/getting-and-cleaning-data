# Getting and Cleaning Data (Johns Hopkins University, Coursera)  
## NOTE: You must extract the zip folder 'UCI HAR Dataset' first in order to move on with the project
**run_analysis.R** file contains all the logic to get and clean data in order to perform analysis.
  
## There are 4 functions in run_analysis.R file  
**1- merge_train_test_dataset**  
The function returns dataset which contains observations from both train and test dataset. It first loads the training data from _X_train.txt_ file stored in _UCI HAR Dataset/train_ directory into a _data table_ and binds with it _subject_ variable as well as _activity_ variable related to the training data, which is stored in file _subject_train.txt_ and _activity_labels.txt_ respectively. It then performs same steps for **test** data as well which is stored in directory _UCI HAR Dataset/test_ and then merges the train and test dataset.  

**2- activities_transforming_into_descriptive_activities**  
The function apply transformation to _activity_ variable by transforming activity values into descriptive form. The following transformation/mapping was applied:  
1 was mapped to WALKING  
2 was mapped to WALKING_UPSTAIRS  
3 was mapped to WALKING_DOWNSTAIRS  
4 was mapped to SITTING  
5 was mapped to STANDING  
6 was mapped to LAYING  

**3- extract_measurements_mean_std**  
The function is resposible for extracting only the measurements on the mean and standard deviation for each measurement from the dataframe returned by above function.  

**4- average_activity_subject**  
The function takes in the dataframe returned by above function and then calculate the average of each variable for each activity and each subject.