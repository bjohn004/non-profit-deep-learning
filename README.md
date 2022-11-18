This README file contains the analysis for the project. See below.

# 1. Overview
***
The dataset provided is used to help determine if certain characteristics will lead to successful applicants, and whether to fund those applicants or not.

The dataset includes several categorical columns and a couple of numerical columns. We will encode the dataset to provide all numerical columns that will allow us to utilize the TensorFlow library to create a neural network model and analyze the data. There is an initial notebook used to create the model, and then a supplemental notebook used for optimizing the model.

The `initial_AlphabetSoup_deep-learning_analysis.ipynb` contains the initial model.
the `AlphabetSoupCharity.h5` contains the hdf5 file for the model in this notebook.

The `AlphabetSoupCharity_Optimization.ipynb` contains the four optimize models.
There are four additional hdf5 files generated for the 4 attempts at optimizing the model in this notebook: `AlphabetSoupCharity_Optimization_1.h5` , `AlphabetSoupCharity_Optimization_2.h5` , `AlphabetSoupCharity_Optimization_3.h5` , `AlphabetSoupCharity_Optimization_4.h5` 
***

# 2. Results
***
## Data Preprocessing

Target Variable: The chosen Target Variable is the `IS_SUCCESSFUL` column within the dataset. 

Feature Variables: The Feature Variables include, `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`. `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS`, and `ASK_AMT`.

Removed Variables: The `EIN` and `NAME` are initially removed from the dataset because they do not add and value to the target variable. They are just generic details for each applicant. In the optimization notebook, the `STATUS` column was also removed because nearly all of the applicants had the same status value, so it does not really add any additonal information to the model in my opinion.
***

## Compiling, Training, and Evaluating the Model

The initial model utilized 8 neurons and 5 neurons in the 2 hidden layers respectively. The number of features was equal to 50. RELU activation was used on the neural network model as demonstrated in class as it is best suited for this type of dataset.

Optimization included the following:

1. Removing an additional column  (`STATUS`)and reducing the epochs - resulted in slightly higher accuracy.
1. Removing an additional column (`STATUS`) and increasing the epochs - resulted in slightly higher accuracy,  but lower than optimization option 1.
1. Removing an additional column (`STATUS`) and increasing the neurons - resulted in slightly higher accuracy, but lower than optimization option 1 and 2.
1. Removing an additional column (`STATUS`) and increasing the hidden layers as well as doing 50 epochs - since 50 epochs performed better than 100, this was used. However, we did not see significant increase.

***
# 3. Sumamry
In summary, further analysis would be needed to achieve higher accuracly results. It might be beneficial to perform an analysis that reduces the number of features or attempts to determine which features are the most important and run the model based on those features. There may be too much data that is irrelevant causing the accuracy and error to not be sufficient for this problem when doing a neural network model.