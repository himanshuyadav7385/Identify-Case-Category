## Use Text Classification to Indentify case category

**Himanshu Yadav**

### Executive summary

**Project overview and goals:** 
The goal of this project is to build a robust machine learning model to automate the categorization of support cases. This model will analyze the text fields, specifically the "Short Description" and "Description," of a case and assign it to the correct category for routing to the appropriate support queue. The categorization hierarchy consists of two levels:

- **Level 1 (Parent Categories):** "Incident" and "Service Request."
- **Level 2 (Child Categories):** Subcategories under each parent category:
    - **Incident:** "Platform Issue" and "Integration Issue."
    - **Service Request:** "User Help" and "User Access."
      
The model employs a two-step binary classification approach:

1) **Parent Category Classification:** Determines whether a case belongs to "Incident" or "Service Request."
2) **Child Category Classification:** Assigns one of the four child categories based on the parent category.
   
To achieve this, we evaluate and tune four text classification algorithms: **Logistic Regression, Support Vector Machine (SVM), Decision Tree,** and **Naive Bayes.** Key performance metrics include **Accuracy, Precision, Recall,** and **F1-Score,**.

**Usage** 
This project addresses a real-world problem faced by support teams. I lead four support teams managing distinct areas of expertise, and this model will be integrated into a chatbot that assists users in raising tickets by directing their queries to the appropriate support queue. The chatbot will:

 - Parse user inputs about issues or questions.
 - Automatically categorize and assign cases to the correct team, reducing delays in issue resolution.
   
Future iterations of the project aim to enhance the system by identifying similar past tickets and sharing their resolutions with support engineers, enabling quicker problem resolution.

**Data and Testing**
The project leverages two years of historical support case data, with "Short Description" and "Description" fields serving as the primary input features. Each case is tagged with corresponding Parent Tags and Child New Tags columns, which serve as ground truth labels for training and validation. The model's performance will also be tested on unseen data from the last two months, ensuring its effectiveness in real-world scenarios.

**Training data**  https://github.com/himanshuyadav7385/Identify-Case-Category/blob/main/Working_data2.xlsx 

**Unseen data**  https://github.com/himanshuyadav7385/Identify-Case-Category/blob/main/test_data.xlsx 

**Results**
Among the four models evaluated, **Logistic Regression** emerged as the best-performing model overall. While **SVM** achieved slightly better performance in the parent classification task, Logistic Regression excelled in child classification and demonstrated significantly better performance on unseen data. Based on these results, Logistic Regression was selected as the final model for deployment.

The model's performance on the test set was impressive, achieving accuracy above 90%. However, there is room for improvement, particularly in the child classification task for unseen data. Performance for the "Platform Issue" category was notably lower, indicating the need for further investigation to understand and address this shortfall.

Given the strong performance of the parent classification task, the model is in a deployable state. Moving forward, efforts will focus on improving the child classification results, especially for underperforming categories, to enhance the model’s overall effectiveness.




![Parent Classification results](Parent%20Results.jpg)

![Child Classification results](Child%20Results.png)

###**Logistic regression Score on unseen data:**

##### Parent Tag Classification Report

| Class             | Precision | Recall | F1-Score | Support |
|--------------------|-----------|--------|----------|---------|
| Incident           | 0.77      | 0.70   | 0.73     | 86      |
| Service Request    | 0.85      | 0.89   | 0.87     | 164     |
| **Accuracy**       |           |        | 0.82     | 250     |
| **Macro Avg**      | 0.81      | 0.79   | 0.80     | 250     |
| **Weighted Avg**   | 0.82      | 0.82   | 0.82     | 250     |

**Parent Tag Accuracy:** 0.82

---

##### Child Tag Classification Report

| Class               | Precision | Recall | F1-Score | Support |
|----------------------|-----------|--------|----------|---------|
| Integration Issue    | 0.69      | 0.64   | 0.67     | 56      |
| Platform Issue       | 0.54      | 0.47   | 0.50     | 30      |
| User Access          | 0.79      | 0.68   | 0.73     | 82      |
| User Help            | 0.60      | 0.74   | 0.67     | 82      |
| **Accuracy**         |           |        | 0.67     | 250     |
| **Macro Avg**        | 0.66      | 0.63   | 0.64     | 250     |
| **Weighted Avg**     | 0.68      | 0.67   | 0.67     | 250     |

**Child Tag Accuracy:** 0.67


#### **Code and Details of each step is available here** - 
[https://github.com/himanshuyadav7385/Identify-Case-Category/tree/main/Models](https://github.com/himanshuyadav7385/Identify-Case-Category/blob/main/Capstone_Classify_Cases.ipynb)

#### **Trained models can be fount here** :- 
https://github.com/himanshuyadav7385/Identify-Case-Category/tree/main/Models



