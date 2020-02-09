<p float="left">
 <img src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/DS%20Logo.png" width = "500"/>
 <img src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/Bicocca%20Logo.png" width = "100" align="right"/>
</p>

# Classification of Amazon Reviews by Topic

The aim of this project is to explore the potential of text mining and machine learning techniques. Specifically, a multiclass text classification problem has been addressed. The primary objective was to develop the data processing flow in order to identify the crucial and most difficult phases in a generic implementation scenario.

<p align="center">
 <img src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/amazon_bow.png" width = "400"/>
</p>

<p float="left">
 <img src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/amazon_comments.png" width = "300" align="right"/>
</p>

## Introduction
Data mining is an interdisciplinary subfield of computer sci- ence and statistics with the overall goal of extracting infor- mation from a dataset and transform it into a comprehensible structure for further use. 

Text mining is a branch of data mining but with the sub- stantial difference that patterns are extracted from natural language text rather than from structured databases. The potential of text mining was already highlighted by some aca- demics. Back in 2004, Ian Witten defined it as "a burgeoning new field that attempts to glean meaningful information from natural language text". 

Although text mining immediately became the object of great interest in academia, it is only in recent years that text mining has attracted the interest of many private companies thanks to the increase in computational capabilities and the interdisciplinarity of the field. Among the many tasks related to text mining are information retrieval, text summarization, content based recommender systems, content clustering and text classification.


## 1. Dataset
The analysis was conducted using the "Amazon reviews data (2018)", which is a collection of product reviews and metadata from Amazon.
Within the collection, the data are divided by product category. Of the available categories, seven were selected to carry out this classification task.
For this task, instead of using the complete review data, a smaller subset consisting of 5-core reviews was used, so that each of the remaining users and items have 5 reviews each.

To avoid making the data analysis process too expensive in computational terms a sample of 2000 was used from each category.


## 2. Preprocessing
A new dataframe was created from the samples extracted from the different categories containing only the variable "reviewText".
Specifically, the following operations were carried out during the pre-processing phase:

  1. Normalization
  2. Tokenization
  3. Stopwords Removal
  4. Stemming
  
  
## 3. Text Representation
In this phase, the first step was to decide between a series of models for the representation of the text in a simplified matrix form.
In the specific case of this analysis, the Bag of Words and Tf-idf were taken into consideration


## 4. Text Classification
This section presents the dataset size reduction techniques and the classification models that have been used.

Since the dimensions of the text representation matrix tf-idf are very large, it was decided to use two techniques to re- duce the dataset dimensionality. The very first step was to operate a feature selection (chi-squared test) which was followed by a features synthetization (with PCA) that allowed to further reduce the numbers of features.

In the development of the project pipeline, a feature selec- tion was first made maintaining only 75% of the best features according to a chi squared test, enabling us to go from 4852 to 3639 features. Subsequently a PCA was carried out, which made it possible to further reduce the number of features from 3639 to 2000, while maintaining more than 90% of the total variance in the data.

Firstly, a set of Machine Learning algorithms was selected taking into account both the data structure and the objective of the analysis.

While the default settings of Scikit-Learn were used for the classifiers LinearSVC and LogistiRegression, for the MLP- classifier an "ad hoc" structure was defined. A neural network with 4 hidden layer was defined. The first layer has 100 neurons while the other 3 have respectively 50 neurons each.
A Rectified Linear Unit (ReLU) activation function was used for all layers. The choice was due both to the efficiency in backpropagation of errors and the ability to make the net- work scattered limiting learning and saturation problems. The Softmax function was selected as the activation function for the output level. This produces as output a probability vector, in the same way as the Sigmoid, and is often used in clas- sification problems preferably in the case of more than two classes.
The loss function to be minimized was the Categori- cal Cross Entropy, although other performance measures were considered including Accuracy, Precision, Recall and F-measure. As optimizer, we used Adam (RMSprop + Mo- mentum), a gradient algorithm with adaptive learning rate, which helps to add a bias correction at different times.


## 5. Models evaluation
This section presents the procedures that have been carried out for the evaluation of the models, the measurements used to compare them and the results thanks to some known graphic techniques.
The best results are obtained by the Linear SVC, not only in terms of higher average accuracy value than other models, but especially of computational cost.

## 6. Conclusions 
The aim of this paper was to highlight the potential of text mining and machine learning techniques. Specifically, a mul- ticlass classification problem was addressed. The primary objective was to develop the data processing flow in order to identify which could be the crucial and most difficult phases in a generic implementation process.
While the development of the classification models was relatively simple, one of the major obstacles was to handle high computational costs with respect to the definition of the most appropriate dataset dimension.
The main problem that this study attempted to address was the reduction in dimensionality to obtain better perfor- mance from the classification algorithms. In particular, a feature selection and PCA was carried out allowing to reduce the number from 4852 features to 2000 main components, maintaining more than 90% of data variability.
Another difficulty was to limit the number of observations for each category because beyond 30000 observations the computational capabilities at the ram level (local and gdrive) would be exceeded.
In conclusion, although the results may be satisfactory, computational costs remain a major hurdle for making models scalable. Possible future developments could be addressed by considering other techniques or variations of the same PCA, such as the categorical PCA.


<p align = "center">
  <img src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/AR%20Logo.png" width = "250">
</p>    
    
    
<p align = "center">
<a href="https://github.com/RaffaeleAns">
<img border="0" alt="W3Schools" src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/GitHub%20Logo.png" width="20" height="20">
</a>
 <a href="https://www.linkedin.com/in/raffaele-anselmo-213a0a179">
<img border="0" alt="do" src="https://github.com/RaffaeleAns/Classification-of-Amazon-Reviews-by-Topic/blob/master/images/LinkedIn%20Logo.png" width="20" height="20">
</a>
</p>
