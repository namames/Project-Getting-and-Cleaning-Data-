---
output:
  pdf_document: default
  html_document: default
---
## Variables used to gather data  

filename - used to download data and to verify it exists in the working directory.  
activities - includes the activities performed by the subjects  
features - data given by the accelerometer and gyroscope  
subject_test - data of test subjects observed  
x_test - recorded features test data  
y_test - test data of activities  
subject_train - data of train subjects observed  
x_train - recorded features train data  
y_train - train data of activities  



## Step 1  
Variables used to merge the data  
X is created by merging x_train and x_test using rbind() function  
Y is created by merging y_train and y_test using rbind() function  
subject is created by merging subject_train and subject_test using rbind() function  
merged is created by merging X, Y, and subject using cbind() function. This will create one dataset with variables and observations  

## Step 2  
data set with specifications given by project (mean and std for each measurement)  
data is created by subsetting merged, selecting only columns: "subject", "code" and the measurements on the mean and standard deviation (std)  

## Step 3  
Giving more descriptive names to "code" column by replacing codes with corresponding activity   

## Step 4  
Labeling other variables with a more descriptive variable name using gsub() function  
code column in data renamed to activities  
All Acc in column’s name replaced by Accelerometer  
All Gyro in column’s name replaced by Gyroscope  
All BodyBody in column’s name replaced by Body  
All Mag in column’s name replaced by Magnitude  
All start with character f in column’s name replaced by Frequency  
All start with character t in column’s name replaced by Time  


## Step 5  
Creating final dataset with the average of each variable for each activity and subject  
data2 is created by grouping the dataset "data" by subject and activity, and summarizing the average of each variable.  
Finally, the data is exported into "data.txt"  




