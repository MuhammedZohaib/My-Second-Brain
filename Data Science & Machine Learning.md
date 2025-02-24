# Data Science & Machine Learning

> ### Data Manipulation with Pandas

Pandas is built on top of two libraries, `numpy` and `matplotlib` . Pandas is designed to work with the rectangular data.

```python
import pandas as pd

data_frame = pd.DataFrame(some_data)
print(data_frame.head()) #Returns some top rows of the data
print(data_frame.info()) #Returns names and dataTypes of the columns
print(data_frame.shape) #Returns number of rows and columns as (rows, columns)
print(data_frame.describe()) #Returns satistics for some numerical data
print(data_frame.columns) #Returns names of columns
print(data_frame.index) #Returns names of rows
print(data_frame.values) #Returns values in 2D numpy array
data_frame.sort_values("column_name_here") #sort by column name

data_frame.sort_values("column_name_here", ascending = False)
data_frame.sort_values(["column_name_here","another_column"]) #sort by multiple columns

# Returns a single column name
data_frame["column_name"] 
#Subsetting multiple columns
data_frame[["column_name1", column_name2]]

data_frame["suppose_weight"] > 50 # Returns a list of Booleans
# Return rows where weight > 50
data_frame[data_frame["suppose_weight"] > 50]

weighs_50 = data_frame["suppose_weight"].isin([50])
data_frame[weighs_50]

data_frame["new_column_name"] = data_frame["old_column"] ___ #some operation
```

> There should be one – and preferably only one –obvious way to do it

### Summarizing Numerical Data :

```python
import pandas as pd

data_frame = pd.DataFrame("some_data")
data_frame["column_name"].mean() #Returns the central value of data
data_frame["column_name"].median()
data_frame["column_name"].mode()
data_frame["column_name"].min()
data_frame["column_name"].max()
data_frame["column_name"].var()
data_frame["column_name"].std()
data_frame["column_name"].sum()
data_frame["column_name"].quantile()
data_frame["column_name"].cumsum()
data_frame["column_name"].cummax()
data_frame["column_name"].cummin()
data_frame["column_name"].cumprod()
```

### Counting :

```python
data_frame.drop_duplicates(subset="column_name")
data_frame["col_name"].value_counts()
data_frame["col_name"].value_counts(sort = True)
data_frame["col_name"].value_counts(normalize = True)

data_frame.groupby("column_name or col_list")["single col or multi cols"].operation

data_frame.groupby("col_name")["col_name"].agg("single or multiple functions here")
```

### Pivot Tables :

```python
data_frame.pivot_table(values = "weight_col", index = "color_col", aggfunc = [])
data_frame.pivot_table(values = "weight_col", index = "color_col", aggfunc = [] columns = "", fill_value=0, margins= True)
```

### Explicit Indexes :

```python
data_frame.set_index("col_name") #single index
# below the column 2 is nested in the column 1 index
data_frame.set_index(["col_name1", "col_name2"]) #multi-level indexes
data_frame.reset_index() #will reset the index column
data_frame.reset_index(drop = True) #will remove the index column
data_frame.loc() #filters or subset on the index value

# by default sort values from outer index to inner index
data_frame.sort_index() 
data_frame.sort_index(level=["col1", "col2"], ascending=[True, False]) 


# To subset the multi-level indexes we need to pass tuples in the loc function
data_frame.loc(["subset 1", "subset 2"]) #filters or subset on the index value
```

### Slicing and Sub-setting :

```python
# The starting index is 0 and ending index is not included in case of lists but
# in case of datasets it is included
data_frame.loc[start_index:end_idex]
# sort the indexes before you slice 

# slicing outer index
data_frame.loc[start:end]
# we cannot slice on basis of inner index just like outer index
data_frame.loc[(index1_start, index2_start):(index1_end, index2_end)]

# Since dataframes are two dimesnsional we can slice columns along with indexes
data_frame.loc[(row_start,row_end):(start_col,end_col)]

# similar as loc
data_frame.iloc[row_int:row_int_end, col_int:col_int_end]

data_frame.mean(axis="col_name")
```

### Missing Values :

```python
# check for missing values
data_frame.isna()
data_frame.isna().any()
data_frame.isna().sum()

data_frame.dropna()
data_frame.fillna(0)
```

### Dictionaries :

Set of key value pairs

```python
my_dict = {
  "KEY" : VALUE
}
my_dict["KEY"] #Returns VALUE
```

### Creating Data Frames :

- From a List of Dictionaries (row by row)
- From a Dictionaries of Lists (column by column)

```python
my_dict = {
  "col_1" : [val1, val2],
  "col_2" : [val1, val2]
}
my_dict = [ 
  {"col_1" : val1, col_2: val1 },
  {"col_1" : val2, col_2: val2 },
]

data_frame = pandas.DataFrame(my_dict)
```

### Reading and Writing `CSVs` :

```python
import pandas as pd

data_frame = pd.read_csv("filename.csv")
data_frame.to_csv("new_csv_filename.csv")
```

