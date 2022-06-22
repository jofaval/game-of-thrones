# Game of Thrones #

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jofaval/game-of-thrones/blob/master/notebook.ipynb)

## Table of contents

1. [📁 Data](#-data)
1. [📓 Description](#-description)
1. [✔️ Objectives](#-objectives)
1. [🧱 Tech stack](#-tech-stack)
1. [💹 Algorithms](#-algorithms)
1. [📊 Visualization](#-visualization)
1. [🤓 Conclusions](#-conclusions)
1. [©️ Credits](#-credits)

## 📁 Data
[↑ Back to the table](#table-of-contents)

The data is from a Kaggle Dataset, [Game of Thrones](https://www.kaggle.com/datasets/mylesoneill/game-of-thrones).

## 📓 Description
[↑ Back to the table](#table-of-contents)

These are cereal ratings of american (USA) cereals, rated by, you guessed it, well, there's no direct clue, but Chris Crawford himself said in the dataset description that: "_Possibly from Consumer Reports_", so there's that. It's a good project to tackle, since the dataset it's one of quality, but really small, less than a hundred rows to work with.

This was a mandatory exercise from our A.I. and Big Data's Master, from which upon I extended into further detail. This is a regression project, that I also turned into a classification one, a multilabel classification project.

This notebook shows conclusions, exploration, analysis, researching into some meanings, hyperparameter tuning, algorithm understanding as to better apply them. It's a long one but it's full of little insights about them. This one I'd say is a little more advanced than the previous ones, and had some references that I looked for, as in, other notebooks that explored similar concepts in the Kaggle's Code section. _Yes, it is, exactly the same as the Game Of Thrones one, since I feel the same, it took more effort than expect to output a decent looking notebook_

## ✔️ Objectives
[↑ Back to the table](#table-of-contents)

In no specific order whatsoever:

- Apply all of the knowledge about regression projects and data exploration.
- Apply all of the knowledge about classification projects.
- Deeply explore, analyze and comprehend the dataset and it's meaning.
- Standarize and unify techniques, plot the explainability and maximize the human effort, I took this one personally at times.
- Understand what goes into the rating of a cereal, and what's the preferred type of cereal.
- Improving and polishing my skills as a junior data scientist and data analyst.
- Explore different solutions and it's prons and cons.
- Working with imbalancement and fixing it.
- Learning to work with small datasets.
- Tackle a project that's out of my comfort zone and not give up.

What were some of the main objectives?

- To try real, useful, and known classification techniques and algorithms to solve this problem
- Detect and find the best solution for the data imbalancement.
- Predict the survivance of a character from the books of Game of Thrones.
- Being able to explain the variability of the dependant variable.

As secondary objectires there were

- Find the house with the most deaths, and the one with the most survivors (characters that remained alive). Which house is the most likely to die.
- Find the culture with the most deaths, and the one with the most survivors (characters that remained alive). Which culture is the most likely to die.
- **Disregarded** - Try to predict the family to which it may belong.
- **Disregarded** - Forecast of how many characters die per season.

It could have been a great idea to predict the culture, or the house even, of a character, but there were cultures with almost no one, and so there were with houses, it wasn't a viable option. But it was contemplated nonetheless.

## 🧱 Tech stack
[↑ Back to the table](#table-of-contents)

Python, that's it! R is a programming language that, as for the moment being, I have no experience with, even though it's powerful and broadly used, but I'd dare to say that no more than Python.

And one of the strongest points, if not the most, about Python, are it's libraries, so... the libraries I've used are:

- Pandas, data manipulation with an ease of use and exploration data analysis.
- Numpy, a really strong linear algebra library, used in the project for it's statistics utilities, SciPy may be an alternative, but I have no experience at all with it.
- Matplotlib and Seaborn, both fantastic libraries for data visualization, and they complement each other.
- Scikit-Learn, the library used for Machine Learning and statistics models: Logistic Regression, SVC, Naive Bayes, Random Forest, etc.
- Tensorflow and Keras, the industry standard for Deep Learning, the way to go, not really, it's just that for now I don't have that many experience with PyTorch

## 💹 Algorithms
[↑ Back to the table](#table-of-contents)

This was a comparison of algorithms with different decomposition and preprocessing techniques, it wasn't about evaluating the best fit as an algorithm, it was about justifying our choices and truly trying out, not all, not most, but quite a few options.

- **Logistic Regression**, always start with the basics, it's surprising how effective the simplest of the solutions usually are, this project showed me that.
- **Polynomial Logistic** Regression, Logistic Regression is Linear Regression with a logarithmic function applied to it's outcome to ensure a binary response, which means that we can add polynomial degrees to it's linear resolution as to improve it's understanding of the problem. Which turned out great
- **Clustering K-Means**, a grouping/segmentation technique, it's not usually meant nor used to classify itself, but it can be done, and it performed, surprisingly, not that bad
- **Clustering MiniBatch K-Means**, and cheaper cost-efficient K-Means implementation, once again, not that bad, at times, even surpasing K-Means
- **KNearest-Neighbour**, imitating real life, near data tend to be similar, in other words, if a row is close (statistically speaking) to another row, there's a chance it will also be of the same label.
- **Linear SVC**, Support Vector Machine are a powerful algorithm that uses to divide a complex problem into simpler ones, it's a better fit for larger datasets, but the linear solver works wonders for smaller ones.
- **Naive Bayes**, a probabilistic approach based on the Bayes' Theorem that the probability of an occurence may contribute to the probability of another event, it performed really great on unbalanced sets, but it was not the best fit for this project when the data was balanced
- **Decision Trees**, really consistent branching resolution to a problem, and very efficient at that, it's also one of the few that explain the resolution, and it does so in a human way
- **Random Forest Classifier**, at times one of the best, but was outperformed but other algorithms, still, a top five for this project and a powerful technique
- **Deep Learning Neural Networks**, Deep Learning here did not perform great, most likely because it required of more data to actually learn the patterns
- **Single Shot Neural Network**, consistent and simple, it performed better on an unbalanced dataset, but, as with the more complex neural network, it required of more data to actually learn the patterns
- **XGBoost Classifier**, a surprisingly efficient solution that, no matter if balanced or unbalanced, actually remained sort of unbiased and, while not having the highest score, performed greatly and consistently at the confusion matrix
- **Baseline**, A dummy model that randomizes the output playing the part as a "Machine Learning Model", almost guaranteed to be close to a ~50% of score

TL;DR; They all performed well enough, XGBoost and Logistic regression have a better confusion matrix.

F1 score wasn't really great for our metrics here, what did gave an insight was the confusion matrix, since many models actually just return either all ones or all zeros. But balancing the data helped a lot fixing that.

## 📊 Visualization
[↑ Back to the table](#table-of-contents)

Distribution and correlation plots are all over the map in this notebook, KDEs (Kernel Density Estimate), boxplots, histplots, piecharts.
Tables really helped a lot, an old classic, but effective! And speaking of old classics, barplots were the main metric for algorithmic comparison, with a couple of variations and groupings, but are the simplest while visually clear plots, for the purpose of my comparison.

There were more advanced plots, such as a violinplot to see the correlation between popularity and the character marital and royal status, and how that affected it's survivance in the series. Some jointplots that helped visualize the correlation between age and survival, or popularity and age while seeing their survivance. Some line plots of explainability and resourcefulness for different techniques.

As aforementioned, the f1 score was "lying" to us, a high score didn't actually represented a model that was performing great, it just represented that on the unbalanced data it didn't miss as much on the majority. Fixing the imbalancement helped greatly, but still, a 50% score could mean that a model only scored well on one label, or that they performed the same on the both labels. So confusion matrix came in the rescue, with a little tuning following Shail Deliwala's notebook, so that the confusion matrix was even clearer to understand and to follow performance-wise.

Concluding: confusion matrices and distribution plots were the main focus for this notebook. Barplots and tables were a comfortable solution to answer some questions.
And, towards the end, the visualization are sort of a report of the performance, the conclusions of the analysis was not the main objective of this project, but what little there is, it's in text form.

## 🤓 Conclusions
[↑ Back to the table](#table-of-contents)

This one took days, I'd dare to say that it even took a week if all the time was put together, the Data Analysis side took time, but the Data Science it's what took the most of this project. But it is, for sure the heaviest I've done without it being a serious project by itself. Alone, without trying to look too much into reference or other's paths.

I'm really proud of myself because I was able to tackle a project that was unbalanced, unclear at times, mainly because of the vague data description, that required of some exploration and algorithm tuning that I never did before. And mostly, because it required consistency and precision, to be conscious at all times of every little change. I learned a lot about the algorithms used as to understanding why they were working and why they weren't. I concluded with a model that barely changes no matter the seed at around ~84% of accuracy.

From start to finish, it took a different turn, a couple of times, and it was sooo worth it! I had a biased result and I did not give up until I cleared that, once I did, I persevered to achieve a resolution that would satisfy myself. There were many aspects to take into account, it had the potential of being really challeing, which it did, but I made it.

As to the model, what seemed to matter the most for the survivance of a character were:

- Name
- Popularity
- Age
- House
- Culture
- Title

Not everyone had a title, nor the age, a house they belonged to. But not having something is already having information. So I took that into account. And this one I also feel that could have more potential to it, but it was hard to work it out to be honest.

## ©️ Credits
[↑ Back to the table](#table-of-contents)

All of the credits for the datasets goes to [Myles O'Neill](http://aboutmyles.com/) and to [Kaggle](https://www.kaggle.com/) a company adquired by Google.

- Shail Deliwala, for it's incredible notebook: https://www.kaggle.com/shaildeliwala/exploratory-analysis-and-predictions/notebook#Exploratory-Analysis
- Gowri Shankar, https://www.kaggle.com/gowrishankarin/analysis-on-got-battles-kaggle-script-of-the-week/report