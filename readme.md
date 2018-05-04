# Project 2 - Ames Housing Data and Kaggle Challenge

Due Date: **May 18, 2018**

Welcome to Project 2! It's time to start modeling. 

1. Creating and iteratively refining a regression model
2. Using [Kaggle](https://www.kaggle.com/) to practice the modeling process

You are tasked with creating a regression model based on the Ames Housing Dataset. This model will predict the price of a house at sale.

The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses.

Secondly, we are hosting a competition on Kaggle to give you the opportunity to practice the following skills:

- Refining models over time
- Use of train-test split, cross-validation, and data with unknown values for the target to simulate the modeling process
- The use of Kaggle as a place to practice data science

## Set-up

Before you begin working on this project, please do the following:

1. Sign up for an account on [Kaggle](https://www.kaggle.com/)
2. **IMPORTANT**: Click this link ([Regression Challenge Sign Up](https://www.kaggle.com/t/ef1b2451fd2c4efc9292b5d5821c1c7e)) to **join** the competition (otherwise you will not be able to make submissions!)
3. Review the material on the [DSI-US-4 Regression Challenge](https://www.kaggle.com/c/dsi-us-4-project-2-regression-challenge)

## The Modeling Process

1. The train dataset has all of the columns that you will need to generate and refine your models. The test dataset has all of those columns except for the target that you are trying to predict in your Regression model.
2. Generate your regression model using the training data. We expect that within this process, you'll be making use of:
    - train-test split
    - cross-validation / grid searching for hyperparameters
    - strong exploratory data analysis to question correlation and relationship across predictive variables
    - code that reproducibly and consistently applies feature transformation (such as the preprocessing library)
3. Predict the values for your target column in the test dataset and submit your predictions to Kaggle to see how your model does against unknown data.
    - **Note**: Kaggle expects to see your submissions in a specific format. Check the challenge's page to make sure you are formatting your files correctly!

## Submission Checklist

We expect the following to be submitted by end of day on the due date.

1. Your code for the regression model, including your exploratory data analysis. Add your (well organized!) notebooks to this repository and submit a pull request.
2. At least one successful prediction submission on [DSI-US-4 Regression Challenge](https://www.kaggle.com/c/dsi-us-4-project-2-regression-challenge) --  you should see your name in the "[Leaderboard](https://www.kaggle.com/c/dsi-us-4-project-2-regression-challenge/leaderboard)" tab.
3. Check the Project Feedback + Evaluation section (below) to ensure that you know what will factor into the evaluation of your work.

## Project Feedback + Evaluation

For all projects, students will be evaluated on a simple 4 point scale (0-3 inclusive). Instructors will use this rubric when scoring student performance on each of the core project requirements:

Score | Expectations
----- | ------------
**0** | _Does not meet expectations. Try again._
**1** | _Approaching expectations. Getting there..._
**2** | _Meets expecations. Great job._
**3** | _Surpasses expectations. Brilliant!_

For Project 2 the evaluation categories are as follows:

- **Organization**:	Clearly commented, annotated and sectioned Jupyter notebook or Python script.  Comments and annotations add clarity, explanation and intent to the work.  Notebook is well-structured with title, author and sections. Assumptions are stated and justified.
- **Presentation**: The goal, methodology and results of your work are presented in a clear, concise and thorough manner.  The presentation is appropriate for the specified audience, and includes relevant and enlightening visual aides as appropriate. 
- **Data Structures**: Python data structures including lists, dictionaries and imported structures (e.g. DataFrames), are created and used correctly.  The appropriate data structures are used in context.  Data structures are created and accessed using appropriate mechanisms such as comprehensions, slices, filters and copies.
- **Python Syntax and Control Flow**: Python code is written correctly and follows standard style guidelines and best practices.  There are no runtime errors.  The code is expressive while being reasonably concise.
- **Modeling**: Data is appropriately prepared for modeling.  Model choice matches the context of the data and the analysis.  Model hyperparameters are optimized.  Model evaluation is robust.  Model results are extracted and explained either visually, numerically or narratively.
- **Regression Challenge Submission**: Student has made at least one successful submission to the [DSI-US-4 Regression Challenge](https://www.kaggle.com/c/dsi-us-4-project-2-regression-challenge)

Your final assessment ("grade" if you will) will be calculated based on a [topical rubric](https://docs.google.com/spreadsheets/d/1V6OzSHPXCJEe_sVT7B1vE7sT-jqNMNo-NrmZHtafMXY/edit?usp=sharing). For each category, you will receive a score of 0-3. From the [rubric](https://docs.google.com/spreadsheets/d/1V6OzSHPXCJEe_sVT7B1vE7sT-jqNMNo-NrmZHtafMXY/edit?usp=sharing) you can see descriptions of each score and what is needed to attain those scores.