### Joining Data with Pandas :

```python
#Inner Join
# return rows of both tables which matches the key column
data_frame_new = df1.merge(df2, on='col')
data_frame_new = df1.merge(df2, on='col',  suffixes='_overlap_col')

# one to one relationship = every row in the left table is related to only one row
# in the right table
# one to many relationship = every row in the left table is related to one or more
# rows in the right table

# merging multiple dataframes
ridership_cal_stations = ridership.merge(cal, on=['year','month','day']) \
            				.merge(stations, on="station_name")

# Left Join : returns all the rows of left table and only rows of right table which
# matches the key column value
data_frame_new = df1.merge(df2, on='col', how="left")
# there are also other joins as:
  # right, outer, self
```

---

> ### Machine Learning with Sci-kit Learn

```python
# deciding wether a email is spam or not
# assigining categories to the books
# There are two types of supervised learning : classification and regression
# conditions for supervised learning 
# - no missing values
# - data should be in numeric format
# - data should be stored as pandas dataframe or numpy array

# basic syntax for scikit-learn
from sklearn.module import Model
model = Model()
model.fit(X,y) # X = features, y = target value
predictions = model.predict(X_new)
```

### k-Nearest Neighbors :

```python
# popular for classification problems
from sklearn.neighbors import KNeighborsClassifier
X = feautures.values
y = target_value.values
# using the .values method will convert the columns to numpy arrays
knn = KNeighborsClassifier(n_neighbors=15)
knn.fit(X, y)
predictions = knn.predict(X_new)

# example exercise from datacamp
# Import KNeighborsClassifier
from sklearn.neighbors import KNeighborsClassifier

# Create arrays for the features and the target variable
y = churn_df["churn"].values
X = churn_df[["account_length", "customer_service_calls"]].values

# Create a KNN classifier with 6 neighbors
knn = KNeighborsClassifier(n_neighbors = 6)

# Fit the classifier to the data
knn.fit(X, y)
# Predict the labels for the X_new
y_pred = knn.predict(X_new)

# Print the predictions for X_new
print("Predictions: {}".format(y_pred))
```

### Measuring Model Performance :

```python
# In classification accuracy is commonly used metric
# number of correct predictions / total obervations
# splitting dataset into training and evaluating data

# to check the accuracy
print(knn.score(X_test, y_test)) # 0 - 100%

# model complexity and over/underfitting
train_accuracies = {}
test_accuracies = {}
neighbors = np.arange(1, 26)

for neighbor in neighbours:
  knn = KNeighborsClassifier(n_neighbours=neighbour)
  knn.fit(X_train, y_train)
  train_accuracies[neighbour] = knn.score(X_train, y_train)
  test_accuracies[neighbour] = knn.score(X_test, y_test)

plt.figure(figsize = (8,6))
plt.title("KNN: Varying number of neighbors")
plt.plot(neighbors, train_accuracies.values(), label="Training Accuracy")
plt.plot(neighbors, test_accuracies.values(), label="Testing Accuracy")
plt.legend()
plt.xlabel("Number of Neighbors")
plt.ylabel("Accuracy")
plt.show()
```

### Regression :

```python
# In classification the values are binary but in regression the values are continuous
# if the feature is only one then it is known as linear regression 
# e.g. y = ax + b # a is the feature where y is target
# In case of mulitple features equation becomes y = a1x1 + a2x2 + b
# here a and b are the features which we want our model to learn but how do we choose
# these fetures? it is simple by defining an error function and picking the features
# which shows the lowest value of the error
# the linear regression under the hood is Ordinary least squares (OLS) in scikit learn
from sklearn.linear_model import LinearRegression
reg = LinearRegression()
reg.fit(X, y)
predictions = reg.predict(X_new)

# to compute the R^2 of the model we call the .score method
reg.score(X_test, y_test)
# another way to predict model accuracy is to compute Root mean squared error
from sklearn.metrics import mean_squared_error
err = mean_squared_error(y_test, y_pred, squared=False)

# Example:
# Import mean_squared_error
from sklearn.metrics import mean_squared_error
# Compute R-squared
r_squared = reg.score(X_test, y_test)
# Compute RMSE
rmse = mean_squared_error(y_test, y_pred, squared=False)
```

### Cross Validation :

```python
# To test our data on the unseen data we use split our dataset into 5 flods
# and we skip the first fold and use all other folds to predict the required metric
# or R^2 or RMSE then we skip the second fold and do the same and so on
# in this way we can find and evaluate our model's different metrics
# if  we split our data in 5 folds it is known as 5-fold CV if k folds then
# it is known as k-folds CV but here is a catch, the greater the number of folds
# the more it is computationally expensive

from sklearn.model_selection import cross_val, KFold
kf = KFold(n_splits=6, shuffle=True, random_state=3) #n_splits has a def value 5
reg = LinearRegression()
cv_results = cross_val(reg, X, y, cv=kf)

# Print the mean
print(np.mean(cv_results))
# Print the standard deviation
print(np.std(cv_results))
# Print the 95% confidence interval
print(np.quantile(cv_results, [0.025, 0.975]))
```

