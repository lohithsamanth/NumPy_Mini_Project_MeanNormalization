
# Mean Normalization

In machine learning we use large amounts of data to train our models. Some machine learning algorithms may require that the data is *normalized* in order to work correctly. The idea of normalization, also known as *feature scaling*, is to ensure that all the data is on a similar scale, *i.e.* that all the data takes on a similar range of values. For example, we might have a dataset that has values between 0 and 5,000. By normalizing the data we can make the range of values be between 0 and 1.

In this lab, you will be performing a different kind of feature scaling known as *mean normalization*. Mean normalization will scale the data, but instead of making the values be between 0 and 1, it will distribute the values evenly in some small interval around zero. For example, if we have a dataset that has values between 0 and 5,000, after mean normalization the range of values will be distributed in some small range around 0, for example between -3 to 3. Because the range of values are distributed evenly around zero, this guarantees that the average (mean) of all elements will be zero. Therefore, when you perform *mean normalization* your data will not only be scaled but it will also have an average of zero. 

# To Do:

You will start by importing NumPy and creating a rank 2 ndarray of random integers between 0 and 5,000 (inclusive) with 1000 rows and 20 columns. This array will simulate a dataset with a wide range of values. Fill in the code below



Now that you created the array we will mean normalize it. We will perform mean normalization using the following equation:

$\mbox{Norm_Col}_i = \frac{\mbox{Col}_i - \mu_i}{\sigma_i}$

where $\mbox{Col}_i$ is the $i$th column of $X$, $\mu_i$ is average of the values in the $i$th column of $X$, and $\sigma_i$ is the standard deviation of the values in the $i$th column of $X$. In other words, mean normalization is performed by subtracting from each column of $X$ the average of its values, and then by dividing by the standard deviation of its values. In the space below, you will first calculate the average and standard deviation of each column of $X$. 



# Data Separation

After the data has been mean normalized, it is customary in machine learnig to split our dataset into three sets:

1. A Training Set
2. A Cross Validation Set
3. A Test Set

The dataset is usually divided such that the Training Set contains 60% of the data, the Cross Validation Set contains 20% of the data, and the Test Set contains 20% of the data. 

In this part of the lab you will separate `X_norm` into a Training Set, Cross Validation Set, and a Test Set. Each data set will contain rows of `X_norm` chosen at random, making sure that we don't pick the same row twice. This will guarantee that all the rows of `X_norm` are chosen and randomly distributed among the three new sets.
