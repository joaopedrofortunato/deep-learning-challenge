# deep-learning-challenge

## Description

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With knowledge of machine learning and neural networks, the features in the provided dataset were used to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Info / Credits

- Analysis by `João Pedro Fortunato` [@joaopedrofortunato](https://github.com/joaopedrofortunato)

- `REPO`: https://github.com/joaopedrofortunato/deep-learning-challenge.git

## Output/Report

# **Alphabet Soup Neural Network Model Analysis**

---

## **Overview of the Analysis**

The purpose of this analysis is to leverage machine learning, particularly deep learning neural networks, to predict the success of organizations seeking funding from the Alphabet Soup foundation. This tool will aid the foundation in optimizing its investments by funding organizations that are more likely to succeed in their ventures.


###**MODELING**

***Data Preprocessing***

- **Target Variable(s)**
  - The target for our model is **'IS_SUCCESSFUL'**.

- **Feature Variables**
  - The features considered for our model include:

    - 'APPLICATION_TYPE'
    - 'AFFILIATION'
    - 'CLASSIFICATION'
    - 'USE_CASE',
    - 'ORGANIZATION'
    - 'STATUS'
    - 'INCOME_AMT'
    - 'SPECIAL_CONSIDERATIONS'
    - 'ASK_AMT'
    - 'IS_SUCCESSFUL'

- **Variables to be Removed**
  - The following variables were removed from the input data since they neither served as targets nor features:
    - 'EIN'
    - 'NAME''
    

###***Compiling, Training, and Evaluating the Model***

**Neural Network Architecture**

  - **Rationale for Architecture Choice**:
    - Drop the non-beneficial ID columns `'EIN'` and `'NAME'`.
    - Choose a cutoff value and create a list of application types to be replaced `application_types_to_replace` and `classifications_to_replace`.
    - Convert categorical data to numeric with `pd.get_dummies`.
    - Split our preprocessed data into our features and target arrays.
    - Split the preprocessed data into a training and testing dataset.
    - Scale the data
    - Define de model as "neural network"
    

  - **Number of Neurons and Layers**:
    - The neural network model consists of `2` layers.
    - Layer 1: `10` neurons
    - Layer 2: `5` neurons

  - **Activation Functions**:
    - For input layer: `relu`
    - For hidden layers: `relu`
    - For output layer: `sigmoid`

- **Model Performance**
  - The model achieved a performance accuracy metric of `73.12%` which `IS_NOT` within the desired target of `75.00%`.


##**MODEL OPTIMIZATION**

###***Data Preprocessing***

- **Target Variable(s)**
  - The target for our model is **'IS_SUCCESSFUL'**.

- **Feature Variables**
  - The features considered for our model include:

    - 'APPLICATION_TYPE'
    - 'AFFILIATION'
    - 'CLASSIFICATION'
    - 'USE_CASE',
    - 'ORGANIZATION'
    - 'INCOME_AMT'
    - 'ASK_AMT'
    - 'IS_SUCCESSFUL'

- **Variables to be Removed**
  - The following variables were removed from the input data since they neither served as targets nor features:
    - 'STATUS'
    - 'SPECIAL_CONSIDERATIONS'

###***Compiling, Training, and Evaluating the Model***

**Neural Network Architecture**

  - **Rationale for Architecture Choice**:
    - Drop the non-beneficial ID columns `'STATUS'` and `'SPECIAL_CONSIDERATIONS'`.
    - Choose a cutoff value and create a list of application types to be replaced `affiliations_to_replace`, `use_cases_to_replace` and `organization_to_replace`.
    - Convert categorical data to numeric with `pd.get_dummies`.
    - Split our preprocessed data into our features and target arrays.
    - Split the preprocessed data into a training and testing dataset.
    - Scale the data.
    - Define de model as "neural network".
    - Run `Keras Tuner`.

- **Top 3 Keras Tuner Results**
  - **Top 1**: `{'activation': 'sigmoid', 'first_units': 33, 'units_0': 13, 'units_1': 3, 'units_2': 23, 'units_3': 18, 'units_4': 18, 'tuner/epochs': 20, 'tuner/initial_epoch': 7, 'tuner/bracket': 1, 'tuner/round': 1, 'tuner/trial_id': '0019'}`
  - **Top 2**: `{'activation': 'sigmoid', 'first_units': 8, 'units_0': 23, 'units_1': 28, 'units_2': 23, 'units_3': 38, 'units_4': 33, 'tuner/epochs': 20, 'tuner/initial_epoch': 7, 'tuner/bracket': 2, 'tuner/round': 2, 'tuner/trial_id': '0015'}`
  - **Top 3**: `{'activation': 'tanh', 'first_units': 23, 'units_0': 28, 'units_1': 28, 'units_2': 13, 'units_3': 23, 'units_4': 3, 'tuner/epochs': 20, 'tuner/initial_epoch': 0, 'tuner/bracket': 0, 'tuner/round': 0}`

- **Model Performance**
  - **Top 1**: The model achieved a performance metric of `73.42%` which `IS_NOT` within the desired target of `75.00%`.
  - **Top 2**: The model achieved a performance metric of `73.31%` which `IS_NOT` within the desired target of `75.00%`.
  - **Top 3**: The model achieved a performance metric of `73.15%` which `IS_NOT` within the desired target of `75.00%`.


---

**CONCLUSION**

The developed neural network model showcases the potential of using `Keras Tuner` to optimize the success of prediction models. Even though `73.42%` `IS_NOT` within our initial target of `75.00%`, there was an increase of about `0.31%` compared to the original model.

---