### Regularized Regression :

```python
# Regularization is the technique to avoid over-fitting 
# The large values in the data can over-fit our model so we need to regularize
# our data-set
# Techniques for regularization
# - Ridge Regression
# In the ridge regression we have an alpha variable which we need to choose it
# is just like picking k in knn. alpha controls the complexity of the model. if
# alpha is equal to 0 it means it can lead to overfitting and if it is very high
# it means it can lead to underfitting

from sklearn.linear_model import Ridge
# picking values of alpha:
scores = []
for alpha in [0.1, 1.0, 10.0, 100.0, 1000.0]:
  ridge = Ridge(aplha=alpha)
  ridge.fit(X_train, y_train)
  y_pred = ridge.predict(X_test)
  scores.append(ridge.score(X_test, y_test))

# There is another regularized regression known as lasso regression
from skelearn.linear_model import Lasso
scores = []
for alpha in [0.1, 1.0, 10.0, 100.0, 1000.0]:
  lasso = Lasso(aplha=alpha)
  lasso.fit(X_train, y_train)
  y_pred = lasso.predict(X_test)
  scores.append(lasso.score(X_test, y_test))

# lasso reg can be used to select important features of the dataset as
# the co-efficients of less imp features are shrunk to 0
from skelearn.linear_model import Lasso
X = data_set.drop("target_col", axis=1).values
y = data_set["target_col"].values
names = data_set.drop("target_col, axis=1").columns
lasso = Lasso(alpha=0.1)
lasso_coef = lasso.fit(X, y).coef_
plt.bar(names, lasso_coef)
plt.xticks(rotation=45)
plt.show()
```

### Model Performance :

```python
# Suppose we have class imbalance in our data where target value has one value 
# very large we cannot predict it by accuracy so we need another metric, so to
# evaluate the mertics we can use the confusion matrix
# many other metrics can also be calculated from the precision matrix such as:
# - precision, accuracy, recall/senstivity, F1 score

from sklearn.metrics import classification_report, confusion_matrix
knn = KNeighborsClassifier(n_neighbors=7)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.4, random_state = 21, stratify=y)
knn.fit(X_train, y_train)
y_pred = knn.predict(X_test)

print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
```

### Logistic Regression and ROC curve :

```python
# Logistic Regression is used for binary classification
from sklearn.linear_model import LogisticRegression
logreg = LogisticRegression()
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.4, random_state = 21, stratify=y)
logreg.fit(X_train, y_train)
y_pred = logreg.predict(X_test)
y_pred_probs = logreg.predict_proba(X_test)[:,1]

# plotting the ROC curve
from sklearn.metrics import roc_curve
fpr, tpr, thresholds = roc_curve(y_test, y_pred_probs)
plt.plot([0,1], [0, 1], 'k--')
plt.plot(fpr, tpr)
plt.xlabel("Flase positive Rate")
plt.ylabel("True positive Rate")
plt.title("Logistic Regression ROC curve")
plt.show()

# calculating auc_score
from sklearn.metrics import roc_auc_score
print(roc_auc_score(y_test, y_pred_probs))
```

### Hyperparameter tuning :

```python
# We have evaluated our model performance but now lets enhance the or optimize
# model performance
# The parameters which we specify before fitting our model are known as 
# hyper-parameters, a fundamental step for building a correct model is choosing
# the correct hyper-parameters

# try lots of different values, fit all of them separately, see how the perform
# choose the best performing value, it is also essential to use cross-validation
# to avoid overfitting

# GridSearchCV in scikit learn
from sklearn.model_selection import GridSearchCV
kf = KFolds(n_splits=5, shuffule=True, random_state=3)
param_grid = {alpha: np.arange(0.0001, 1, 10), 
              solver: ["sag", "lsqr"]}
ridge = Ridge()
ridge_cv = GridSearchCV(ridge, param_grid, cv=kf)
ridge_cv.fit(X_train, y_train)

print(ridge_cv.best_params_, ridge_cv.best_score_)

# RandomizedSearchCV in scikit learn
from sklearn.model_selection RandomizedSearchCV
kf = KFolds(n_splits=5, shuffule=True, random_state=3)
param_grid = {alpha: np.arange(0.0001, 1, 10), 
              solver: ["sag", "lsqr"]}
ridge = Ridge()
ridge_cv = RandomizedSearchCV(ridge, param_grid, cv=kf, n_iter=2)
ridge_cv.fit(X_train, y_train)

print(ridge_cv.best_params_, ridge_cv.best_score_)
```

### Preprocessing and Pipelines :

