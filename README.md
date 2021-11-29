
# Spam Analysis on YouTube Comments
By: Mustafa Kolanci


![image](https://i.ytimg.com/vi/al2AN2pbnu8/maxresdefault.jpg)


###  Overview
Capstone Project for Flatiron Data Science BootCamp. In this Project, I generate various models to accurately identify whether a YouTube comment is spam or non-spam. I start by importing necessary packages, cleaning/preprocessing the data and building a baseline model. This spam detection model is needed to provide better user experience for both content and comment owners. Some of the recomendations include only using this model on music video comments and flagging the detected spam comments instead of removing them.


### Stakeholder
YouTube's maintanence team

### Business Problem
As a data scientist, I was approached by a stakeholder, Youtube's maintance team. They have noticed that many popular music videos have several spam comments under them. Spam comments are undesired comments that are not related to the music video. They would like detect these comments in order to improve user experience. Therefore, they have asked me to generate a model that performs spam detection analysis in order to categorize comments as spam and not spam.


### Data
The dataset is taken from https://archive.ics.uci.edu/ml/datasets/YouTube+Spam+Collection.
The dataset is from the year 2013 and includes  1,956 comments. There are five columns, the first column is the comment id, the second column is the author of comment, the third column is the date comment was submitted, the fourth column is the comment itself and fifth column is the category of comment (spam is 1 and non-spam is 0).

### Methods
I first import and prepare the data, then I use regex to clean the comments from all html tags. After that, I use regex again to detect and label the urls in the comments and filter the comments so that only the alphanumeric characters remain. Next, I tokenize the comments to split each comment into words so that each word is a feature in the model. I also remove common English stopwords as they provide little to no value to spam analysis. Then, I use lemmatization to group words with the same meaning together as one word. Finally, I use TF-IDF to assign each word in each comment a numeric value based on its importance across all comments. I use pandas to perform data analysis and filtering, nltk to perform text preprocessing, and sklearn for TF-IDF. For modeling, I utilize the sklearn's MultinomialNB, LogisticRegression, and RandomForestClassifier methods. I tune the models using GridSearchCV also provided by sklearn.

### Conclusion 
The goal of this project was to come up with a method to perform spam analysis on popular YouTube music video comments. To do so, I created multiple classification models and identified the best one as both logistic regression and random forest models with both having a test accuracy of 88%. These models will allow the stakeholder to identify most spam comments correctly.

### For More Information
Please review our full analysis in our [Jupyter Notebook]() or our [presentation]().
### Repository Structure

```

├── data <- folder that includes the five csv files that contain all the data


├── README.md <- The top-level README for reviewers of this project, you are reading it right now


└──  Spam_Analysis_on_YouTube_Comments.ipynb <- Jupyter Notebook
