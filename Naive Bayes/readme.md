# **Naive Bayes Classifier**
Naive Bayes is a simple yet powerful probabilistic machine learning algorithm used for classification tasks. It is based on Bayes' Theorem with the assumption that features (predictors) are conditionally independent given the class label. Despite this "naive" assumption, Naive Bayes often performs well in various real-world applications, especially in text classification and spam filtering.

In this section, we'll cover the mathematical foundation of Naive Bayes, the application of Bayes' Theorem, how it works in practice, and illustrate it with an example of predicting whether it will rain based on features like humidity, wind, and temperature.

Naive Bayes Classifier is based on Bayes' Theorem, a mathematical formula used to update probabilities based on new information.

Bayes' Theorem is expressed as:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_byes_theorem.jpg)

Where:
* P(C∣X) is the posterior probability: the probability of class 𝐶 (e.g., rain or no rain) given the feature vector 𝑋 (e.g., humidity, wind, temperature).
* P(X∣C) is the likelihood: the probability of observing the features 𝑋 given that the class is 𝐶.
* P(C) is the prior probability of the class 𝐶, independent of the features.
* P(X) is the marginal likelihood or evidence: the probability of the features 𝑋 occurring across all possible classes.

** Naive Bayes Assumption: **

The "naive" part of Naive Bayes comes from assuming that the features are conditionally independent, meaning each feature contributes independently to the probability of the class. Mathematically, if 𝑋=(𝑥1,𝑥2,...,𝑥𝑛) are​ the features, then:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_features.jpg)

This assumption simplifies the calculations significantly, although it might not hold in every real-world scenario.

### **Types of Naive Bayes Classifiers**

There are different variants of Naive Bayes Classifiers depending on how the features are modeled. The most common ones are:

1. **Gaussian Naive Bayes:** Assumes that continuous features follow a Gaussian (normal) distribution.
2. **Multinomial Naive Bayes:** Used when the features represent counts (e.g., word counts in text data).
3. **Bernoulli Naive Bayes:** Used when the features are binary (e.g., yes/no, true/false).

### ***Naive Bayes Classifier for Rain Prediction Example**

Let's consider an example where we want to predict whether it will rain (binary classification: Rain or No Rain) based on the following features:

* Humidity (High, Low)
* Wind (Strong, Weak)
* Temperature (Hot, Mild, Cool)

## **Step 1: Collect the Training Data**

We assume the following training dataset of 10 days where we record the weather conditions and whether it rained:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_dataset.jpg)

## **Step 2: Calculate the Prior Probabilities 𝑃(𝐶)**

We begin by calculating the prior probabilities for the class labels Rain and No Rain:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_prob_labels.jpg)

## **Step 3: Calculate the Likelihoods 𝑃(𝑋∣𝐶)**

Next, we calculate the likelihoods for each feature given the class label. For example, we'll calculate the probability of having High Humidity given that it rained:

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_prob_high_humidity_rain.jpg)

Similarly, we calculate the other likelihoods:

* **Humidity Likelihoods:**

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_humidity_likelihood.jpg)

* **Wind Likelihoods:**

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_wind_likelihood.jpg)

* **Temperature Likelihoods:**

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_temp_likelihood.jpg)

## **Step 4: Predicting Using Bayes' Theorem**

Now, let's use these probabilities to predict whether it will rain based on the following new day observation:

* Humidity = High
* Wind = Weak
* Temperature = Hot

We calculate the posterior probabilities for both Rain and No Rain:

**Using the Naive Bayes formula:**

Since 𝑃(𝑋) is the same for both Rain and No Rain, we only need to compare the numerators for each class.

![](https://github.com/shubham031194/Machine-Learning/blob/main/Naive%20Bayes/assets/Naive_Bayes_result.jpg)

## **Step 5: Final Decision**

Since 𝑃(Rain∣𝑋)=0.134 is greater than 𝑃(No Rain∣𝑋)=0.0125, we predict that it will rain.

##Limitations:##
1. **Conditional Independence Assumption:** This assumption often does not hold in real-world datasets, which can reduce performance.
2. **Zero Probability Problem:** If a class-conditional probability is zero, the entire posterior probability becomes zero. This issue can be handled using techniques like Laplace smoothing.


Naive Bayes is a fast, simple, and effective classifier that works well for many practical classification tasks. By leveraging Bayes' Theorem and assuming feature independence, it is especially useful when dealing with small datasets or high-dimensional data, making it a go-to algorithm for text classification and spam filtering.

Happy Learning! 🎉