```python
# As we earlier saw that for scikit learn to work our data should be numeric and
# there should be no missing values, but in reality that is not much applicable
# so we need preprocessing on our dataset.
# Dealing with categorical features in dataset we can use OneHotEncoder 
# or pandas get_dummies method of scikit learn 

import pandas as pd
data_frame = pd.read_csv("data.csv")
music_dummies = pd.get_dummies(m=data_frame["col_to_encode"], drop_first=True)
# once we have encoded the column we need to bring the encoded column back into
# our dataset so
music_dummies = pd.concat([data_frame, music_dummies], axis=1)
# removing the original column which we encoded
music_dummies = music_dummies.drop("col_to_drop", axis=1)
```

### Handline Missing Data :

```python
print(dataframe.isna().sum.sort_values())
# drop the missing rows if the missing values are less than 5% of data
dataframe.drop(subset["col1", "col2"])
# Another approach is to fill the missing value with some sort of guessed value
# this is known as imputing
from sklearn.impute import SimpleImputer
```

![image.png](https://res.craft.do/user/full/f135b8cc-098b-e494-da0c-42c7dacc3eae/doc/7eacd8ef-52b7-4436-90f6-346b9d9964f9/efe80e39-7b44-4c27-b67a-3435a5927f3f)

```python
from sklearn.pipeline import Pipeline

# Create steps
steps = [("imp_mean", SimpleImputer()), 
         ("scaler", StandardScaler()), 
         ("logreg", LogisticRegression())]

# Set up pipeline
pipeline = Pipeline(steps)
params = {"logreg__solver": ["newton-cg", "saga", "lbfgs"],
         "logreg__C": np.linspace(0.001, 1.0, 10)}

# Create the GridSearchCV object
tuning = GridSearchCV(pipeline, param_grid=params)
tuning.fit(X_train, y_train)
y_pred = tuning.predict(X_test)

# Compute and print performance
print("Tuned Logistic Regression Parameters: {}, Accuracy: {}".format(tuning.best_params_, tuning.score(X_test, y_test)))
```

### Centering and Scaling :

```python
# subtract the mean and divide by variance -> standardization
# subtract minimum and divide by the range of data
# normalize data so it ranges between -1 and 1

from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

### Evaluating Multiple Models :

```python
# as there are so many models so how do we decide to pick up a model?
# Guidelines:
# size of dataset 
  # fewer features
  # some models require large amount of data

# Regression Model Evaluation:
  # RMSE
  # R-squared
# Classification
  # Accuracy
  # Confusion Matrix
  # Precision, Recall, F1
  # ROC, AUC

# Model affected by scaling
  # KNN
  # Linear_Regression -> Ridge, Lasso
  # Logistic Regression
  # Artificail Neural Network

models = {"Linear Regression": LinearRegression(), "Ridge": Ridge(alpha=0.1), "Lasso": Lasso(alpha=0.1)}
results = []
# Loop through the models' values
for model in models.values():
  kf = KFold(n_splits=6, random_state=42, shuffle=True)
  # Perform cross-validation
  cv_scores = cross_val_score(model, X_train, y_train, cv=kf)
  # Append the results
  results.append(cv_scores)

# Create a box plot of the results
plt.boxplot(results, labels=models.keys())
plt.show()
```

---

> ### Statistics in Python

Statistics : The practice and study of collecting and analyzing data

Summary Statistics : fact about or summary of some data

There are two main branches of statistics:

- Descriptive Statistics : Describing and summarizing the data at hand
- Inferential Statistics : Use sample data to make inferences about larger population of data

There are two main types of data:

- Numeric (Quantitative Data)
   - Continuous (Measured)
   - Discrete (Counted)
- Categorical (Qualitative Data)

#### Measures of Center :

- Mean (average) → add all data and divide by total instances
- Median → the middle value in the sorted data where 50% lower and 50% higher values
- Mode → Mode is the most frequent value in the data

```python
# mean 
# mean is senstive to extreme values, use for symmertrical data
import numpy as np
np.mean()
# median
# use median when data is not symmeterical
np.median()
# mode
import statistics
statistics.mode()
```

#### Measures of Spread :

- Variance → average distance of each data point to the data's mean

```python
# The higher the variance is the higher is the spread of the data
import numpy as np
np.var('column_name', ddof=1) # ddof=1 is used on sample data
```

- Standard Deviation  → calculated by taking square root of the variance

```python
np.std('column', ddof=1)
```

- Quantiles → also called percentiles, split up data into some equal number of parts

```python
np.quantile('column', 0.5)
np.linspace('start', 'stop', 'interval')
```

- Interquartile Range

```python
from scipy.stats import iqr
iqr('column')

np.quantile('column', 0.75) - np.quantile('column', 0.25)
```

- Outliers → data points which is substantially different from the others

```python
# data < Q1 - 1.5 * IQR
# data > Q3 + 1.5 * IQR
```

- Probability

```python
# Probability(E) = # of ways an event can happen / total outcomes
# if the event has a probability of 0 then it will never happen however if the
# event has a probability of 100% then it certainly will happen.

# picking a random sample
data_frame.sample()
# to get a same result everytime
np.random.seed("value here")
data_frame.sample()
# independance
# two events are said to be indepandant if the probability of second event isn't
# affeceted by the first event
# in general there are two types of the probabilities:
# with replacement and without replacement
```

- Discrete Distribution

```python
Describe the distribution of each possible outcome in a scenario
e.g. rolling a dice 
what are chances of 1 to be rolled.
1 * 1/6

Can be used for discrete values such as countable values

Law of large numbers: As the size of the sample increase the mean will approach
the expected value.
```

- Continuous Distribution

```python
from scipy.stats import uniform
uniform.cdf(7, 0, 12) //continuous distribution fucntion(at value, lower, higher)

uniform.rvs(0,5,size=10) //generate 10 random distributions betweem 0 and 5

# Min and max wait times for back-up that happens every 30 min
min_time = 0
max_time = 30

# Import uniform from scipy.stats
from scipy.stats import uniform

# Calculate probability of waiting 10-20 mins
prob_between_10_and_20 = uniform.cdf(20, min_time, max_time) - uniform.cdf(10, min_time, max_time)
print(prob_between_10_and_20)
```

- Binomial Distribution

```python
# Distribution used where the outcome is binary such as flipping a coin we get 
# either heads or tails.

from scipy.stats import binom

binom.rvs(number of coins, porbability of heads/tail, size=number of trials)
binom.pmf(num of heads, num trials, prob. of heads)
```

- Normal Distribution

```python
# Defined by mean and standard deviation

from scipy.stats import norm
norm.cdf(number of interest, mean, stand. deviation)
norm.ppf(percentage, mean, stand. deviation)
norm.rvs(mean, stand. deviation, size=num)
```

- Central limit Theorem

```python
# A sampling distribution of statistic becomes closer to the normal distribution
# as the number of trials increases.
```

- Poisson distribution

```python
"""
Poisson process: Events appear to happen at a certain rate, but completely at
random.
Poisson distribution is represented by a lambda.
Average number of events per time interval
"""
from scipy.stats import poisson
poisson.pmf(5,8)
poisson.cdf(5,8)
poisson.rvs(8, size=10) # for sampling
```

- Exponential Distribution

```python
from scipy.stats import expon
expon.cdf(1, scale=num)
```

- T Distribution

```python
"""Also known as Student's T Distribution
in T distribution observations are more likely to fall further from the mean
effected by degree of freedom
low df = thicker tails, higher std
"""
```

- Log-normal Distribution

```python
# Variables whose log is normally distributed
# Results in skewed distributions
```

### Correlation:

Relationship between variables. Can be visualized using scatter plots.

Explanatory or independant variable is on x-axis

Response or dependent variable is on y-axis. The value of correlation ranges between -1 and 1. The sign shows the direction of the relationship. Positive sign shows direct proportionality while the Negative sign shows inverse proportionality. If the correlation between two variables is close to 1 then it means they have strong relationship.

```python
import seaborn as sns
sns.scatterplot(x="independant_var", y="dependant_var", data=data_frame)
plt.show()

# adding a linear trendline to scatter plot
sns.lmplot(x="independant_var", y="dependant_var", data=data_frame, ci="None")
# ci="None" removes any confident interval patterns along the line

#finding correlation between to variables of a series
data_frame1['var1'].corr(data_frame1['var2']) 
# above is pearson product-moment correlation
# note: The order of these variables does not matter in correlation

"""
formula for pearson product-moment correlation:
r = (x1 - mean x) + .... (xn - mean x) * (y1 - mean y) + .... (yn - mean y) 
        / std x * std y
"""

# Variations in the formula:
# Kendall's tau
# Spearmans rho
```

### Correlation Caveats:

correlation measure only linear relationship between two variables. Always visualize your data before finding the correlations between two variables to make sure that they have a linear relationship. sometimes when we visualize the data we may find that the distribution of the data is not linear rather it is skewed, in such cases we can add a new column by using log transformation. Other than that we can also use square root transformation or reciprocal transformation. These transformation can be applied on data in different combinations.

such as: `log x` `log y`

`sqrt x` `reciprocal y`

Why do we need transformations?

Many statistical methods require variables which have a linear relationship such as correlation, Linear regression.

Correlation does not imply causation: if `x` and `y` are correlated it does not mean `x` causes `y` . Sometimes there exist a strong correlation between two variables due to a third confounding variable.

### Design of Experiment:

   Treatment : explanatory / independent variable

   Response : response / dependant variable

   fewer opportunities for bias = more reliable conclusion about causation

---

> ### **Matplotlib**

```python
import matplotlib.pyplot as plt
fig, ax = plt.subplots()

ax.plot(x,y)
plt.show()

# adding a marker to the plot'
# visit https://matplotlib.org/stable/api/markers_api.html'
ax.plot(x, y, marker="o")

# changing the linestyle
ax.plot(x, y, marker="o", linestyle="--")
# visit: https://matplotlib.org/stable/gallery/lines_bars_and_markers/linestyles.html

# changing the line color
ax.plot(x, y, marker="o", linestyle="--", color = 'r')
# setting the plot labels
ax.set_xlabel("This is x label")
ax.set_ylabel("This is y label")
ax.set_title("This is the title")

# small multiples
fig, ax = plt.subplots(3,2)
# this will return an array of subplots which can be indexed for plotting
# this will insure the range on y-axis is same in all subplots
fig, ax = plt.subplots(3,2)
```

### Plotting Time Series Data

```python
fig, ax = plt.subplots()
ax.plot(df.index, df['col'])
ax.set_xlabel("This is x-label")
ax.set_ylabel("This is y-label")
# Using different y-axis
ax2 = ax.twinx()
ax2.plot(df.index, df['col_1']) # different y-axis but same x-axis
ax2.set_ylabel("This is y-label for 2nd plot")
plt.show()

# we can give color to the plots as well as the labels and ticks
ax.tick_params('either x or y', color='color_name')
```

### Adding Annotations

```python
ax.annotate("annotation text", xy=(pd.TimeStamp("yyyy-mm-dd"), 1))

# moving the annotation:
ax.annotate("annotation text", xy=(pd.TimeStamp("yyyy-mm-dd"), 1), xytext=(pd.Timestamp("yyyy-mm-dd"), -0.2))

# adding arrow to connect the annotation and plot point
ax2.annotate(">1 degree", xy=(pd.Timestamp("yyyy-mm-dd"), 1), 
            xytext=(pd.Timestamp("yyyy-mm-dd"), -0.2),
             arrowprops={"arrowstyle": "->", "color":"gray"})
```

### Bar Charts

```python
# simple bar chat
fig, ax = plt.subplots()
ax.bar(x, y)
plt.show()

# rotating the x-tick labels by 90 degree
ax.set_xticklabels(column, rotation=90)

# creating a stacked bar-chart
ax.bar(x1, y)
ax.bar(x2, y, bottom=x1)
ax.bar(x3, y, bottom=x1+x2)

# adding legends
ax.legend()

# showing plot
ax.show()
```

### Histograms

```python
fig, ax = plt.sublplots()
ax.hist(dataframe['column'])
plt.show()

ax.hist(dataframe['column'], label="label for this histogram", bins="number of bins")
# we can also provide a list of bins in bins parameter
ax.hist(dataframe['column'], bins=[20, 40, 60, 80, 100])

# sometimes if we plot multiple variables in a single plot our plot can be
# overlapping so we can change the histogram type so it can be hollow and
# visible
ax.hist(dataframe['column'], bins=[20, 40, 60, 80, 100], histtype="Step")
```

### Statistical Plotting

```python
# Error Plot -- 1
fig, ax = plt.subplots()

ax.bar("Rowing", mens_rowing['Height'].mean(), yerr=mens_rowing['Height'].std())
ax.bar("Gymnastics", mens_gymnastics['Height'].mean(), yerr=mens_gymnastics['Height'].std())
ax.set_ylabel("Height (cm)")
plt.show()

# Error Plot -- 2
fig, ax = plt.subplots()
ax.errorbar(seattle_weather['MONTH'], seattle_weather['MLY-TAVG-NORMAL'], yerr=seattle_weather['MLY-TAVG-STDDEV'])
ax.errorbar(austin_weather['MONTH'], austin_weather['MLY-TAVG-NORMAL'], yerr=austin_weather['MLY-TAVG-STDDEV'])
ax.set_ylabel("Temperature (Fahrenheit)")
plt.show()

# Error Plot -- 3 (Box Plot)
fig, ax = plt.subplots()
ax.boxplot([mens_rowing['Height'], mens_gymnastics['Height']])
ax.set_xticklabels(["Rowing", "Gymnastics"])
ax.set_ylabel("Height (cm)")
plt.show()
```

### Scatter Plot

```python
fig, ax = plt.subplots()
ax.scatter(climate_change['co2'], climate_change['relative_temp'])
ax.set_xlabel("CO2 (ppm)")
ax.set_ylabel("Relative temperature (C)")
plt.show()

# giving time index to scatter plot as c param
fig, ax = plt.subplots()
ax.scatter(climate_change['co2'], climate_change['relative_temp'], c=climate_change.index)
ax.set_xlabel("CO2 (ppm)")
ax.set_ylabel("Relative temperature (C)")
plt.show()
```

### Changing Plot Style in Matplotlib

```python
plt.style.use("ggplot")
plt.style.use("default")
plt.style.use("bmh")
plt.style.use("seaborn-colorblind")
plt.style.use("tableau-colorblind10")
plt.style.use("grayscale")
plt.style.use("Solarize_Light2")
```

### Saving Matplotlib Plots

```python
fig.savefig("Name_of_plot.png")
fig.savefig("Name_of_plot.jpg")
fig.savefig("Name_of_plot.jpg", quality=50) # 50% quality
fig.savefig("Name_of_plot.svg")
fig.savefig("Name_of_plot.png", dpi=300)

# controlling the size of the figure
fig.set_size_inches([5,3]) # [width, height]


# plot pipeline example:
fig, ax = plt.subplots()
for sport in sports:
  sport_df = summer_2016_medals[summer_2016_medals['Sport'] == sport]
  ax.bar(sport, sport_df["Weight"].mean(), yerr=sport_df["Weight"].std())

ax.set_ylabel("Weight")
ax.set_xticklabels(sports, rotation=90)
fig.savefig("sports_weights.png")
```

---

> ### **Seaborn**

```python
# Data Visualization Library
# Based on Pandas and Matplotlib
# Samuel Norman Seaborn (sns)
import seaborn as sns

sns.countplot() # either specify x or y axis
sns.scatterplot()

# load dataset with seaborn
sns.load_dataset("path to csv file")

# adding a third parameter to the plot using hue parameter
hue_colors = {"Yes": "black",
              "No": "red"} # we can also use hex code for colors
sns.scatter(x="column_name", y="column_name", data="pandas dataframe"
           hue="third_column_name", hue_order=["label", "label"],
           palette=hue_colors)
```

### Relation Plots and Subplots

```python
# for relational plots we have been using scatter plots but we
# can also use relplot in place of it

sns.relplot(x="column_name", y="column_name", data=data_frame, kind="scatter")
# adding a third column but using relplot
sns.relplot(x="column_name", y="column_name", data=data_frame, kind="scatter",
           col="third_column")
sns.relplot(x="column_name", y="column_name", data=data_frame, kind="scatter",
           row="third_column")
# specifying number of plots per row
sns.relplot(x="column_name", y="column_name", data=data_frame, kind="scatter",
           row="third_column", col_wrap=2, col_order["Val_1", "Val_2"])
```

### Size and Style Parameter

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.relplot(x="column_name", y="column_name", data=date_frame, kind="scatter",
           hue="column_name", style="column_name", alpha="value between 0 and 1")
```

### Line Plots in Seaborn

```python
sns.relplot(x="column_name", y="column_name", data=data_frame, kind="line",
           dashes=False, markers=True)
# confidence interval
sns.relplot(x="column_name", y="column_name", data=data_frame, kind="line",
           ci="sd")
# Example
import matplotlib.pyplot as plt
import seaborn as sns
sns.relplot(x="model_year", y="horsepower", 
            data=mpg, kind="line", 
            ci=None, style="origin", 
            hue="origin", markers=True, dashes=False)
plt.show()
```

### Count Plots and Bar Plots

```python
# These are type of categorical plots we use catplot() function

# plotting countplot using catplot
sns.catplot(x="col_name", data=df, kind="count")

# specifying the order of category
# make a list
category_order = ["val_1", "val_2", "val_3", "val_4"]
sns.catplot(x="col_name", data=df, kind="count", order=category_order)

# plotting bar plot
sns.catplot(x="col_name", data=df, kind="bar")
# turning confidence intervals off
sns.catplot(x="col_name", data=df, kind="bar", ci=None)

"""
Example
"""
category_order = ["<2 hours", 
                  "2 to 5 hours", 
                  "5 to 10 hours", 
                  ">10 hours"]
sns.catplot(x="study_time", y="G3",
            data=student_data,
            kind="bar",
            order=category_order, ci=None)
plt.show()
```

### Box Plots using Seaborn

```python
# shows distribution of quantitative data
# box plots shows us median, spread, skewness and outliers in the data
g = sns.catplot(x="col", y="col", data=df, kind=box)
# box plot also has order parameter which can change the order of data in plot
# we can also remove outliers from the plot using sym variable
# if we pass empty string "" it will remove the outliers else it can also be use
# to change the appearance of the outliers

# IQR is the 25th to 75th percentile of ditribution of the data 
# any data that is 1.5 * IQR is considered outlier
g = sns.catplot(x="col", y="col", data=df, kind=box, sym="")

#Changing the whiskers
sns.catplot(x="col", y="col", data=df, kind=box, sym="", whis=2.0) # 2.0 * IQR
sns.catplot(x="col", y="col", data=df, kind=box, sym="", whis=[5, 95])
sns.catplot(x="col", y="col", data=df, kind=box, sym="", whis=[0, 100])
```

### Points Plot

```python
# another categorical plot which only plots the mean of categories using points
sns.catplot(x="col_name", y="col_name", data=df, hue="col_name", kind="point")
# removing the joins between the points
sns.catplot(x="col_name", y="col_name", data=df, hue="col_name", kind="point",
           join=False)
# changing the estimator from mean to median, we usually do this because median
  # is more robust to outliers, use it incase the data has a lot of outliers
from numpy import median
sns.catplot(x="col_name", y="col_name", data=df, kind="point", estimator=median)

# adding caps at the end of confidence intervals
sns.catplot(x="col_name", y="col_name", data=df, kind="point", capsize=0.2)

# similary confidence interval can be turned off using ci=None
```

### Customizing Seaborn Plots

```python
# Seaborn has five 5 preset figures
"""
white, dark, whitegrid, darkgrid, ticks
"""
# changing global styling of the seaborn plots
sns.use_style()

# changing the seaborn color palletes
"""
Diverging Palletes
RdBu, PRGn, RdBu_r, PRGn_r
Sequential Palletes
Greys, Blues, PuRd, GnBu
"""
# changing global pallete
sns.set_pallete()
# we can also pass custom palletes using a list with names or hex codes.

# changing the scale of the plot
"""
paper, notebook, talk, poster
"""
sns.set_context()

# adding titles and ticks
# assign the plot to a variable, mostly assigned as g
g = sns.catplot() # returns Faceit Grid
g = sns.replot()  # returns Faceit Grid
g = sns.scatterplot() # returns AxesSubplot
g = sns.countplot() # returns AxesSubplot

# adding title to seaborn plot in case of Faceit Grid
g.fig.suptitle("New Title")
g.fig.suptitle("New Title", y=1.05) # it will make the title a little higher
# adding title to seaborn plot in case of AxesSubplot
g.set_title("New Title", y=1.05)

# when we create subplots
g.fig.suptitle("New Title", y=1.03)
g.set_titles("This is {col_name}")

# setting x and y labels in the plot
g.set(xlabel="New X label", ylabel="New Y label")
# for chaning the ticks to 90 degree we use matplotlib function
plt.xticks(rotation=90)
```

---

# Unsupervised Learning

Measuring clustering quality

- using only samples and their cluster labels
- a good clustering has tight clusters
- samples in each cluster bunched together

we can measure the clustering quality by finding the inertia basically inertia is measure of how close the cluster are the lower the inertia the better

```python
from sklearn.cluster import KMeans
model = KMeans(n_clusters=3)
model.fit(samples)
print(model.inertia_)
```

```python
import pandas as pd
df = pd.DataFrame({'labels': labels, 'species': species})
    ct = pd.crosstab(df['labels'], df['species'])
```

## Use Standard Scaler for feature Transformation

```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
scaler.fit(samples)
StandardScaler(copy=True, with_mean=True, with_std=True)
samples_scaled = scaler.trasnform(samples)
```

- other than Standard Scaler we also have `MaxAbsScaler` and `Normalizer`

## Creating a simple pipeline

```python
from sklearn.preprocessing import StandarcScaler
from sklearn.cluster import KMeans

scaler = StandarcScaler()
kmeans = KMeans(n_clusters=3)

from sklearn.pipeline import make_pipeline
pipeline = make_pipeline(scaler, kmeans)
pipeline.fit(samples)
labels = pipeline.predict(samples)
```

## Visualizing hierarchies

Two unsupervised Learning techniques for visualization:

- t-SNE
- hierarchical clustering

In hierarchical clustering a tree like diagram called a dendrogram is formed, at the start there are as many clusters as there are data points but in the end there is only cluster is left this type of clustering is particularly known as agglomerative clustering. and there is also divisive clustering which is totally opposite.

```python
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import linkage, dendrogram
mergings = linkage(samples, method='complete')
dendrogram(mergings,
          labels=country_names,
          leaf_rotation=90,
          leaf_font_size=6)
plt.show()
```

### intermediate clustering

```python
from scipy.cluster.heirarchy import linkage, fcluster
mergings = linkage(samples, method='complete')
labels = fcluster(mergings, 15, criterion='distance')
print(labels)

import pandas as pd
pairs = pd.DataFrame({'labels':labels, 'countries': country_names})
print(pairs.sort_values('labels'))
```

### t-SNE for 2-dimensional maps

t-SNE stands for t-distributed stochastic neighbor embedding has a very simple job and that is to map samples to 2D space or 3D. It also preserves the nearness of samples.

```python
import matplotlib.pyplot plt
from sklearn.manifold import TSNE
model =  TSNE(learning_rate=100)
transformed = model.fit_transform(samples)
xs =  transformed[:, 0]
ys = transformed[:, 1]
plt.scatter(xs, ys, c=species)
plt.show()
```

## Dimension Reduction

- PCA (Principal Component Analysis) → fundamental dimension reduction technique

```python
from sklearn.decomposition import PCA
model = PCA()
model.fit(samples)
transformed = model.transform(samples)

features = range(model.n_components_)
plt.bar(features, model.explained_variance_)
plt.xticks(features)
plt.ylabel('variance')
plt.xlabel('PCA feature')
plt.show()
```

intrinsic dimension =  number of features needed to approximate the dataset

dimension reduction = representing same data with less features

NMF =  non-negative matrix factorization

Like PCA, NMF is also a dimension reduction technique. it cannot be applied to every dataset it requires data to be non-negative. NMF expresses the document as combinations of topics and images as combinations of patterns

```python
from sklearn.decomposition import NMF
model = NMF(n_components=2)
model.fit(samples)
print(model.components_)
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Data+Science+&+Machine+Learning.md&fileType=undefined&fileExtension=md