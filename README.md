## Use Text Classification to Indentify case category

**Himanshu Yadav**

### Executive summary

**Project overview and goals:** The goal of this project is to build a model that assigns a category to a support case so that it can be assigned to the right support queue. The model will read the description and short description of the case and assign the right category. There are two levels of category (Parent and child) . level one categories are  "Incident" and "Service Requests" . There are 4 level two categories and each of these four are sub categories of level 1 . Sub categories of Incident are "Platform Issue" and "Integration issue" and sub categories of Service Requests are "User Help" and "User Access". We will be doing two level of binary classification and assign one of the four level two category to a case. We will be training and tuning four binary text classification models to accurately classify each case. Four approaches considered are  "Logistic Regression", "Support Vector", "Decision Tree", and "Naive Bayes". We will be using Accuracy, Precision, Recall and F1 score to identify the best model. Recall will be most critical as we do not want to miss any incidents as time is critical there. 

**Usage** I am leading around 4 supprt teams supporting different areas . Aim is to add this model as part of a chatbot that we are building where users can ask questions and talk about the issues they are facing and if a support ticket needs to be raised This chat bot can use this model and assign the case to right queue.  this helps in directing the issue to right team quickly. Going forward I also want to expand this to identify past tickets with similar issue and share it with the support engineer for quicker resolution. 

**Usage** I will we using past two years case data . We will be using "Short Description" and "Description" of the cases for the text from which features will be extreacted . Each case is also assigned Parent and child categories under columns "Child New Tags" and "Parent Tags" . We will aslo use last two months data to test the performance of the model. This will act as unseen data. 
