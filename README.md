# Heart Disease Prediction

## Abstract
Heart disease is one of the most significant causes of mortality in the world today. Prediction of cardiovascular disease is a critical
challenge in the area of clinical data analysis. Machine learning (ML) has been shown to be effective in assisting in making
decisions and predictions from the large quantity of data produced by the healthcare industry. We have also seen ML techniques
being used in recent developments in different areas of the Internet of Things. Various studies give only a glimpse into predicting
heart disease with ML techniques. In this project, we propose a method that aims to find significant features by applying
machine learning techniques that improve the accuracy of the prediction of cardiovascular disease. The prediction model
is introduced using logistic regression techniques.

## Methods 
In the part of working with a structured dataset we first cleaned our data by determining how many NaN values we have and plotting a histogram of missing values. After removing missing values, we decided to see our categorical variables distribution. After that we plot variables correlation to see which features are correlated with our target. We found out there are some features that are highly correlated with each other. We trimmed some of them to reduce the dimensions of our features.

● “sysBP” and “diaBP” are highly correlated. (0.79)

● “prevalentHyp” and “sysBP” are highly correlated. (0.7)

● “currentSmoker” and “cigsPerday” are highly correlated. (0.77)

Then we check how each of these features are correlated with our target (“TenYearCHD”)

● “currentSmoker” = 0.019

● “diaBP” = 0.15

● “prevalentHyp” = 0.18

We found important features by performing a Logistic Regression and evaluating coefficients. We also used the RandomForestClassifier to find important features. We achieved some evidence that shows the most important features are 1,9,10,11,12,13,14 ['age', 'totChol', 'sysBP', 'diaBP', 'BMI', 'heartRate', 'glucose']. The third method we used to make sure was the chi-squared (chi²) statistical test. But before that, we decided to see how our target was balanced to determine which metrics we should use to evaluate our model. Our dataset is imbalanced, so we used confustion_matrix and roc_auc_score. We also over-sampled our dataset to create a balanced dataset.

In image classification, we split the dataset into 2part: one for the train test, which contains ¾ of the main data, and the rest for test data. By looking at the data, we understood that our data was not balanced. Most of the samples are type ‘0’, which is a normal heartbeat. On the other hand, we have the least number of Fusion Beats. So, we resample the data next and get a dataset that includes 100,000 samples, with each category having 20,000 samples. After that, we visualized one sample from each category. Then, we plot one sample from 4 abnormal heartbeats.

Then, we work on building our Neural Network. Since our data is image, and these images represent a signal we decided to use CNN instead of other methods like RNN. In our model, we used three CNN layers. For CNN layers, we used the Relu activation function since these days, this method works better than the others. After each CNN layer we used BatchNormalization which applies a transformation that maintains the mean output close to 0 and the output standard deviation close to 1. Following by Batchnormalization, using MaxPool is a good option. MaxPool is used to downsample the input representation by taking the maximum value over a spatial window of pool size. After that, we flatten the output to be ready as input of next dense layers. The learned features are flattened to one long vector and pass through a fully connected three layers’ network before the output layer used to make a prediction. In the last dense layer, we used the softmax activation function because our output is multiclass classification. For this model, we will use a standard configuration of 64 parallel feature maps and a kernel size of 3. The feature maps are the number of times the input is processed or interpreted, whereas the kernel size is the number of input time steps considered as the input sequence is read or processed onto the feature maps. Once the model is fit, it is evaluated on the test dataset, and the accuracy of the fit model on the test dataset is returned.

## Note
*The full report is available in the Final FDS project.pdf*

*FDS_Project_final.ipynb notebook contains the codes and details on implementation.*
