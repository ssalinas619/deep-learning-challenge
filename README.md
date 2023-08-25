## deep-learning-challenge report

# Overview of the analysis: Explain the purpose of this analysis.
The non-profit foundation Alphabet Soup is asking for a tool to help select what applicants to fund in order to have the best chance of success. The purpose of the analysis is to train the model to see which features (application type, classification, organization, etc) correlate best to succesful ventures (using the 'IS_SUCCESSFUL' column).

## Results: Using bulleted lists and images to support your answers, address the following questions:

## Data Preprocessing
# What variable(s) are the target(s) for your model?
The target variable used was 'IS_SUCCESFUL' because it helps answer our question at hand
# What variable(s) are the features for your model?
The features of the model include 'NAME', 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', 'ASK_AMT'

# What variable(s) should be removed from the input data because they are neither targets nor features?
The variable that I removed from the input data was 'EIN' which is the identification number

## Compiling, Training, and Evaluating the Model
# How many neurons, layers, and activation functions did you select for your neural network model, and why?
In my first attempt I started off with 3 layers:
first 80 with activation=relu
second 30 with activation=relu
output with activation=sigmoid
I chose to do a model similar to ones we worked on previously in class in order to create a baseline for my first attempt.
# Were you able to achieve the target model performance?
In my first attempt I was only able to achieve an accuracy score of 73% (0.7306) but in my optimization attempt I was able to achieve the target model with an accuracy score of 76% (0.7628)
# What steps did you take in your attempts to increase model performance?
To increase my model performance I included the 'NAME' column and created an 'other' bin for any names that had been used less than 100 times (in order for in to be readable by the amount of RAM available in Googlecolab).
I also added an additional layer and minimized the number of nodes:
first 30
second 20
third 20
output
Lastly I decreased the number of epochs to 50
# Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
The model was able to achieve the goal (75% accuracy) with an accuracy score of 76%. However for investments it is important for accuracy to be as close to 100% as possible. To account for the many features of the data set, I would reccomend a random forest model instead to see if that would improve accuracy.