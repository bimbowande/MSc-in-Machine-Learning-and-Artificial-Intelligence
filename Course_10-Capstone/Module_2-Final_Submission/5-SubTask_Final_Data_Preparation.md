# SubTask: Final Data Preparation

Once you are ready with the preprocessed data set, you can go ahead and complete the final data preparation steps such as various aggregations and joins at a device_id level before doing the train-test split for our model building. Let's watch the next video to learn more about this.

**VIDEO**

In the video above, Arihant explained how your final preprocessed data would look like after completing all the data cleaning and feature engineering steps.  At this juncture, you will have to split the data into train data and test data for further modelling purposes. The file attached below includes a new column flag appended to the original device information, to provide you with the mapping that you need to consider while splitting the data.

Download [train_test_split](train_test_split.csv)

## **Important Note**

**Be careful while handling the CSV file provided here. It may be possible for the device_id information to get corrupted on frequent opening and closing of the file. This would lead to a mismatch in the device_id information present in the train tables and the train_flaginformation file.**

Also, you will have to keep in mind Scenario 1 and Scenario 2, which we discussed earlier during the data ingestion process. Essentially, all the device ids available with you will not have the corresponding event data, so the modelling process has to be different for these two cases. You will learn more about this in the next segment.