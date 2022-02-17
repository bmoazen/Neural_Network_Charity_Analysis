# Neural_Network_Charity_Analysis
## Overview of the Analysis
In this project, we have been tasked with creating a binary classifier deep learning model in order to predict whether applicants will be successful if funded by Alphabet Soup. To acheive this, we utilized TensorFlow to design, train, and evaluate a neural network.

## Results
### Data Preprocessing
The data was contained in a CSV file named 'charity_data'.  This file contained over 34,000 organizations who received funding from Alphabet Soup over several years. Each organization had values for the following fields:<br />
['EIN', 'NAME', 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION','USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT','SPECIAL_CONSIDERATIONS', 'ASK_AMT', 'IS_SUCCESSFUL']<br />

The target variable in the data set is 'IS_SUCCESSFUL'.  This is a 1 if the applicant was sucessful and 0 otherwise.  The fields 'EIN', and 'NAME' were removed from the data as they are only identifiwers and would have no influence in the model.  The rest of the variables were considered features.<br />
For features with many different values (such as 'INCOME_AMT') binning was used to collate similar data and simplify the model.<br />
The categorical data variables were encoded and the data was seperated into stratified training and testing sets.<br />
### Compiling, Training and Evaluating the Model
#### Model 1
The first deep neural net created consisted of 2 hidden layers  with a 'relu' activation function utilized for the two hidden layers and a 'sigmoid' activation function for the output layer.  This model was trained through 50 epochs and returned an accuracy of roughly 72.3 percent.<br />
#### Reducing Features
To simplify the model and hopefully improve accuracy, many features were removed due having very little variance in the data.  For example, the field 'SPECIAL_CONSIDERATIONS_N' had only 27 organizations with the value 0 (as opposed to 1) out of the over 34,000 total.  This suggests very few organiaztions would be affected by this variable and so it was removed. The complete list of the variables removed for this reason is given below:<br />
<br />
'STATUS', 'AFFILIATION_Other', 'AFFILIATION_Regional', 'AFFILIATION_Family/Parent', 'USE_CASE_Other', 'ORGANIZATION_Corporation', 'SPECIAL_CONSIDERATIONS_N', 'SPECIAL_CONSIDERATIONS_Y'<br />
#### Model 2
In order to improve upon the previous model accuracy, an additional hidden layer was added. It was speculated that additional functionality would improve the model accuracty. In addition, the model was trained for an additional 25 epochs (75 total).  However, these changes had very little effect, with a final accuracy of 72.5 <br />
#### Model 3
This model changed the number of nodes for the first and second hidden layer (see table below). Again, there was essentially no change in the accuracy (72.6 percent)<br />
#### Model 4
This model changed the activation function of the first two layers to 'tanh'. Again, no improvement on the accuracy (72.5 percemnt) was observed.<br />
<br />
A summary of the model results is shown below:<br />
Model Number | Nodes in Layer 1 | Nodes in Layer 2 | Nodes in Layer 3 | Activation Functions | Epochs | Accuracy
--- | --- | --- | --- | --- | --- | ---
1 | 80 | 30 | n/a | relu / relu / sigmoid | 50 | 0.723
2 | 80 | 30 | 20 | relu / relu / relu / sigmoid | 75 | 0.725
3 | 80 | 40 | 15 | relu / relu / relu / sigmoid | 50 | 0.726
4 | 80 | 40 | 25 | tanh / tanh / relu / sigmoid | 50 | 0.725
<br />

## Summary
We were able to achieve an accuracy of roughly 72.5 percent using a neural network designed using TensorFlow. However, this task may have been better served using support vector machine (SVM) instead of deep learning due to the fact that the target variable only had two possibilities. While deep learning can handle classification into many groups, SVM specializes in classifying data into two distinct groups, which is what we have in this task (successful or not successful). For this main reaosn, further study should start with utilizing SVM.
