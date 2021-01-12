# Thinkful-Capstones-and-Projects
Capstone projects for Thinkful Data Science Flex Bootcamp - 2020

## Supervised Learning - Predicting the Temperatures of Superconductors
### Background
A superconductor is a material that has the ability to transmit electricity, i.e. maintain a current through it, without any resistance. This means that means an electric current can flow without any energy loss. However, this phenomenon only occurs at or below a certain temperature - the critical temperature ( Tc ) - for each material which is often a cryogenic temperature very close to absolute zero (0 Kelvin or -273.1 degrees C).

Superconductors have wide spread applications today and hold great promise for future technological advancement. Superconducting magnets are among the most powerful magnets developed today, as the sheer amount of resistance-free current that can be flowed through them is so high. These types of magnets are used in MRI machines, particle accelerators, and currently in the development of fusion reactors. Developing better superconductors holds a lot of promise, especially in the energy sector with regard to powerlines and the global effort to produce power via fusion.

 The goal of this analysis is to generate a supervised learning model that can predict the critical temperature of a semiconductor from its features.

### Data
The dataset is available publically on the UCI Machine Learning Repository and was used initially in a paper published in Computational Materials Science: https://archive.ics.uci.edu/ml/datasets/Superconductivty+Data/. It contains information about 21,263 known superconductors. 80 features are derived from their chemical formula plus the critical temperature, and their chemical formulas broken up element-wise into different columns.

### Methodology 
1. Used normalized (i.e. [0,1]) features and unaltered target (Tc)
2. Split into test & train targets and features (30%, 70%)
3. Create a baseline model with default hyperparameters
4. Optimize hyperparameters with Ax, the Adaptive Experimentation Platform, from Facebook
5. Run model with refined hyperparameters, compare key statistics
  * Linear Regression, Random Forest, KNN, SVN, and Gradient Boosting Regression models were used
### Results
Random Forest 
* RMSE: 9.80 
* Cross Val RMSE: 12.92 (+/- 9.65) 
* R² train, test: 0.97, 0.92 
* Cross Val Accuracy: 0.73 (+/- 0.20) 
* Runtime:0:00:13.331816
______________________________________________
Linear Regression 
* RMSE: 20.65 
* Cross Val RMSE: 21.06 (+/- 1.39) 
* R² train, test: 0.62, 0.64 
* Cross Val Accuracy: 0.62 (+/- 0.04) 
* Runtime:0:00:00.005457
______________________________________________
KNN 
* RMSE: 12.58 
* Cross Val RMSE: 14.51 (+/- 10.59) 
* R² train, test: 0.93, 0.89 
* Cross Val Accuracy: 0.66 (+/- 0.20) 
* Runtime:0:00:00.034901
______________________________________________
SVM Regression 
* RMSE: 15.99 
* Cross Val RMSE: 16.10 (+/- 11.90) 
* R² train, test: 0.77, 0.78 
* Cross Val Accuracy: 0.57 (+/- 0.26) 
* Runtime:0:00:52.956457
______________________________________________
Gradient Boosting 
* RMSE: 10.69 
* Cross Val RMSE: 13.23 (+/- 8.61) 
* R² train, test: 0.94, 0.90 
* Cross Val Accuracy: 0.71 (+/- 0.18) 
* Runtime:0:00:05.238682

### Results
Random Forest and Gradient Boosting are near ties, using minimal computer power, 13 and 5 seconds, respectively, to run the models. The paper cited above generated a model resulting in +/- 9.5K based on RSME (it's also interesting to note that this value is an average of 25 folds and no confidence interval was reported). These two models come very close to meeting that published benchmark; Random Forest coming the closest at +/- 9.8K using the same statistic. However, I believe Gradient Boosting to be the better model, using less computer power and having narrower confidence intervals for it's cross validation accuracies and root mean squares. 

### Future Work/ Goals
* Continue to work feature selection to remove any bias or variance of result statistics
* Investigate any new variables - interactions of multiple features or powers of existing features
* Other datasets to bring in that would help prediction
* Create  functions to automate running each type of model and stats printed each time

## Fashion MNIST - Deep Learning

Using the fashion MNIST dataset, this project works to optimize different ANN models by investigating:
1. Number of layers
2. Activation functions of layers
3. Number of neurons of layers
4. Different batch sizes during training

Best Model - 3 layers, Tanh Activation, 128 neurons/ layer, Mini Batch Size of 8
 Test Score: 0.8848999738693237
 Training Score:0.9212499856948853
