# Neural_Network_Charity_Analysis
## Overview of the Analysis
In this project, we have been tasked with creating a binary classifier deep learning model in order to predict whether applicants will be successful if funded by Alphabet Soup.

## Results
### Data Preprocessing
The data was contained in a CSV file named 'charity_data'.  This file contained over 34,000 organizations who received funding from Alphabet Soup over several years. Each organization had values for the following fields:<br />
['EIN', 'NAME', 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION','USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT','SPECIAL_CONSIDERATIONS', 'ASK_AMT', 'IS_SUCCESSFUL']<br />

The target variable in the data set is 'IS_SUCCESSFUL'.  This is a 1 if the applicant was sucessful and 0 otherwise.  The fields 'EIN', and 'NAME' were removed from the data as they are only identifiwers and would have no influence in the model.  The rest of the variables were considered features.<br />
For features with many different values (such as 'INCOME_AMT') binning was used to collate similar data and simplify the model.<br />
The categorical data variables were encoded and the data was seperated into stratified training and testing sets.<br />
### Compiling, Training and Evaluating the Model
#### Model 1
The first deep nural net consisted of 2 hidden layers  with a 'relu' activation function utilized for the two hidden layers and a 'sigmoid' activation function for the output layer.  This model was trained through 50 epochs and returned an accuracy of roughly 72.3 percent.<br />
### Reducing Features
To simplify the model and hopefully imprive accuracy, many features were removed due having very little variance in the data.  For example, the field 'SPECIAL_CONSIDERATIONS_N' had only 27 organization with the value 0 out of the over 34,000 total.  This suggests very few organiaztions would be affected by this variable so it was removed. The complete list of the variables removed for this reason is given below:<br />
<br />
'STATUS', 'AFFILIATION_Other', 'AFFILIATION_Regional', 'AFFILIATION_Family/Parent', 'USE_CASE_Other', 'ORGANIZATION_Corporation', 'SPECIAL_CONSIDERATIONS_N', 'SPECIAL_CONSIDERATIONS_Y'<br />
#### Model 2
In order to improve upon the previous model accuracy, an additional hidden layer was added. It was speculated that additional functionality would improve the model accuracty. In addition, the model was trained for an additional 25 epochs (75 total).  However, these changes had very little effect, with the final accuracy of 72.5 <br />
### Model 3
This model changed the number of nodes for the second and third hidden layer (see table below). Again, there was essentially no change in the accuracy (72.6 percent)<br />
### Model 4
This model changed the activatoin function of the first two layers to 'tanh'. Again, no improvement on the accuracy (72.5 percemnt).<br />
<br />
A summary of the model results is shown below:
