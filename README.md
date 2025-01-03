## Use Text Classification to Indentify case category

**Himanshu Yadav**

### Executive summary

**Project overview and goals:** The goal of this project is to build a model that assigns a category to a support case so that it can be assigned to the right support queue. The model will read the description and short description of the case and assign the right category. There are two levels of category (Parent and child) . level one categories are  "Incident" and "Service Requests" . There are 4 level two categories and each of these four are sub categories of level 1 . Sub categories of Incident are "Platform Issue" and "Integration issue" and sub categories of Service Requests are "User Help" and "User Access". We will be doing two level of binary classification and assign one of the four level two category to a case. We will be training and tuning four binary text classification models to accurately classify each case. Four approaches considered are  
"Logistic Regression", "Support Vector", "Decision Tree", and "Naive Bayes". 
