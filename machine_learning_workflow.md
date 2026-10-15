
# The Machine Learning Workflow

![workflow_unsplash.jpg](./assets/workflow_unsplash.jpg)

_Photo by Campaign Creators on Unsplash_

## Goal of Machine Learning

The goal of machine learning is to build a machine learning model that uses data to **help us make decisions**, answer questions, or solve problems.

## The Workflow

![ml_workflow.png](./assets/ml_workflow.png)

### Step 1 - Define Business Goal or Research Question

The first step in any data science project is to **define a clear, specific, and measurable goal** that aligns with the overall business or research objectives. Before proceeding, you should assess whether machine learning is the most suitable approach, as simpler alternatives may be more effective in some cases. Additionally, you should ensure that you have sufficient, "high-quality" data to train a reliable model, as data availability and quality significantly impact its performance. You also should establish clear success criteria to determine when the model is adequately refined.

For example, a well-defined goal could be:

> **Develop a predictive model** to estimate the number of bikes required at each station during different times of the day with a Mean Absolute Error (MAE) of less than two bikes, using variables such as time of day, day of the week, weather conditions, and so on.

### Step 2 - Get the Data

Now that your goals are set, it's time to **gather the data** you need. Begin by sourcing from reliable databases, APIs, and public datasets, or by scraping relevant websites. Focus on collecting all crucial attributes for your project, ensuring the data is comprehensive and pertinent for your machine learning models.

### Step 3 - Train-Validation-Test Split

After you collect your data, you should **split the dataset** into three distinct sets: **training data**, **validation data**, and **test data**. This split is crucial for developing a robust machine learning model.

The reason for this division is to ensure that you can accurately assess your model's performance on unseen data. Here’s how it works:

- **Training Data**: This is the main part of your dataset and is used to train your model. The model learns from this data, adjusting its parameters to fit the data as closely as possible.
- **Validation Data**: This subset is used to fine-tune the model's configurations and to select the best version of the model during the training process. It helps in optimizing model parameters and avoiding overfitting.
- **Test Data**: You don’t use this data until the final step of your workflow. This set is crucial because it acts as new, unseen data for the model, simulating how the model will perform in the real world. After all adjustments and selections have been made using the training and validation sets, the test data gives you a final evaluation to see how well your model is likely to perform on data it has never seen before.

### Step 4 - Data Exploration

Before you start modeling, it's crucial to conduct exploratory data analysis (EDA). This step helps you understand the data's structure, identify any outliers, and explore relationships between variables. EDA also involves cleaning the data to ensure accuracy in your analyses. Here’s a checklist to guide you through the process:

- **Understand the Basics**
  - Check data types (categorical, numerical).
  - Examine basic statistics and distributions.
- **Check for Missing Values**
  - Identify missing data.
  - Decide on handling methods (impute or remove).
- **Look for Duplicates**
  - Spot duplicate records.
- **Identify Outliers**
  - Use plots and statistics to detect outliers.
  - Decide on removal or further investigation.
- **Assess Data Quality**
  - Ensure data consistency and accuracy.
  - Correct format or entry errors.
- **Visualize Data**
  - Create visuals for distributions and relationships.
  - Use histograms, box plots, scatter plots.
- **Correlation Analysis**
  - Check variable correlations.

### Steps 5, 6, 7, and 8

As shown in the figure above, the steps of **Feature Engineering**, **Hyperparameter Tuning**, **Model Training**, and **Validating Scoring** work together in an iterative loop within the machine learning workflow. During this iterative loop you can continually refine the model through repeated adjustments and evaluations.

The **Feature Engineering** step involves creating or transforming features based on domain knowledge and initial data analysis. As new insights are gained from the model performance and the validation feedback, you may go back and adjust or create new features.

Before the model is trained, **hyperparameters** (which control the learning process and the structure of the model) need to be set. These may need adjustment if the model does not perform as expected on the **validation data**. With the **features** set and **hyperparameters** configured, **the model** is **trained** on the **training data**. This step **fits** the **model parameters** (weights, biases, etc.) to the data. After the **model** is trained, it is **assessed** using the **validation set**.

#### Baseline Model

**Before starting** the iterative process, however, it's crucial to **establish** a **clear starting point**. One strategy is to research methods that others have successfully implemented, adapt them, and try to improve upon these methods to outperform existing solutions. Another approach is to develop a **simple baseline model** that serves as a benchmark for more complex models to outperform. Typically, a baseline model is **straightforward to implement**. It often relies on domain knowledge or basic assumptions that can quickly be turned into predictive rules. For instance, in the case of the bike rental example, a simple heuristic model could be:
> If the time is during rush hours, predict the number of bikes needed based on the average demand observed during past rush hours. If the time is outside of rush hours, predict the number of bikes needed based on the average demand observed during past non-rush hours.

### Step 9 - Calculate Test Score

After the iterative process, you should select the optimal model and retrain it using the combined training and validation datasets. During this phase, maintain the same features and best hyperparameters you have found before. Finally, you are ready to calculate the test score using the test data.

### Step 10 - Deploy & Monitor

Once the model meets the business requirements, it is ready for deployment in production. While in use, it is crucial to ensure that the model’s performance does not deteriorate. To achieve this, continuous monitoring is necessary, along with setting up an alert system to notify you of performance dips. If performance declines, you may need to gather more data and retrain the model.
