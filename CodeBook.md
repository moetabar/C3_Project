I try to explain how my code works:

STEP 1
====================================

In the first Step we try to read training data and integrate them all together and make
one data frame which has following structure:
  ## Subject  Activity_Label  561 columns for features 128 columns for each body/total X,Y,Z acc&Gyro
  ## -------  -------------   ------------------------ ------------------------------------------- 
This data is stored in  "train_tidy_data" data frame.
Next we repeat the similar step to generate  "test_tidy_data" data frame.

Now that we have both train and test data in tidy shape we merge them together and 
store them in "merge_tidy_data" data frame.

STEP 2
====================================

Here the mean and sdt columns plus activity_label and subject are extracted from merge_tidy_data
and stored in "mean_sd_data" data frame. This data frame will be used by the rest of the code

STEP 3 &4
====================================
Here the activity_label file is read and then mapped to label column of the data frame (mean_sd_data)
in other words numbers 1 to 6 are replaced by ativities lile WALKING, etc
Also please be advised that labeling of all variables have been done in former steps
so this also addresses step 4 of the project as well.


STEP 5
====================================

Next, for better presentation first we sort our data frame from previous step by subject
and store that in "ordered_data" data frame and next we group it by subject and label (activity)
Finally we run mean over the grouped segments using summerize function and store the result
in two formats: result.txt and result.csv for better presentation 