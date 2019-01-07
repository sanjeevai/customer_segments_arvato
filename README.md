# Data Scientist Nanodegree

## Unsupervised Learning

## Identifying Customer Segments for Arvato

## Table of Contents

1. [Project Introduction](#intro)
2. [Project Overview](#overview)
3. [Software and Libraries](#sw)
4. [Project Motivation](#motive)
5. [Project Details](#details)
    1. [The Data](#data)
    2. [Preprocessing](#prep)
    3. [Feature Transformation](#transform)
    4. [Clustering](#cluster)
    5. [Submission Evaluation](#submit)
6. [Arvato: Terms and Conditions](#tnc)

*** 

<a id='intro'></a>

### Project Introduction

In this project, Udacity's Bertelsmann partners **AZ Direct** and **Arvato Financial Solutions** have provided **two** datasets one with **demographic** information about the people of **Germany**, and one with that same information for customers of a **mail-order sales company**. I'll look at relationships between demographics features, organize the population into clusters, and see how prevalent customers are in each of the segments obtained.

<a id='overview'></a>

### Project Overview

In this project, I'll work with **real-life** data provided to us by Udacity's Bertelsmann partners AZ Direct and Arvato Finance Solutions. The data here concerns a company that performs mail-order sales in Germany. Their **main question** of interest is to identify facets of the population that are most likely to be purchasers of their products for a mailout campaign. My job as a data scientist is to use unsupervised learning techniques to organize the general population into clusters, then use those clusters to see which of them comprise the main user base for the company. **Prior** to applying the machine learning methods, I will also need to **assess** and **clean** the data in order to convert it into a **usable** form.

<a id='sw'></a>

### Software and Libraries

The data is **proprietary**, so it is not uploaded here to comply with the [terms and conditions](https://github.com/sanjeevai/customer_segments_arvato/blob/master/terms_and_conditions/terms.md).

This project uses Python 3.6.3 and is designed to be completed through the Jupyter Notebooks IDE. The following libraries are used in this project:

- NumPy
- pandas
- Sklearn / scikit-learn
- Matplotlib (for data visualization)
- Seaborn (for data visualization)

<a id='motive'></a>

### Project Motivation

The unsupervised learning branch of machine learning is key in the organization of large and complex datasets. While unsupervised learning lies in contrast to supervised learning in the fact that unsupervised learning lacks objective output classes or values, it can still be important in converting the data into a form that can be used in a supervised learning task. Dimensionality reduction techniques can help surface the main signals and associations in our data, providing supervised learning techniques a more focused set of features upon which to apply their work. Clustering techniques are useful for understanding how the data points themselves are organized. These clusters might themselves be a useful feature in a directed supervised learning task. This project gave me hands-on experience with a real-life task that makes use of these techniques, focusing on the unsupervised work that goes into understanding a dataset.

In addition, the dataset presented in this project requires a number of assessment and cleaning steps before I can apply my machine learning methods. In workplace contexts, I will be frequently need to work with data that is untidy or needs preprocessing before standard algorithms and models can be applied. The ability to perform data wrangling and the ability to make decisions on data that we work with are both valuable skills that I practiced in this project.

<a id='details'></a>

### Project Details

<a id='data'></a>

#### Step 0: The Data

There are a number of files used for this project. I have not shared the files here in [agreement](https://github.com/sanjeevai/customer_segments_arvato/blob/master/terms_and_conditions/terms.md) with Arvato Bertelsmann, as the data is proprietary.

The files used in this project are:

1. `Udacity_AZDIAS_Subset.csv`: Demographic data for the general population of Germany; 891211 persons (rows) x 85 features (columns).

2. `Udacity_CUSTOMERS_Subset.csv`: Demographic data for customers of a mail-order company; 191652 persons (rows) x 85 features (columns).

3. `Data_Dictionary.md`: Information file about the features in the provided datasets.

4. `AZDIAS_Feature_Summary.csv`: Summary of feature attributes for demographic data.

5. `Identify_Customer_Segments.ipynb`: Jupyter Notebook divided into sections and guidelines for completing the project.

<a id='prep'></a>

#### Step 1: Preprocessing

Before we start an analysis, we must first explore and understand the data that we are working with. In this (and the next) step of the project, I worked with the general demographics data. As part of my investigation of dataset properties, I came at the following key points:

- How are missing or unknown values encoded in the data? Are there certain features (columns) that should be removed from the analysis because of missing data? Are there certain data points (rows) that should be treated separately from the rest?

- Consider the level of measurement for each feature in the dataset (e.g. categorical, ordinal, numeric). What assumptions must be made in order to use each feature in the final analysis? Are there features that need to be re-encoded before they can be used? Are there additional features that can be dropped at this stage?

I created a cleaning procedure that I applied first to the general demographic data, then later to the customers data.

<a id='transform'></a>

#### Step 2: Feature Transformation

After data cleaning, I used dimensionality reduction techniques to identify relationships between variables in the dataset, resulting in the creation of a new set of variables that account for those correlations. In this stage of the project, I attended to the following key points:

- The first technique that I should perform on our data is feature scaling. What might happen if I don’t perform feature scaling before applying later techniques I’ll be using?

- Once I’ve scaled my features, I can then apply principal component analysis (PCA) to find the vectors of maximal variability. How much variability in the data does each principal component capture? Can I interpret associations between original features in your dataset based on the weights given on the strongest components? How many components will I keep as part of the dimensionality reduction process?

I used the sklearn library to create objects that implement my feature scaling and PCA dimensionality reduction decisions.

<a id='cluster'></a>

#### Step 3: Clustering

Finally, on my transformed data, I will apply clustering techniques to identify groups in the general demographic data. I'll then apply the same clustering model to the customers dataset to see how market segments differ between the general population and the mail-order sales company. I will perform the following taska in this stage:

- Use the k-means method to cluster the demographic data into groups. How should I make a decision on how many clusters to use?

- Apply the techniques and models that I fit on the demographic data to the customers data: **data cleaning, feature scaling, PCA,** and **k-means** clustering. Compare the distribution of people by cluster for the customer data to that of the general population. Can I conclude anything about which types of people are likely consumers for the mail-order sales company?

`sklearn` will continue to be used in this part of the project, to perform my k-means clustering. In the end, I'll export the completed notebook with my work as an HTML file, which will serve as a report documenting my approach and findings.

<a id='submit'></a>

#### Step 4: Submission Evaluation

This project was evaluated successfully against this [rubric](https://github.com/sanjeevai/customer_segments_arvato/blob/master/Project_Rubric.pdf).

<a id='tnc'></a>

### Arvato: Terms and Conditions

Terms and Conditions before using the data set for this project-

In addition to Udacity's Terms of Use and other policies, your downloading and use of the **AZ Direct GmbH** data solely for use in the **Unsupervised Learning** and **Bertelsmann Capstone** projects are governed by the following additional terms and conditions. The big takeaways:

- You agree to AZ Direct GmbH's General Terms provided below and that you only have the right to download and use the AZ Direct GmbH data solely to complete the data mining task which is part of the Unsupervised Learning and Bertelsmann Capstone projects for the Udacity Data Science Nanodegree program.

- You are prohibited from using the AZ Direct GmbH data in any other context.

- You are also required and hereby represent and warrant that you will delete any and all data you downloaded within 2 weeks after your completion of the Unsupervised Learning and Bertelsmann Capstone projects and the program.
- If you do not agree to these additional terms, you will not be allowed to access the data for this project.