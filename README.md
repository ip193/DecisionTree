


# Implementing a Decision Tree Image Classifier in Python

#### Using data: scikit-learn handwritten digits dataset

#### Code created for lecture "Fundamentals of Machine Learning" at Uni Heidelberg WS 2018, authors: Jakob Weichselbaumer, Eike Harms, Stephan Detert.  

## Introduction: What is this and how does it work?


![alt text](https://scikit-learn.org/stable/_images/sphx_glr_plot_digits_classification_001.png "Images from the sklearn dataset")

*Image: Sample digits from the sklearn handwritten digits dataset*


Image classification has long counted as one of the toughest problems in machine learning: Given a new image, how can we get a computer to determine what it depicts? Recent advances in machine learning, especially among neural network variants, have seen great progress made on the task. 

Nevertheless, it can be helpful to understand and implement some of the classical approaches to this problem, as they still see use in other machine learning applications. Here, we implement the so-called "decision tree". 

The decision tree is a discriminative classifier used to map an input vector (an image) to a class label (the digit it represents). The guiding idea behind this classifier is that we can find out what digit an image most likely represents by dividing up the set of images we know already into increasingly smaller clusters in our feature space. Once we have divided up all the images we have already seen into small clusters (bins) of images that mostly depict the same kind of image and effectively distinguishes images of different types, we can classify an unseen image based on the bin it falls in. 

For this task, we classified 1797 sample handwritten digits from the sklearn digits dataset to test the performance of the *decision tree* on this problem and see how its preditive power changes when scaled to the *decision forest*. 


### Forests: Greater than the sum of their parts

The decision tree is so called because of how it stores its decison-making function: As a [mathematical tree](https://en.wikipedia.org/wiki/Tree_(graph_theory)). 

A decision *forest*, in turn, is a collection of decision trees. A decision forest can be used as a classifier, the same way a decision tree can. The difference, however, is that the decision tree represents the classification produced by *only one tree*, whereas the decision forest takes a democratic vote of multiple individual decision trees and chooses the most common class label. Neat!

This has real advantages over only using a single decision tree and improves classifier performance. 

To make things even better, adding more trees doesn't even require more data! Using a technique called [bootstrap sampling](https://en.wikipedia.org/wiki/Bootstrapping_(statistics)), we can create a lot of new decision trees in a systematic way from the data we already have and more reliably deal with "weird" data at the same time!


**Note**: In this implementation, we use Gini impurity to find the bins that give the best result. Due to data constraints, we used the training set for testing the accuracy of the classifier. Usually this is a bad idea, because it overestimates the suitability of the classifier and ignores defects of the training set. 


## Viewing the results

*To show the results of the classifier in your browser, open DecisionTree.ipynb*.

Scroll to see the source code and the annotated confusion matrices below. 

Make sure you have [Jupyter Notebook](http://jupyter.org/) installed if you want to edit or run the code in your browser!

--------

This project is licensed under the terms of the MIT license.


