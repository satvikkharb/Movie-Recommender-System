# Movie-Recommender-System
A recommender system, or a recommendation system, is a subclass of information filtering systems that seeks to predict the "rating" or "preference" a user would give to an item. They are primarily used in commercial applications. (source - Wikipedia)

Mainly three types of recommendation systems in machine learning based on filtering are used to suggest products and services to the consumers.


1. Content Filtering

2. Collaborative Filtering

3. Hybrid Filtering


## Content Filtering:

In this algorithm, we try finding items that look alike. Once we have the item look like a matrix,

we can easily recommend alike items to a customer, who has purchased any item from the store.

## Collaborative Filtering:

Here, we try to search for look-alike customers and offer products based on what his/her lookalike has chosen.

This algorithm is very effective but takes a lot of time and resources.

## Hybrid Filtering (Content Filtering + Collaborative Filtering):

Both Content Filtering & Collaborative Filtering are used for this purpose. YouTube uses this algorithm for its strong recommendation system.

For this project, a content-based filtering model more specifically an item-based filtering concept has been used. The concept of Clustering, a subset of unsupervised machine learning has been used to build this recommendation system. CountVectorizer of sklearn library has been used to count the frequency of the genres types. The Hyperparameter of CountVectorizer gives better results. 

## Cellwise breakdown

In [58]
Here genera column is a string of a list that contains a dictionary. Hence we will need to use the ast.lieral_eval function to convert it into a list that contains  a dictionary.
Here we are making a function named ‘convert’ that has an empty list L that is going to append all the values of the key ‘name’ to the list L.
We are going to pass this function on the genera column so it has all the values of the name keyword.
Now movies[‘genres’] column has a list of all the genres related to that movie

In [64]
Convert2 is the function created for the column crew as we are trying to extract the top 3 actors by their real names. Here we create a variable named counter and iterate it till we extract the first 3 names as a list.

In [73]
In the crew column we just need to extract the name of the director hence we we will make a function convertor3 that will give out just the name of the person who’s job is the Director.

In [79]
Now we will need to remove the spaces between the names as our recommender system will consider first name and last name as different entities. Eg. we need to watch a movie  from Sam Wilmington but we also have Sam Mendes as one of our tags hence our model will get confused. So we will remove the spaces between the first name and the last name so that our model performs well.
We will make a function named collapse that will remove all the spaces (“ “) between the words with blanks (“”)
And then apply this function to all the rows

In [83]
We will create a column named tags that will be a collection of all the columns.

In [85]
We will create a new database with just the three columns. 

In [87]
We will convert the tags column from a list to a string using the lambda and join function.

In [97]
Using the lambda function we are converting the tags column to lowercase so that it will help in searches.

In [115]
We have found the vectors, and now we need to deal with similar words like love, loving, loved. For dealing with these similar words we are gonna use the nltk library. This process is called stemming.

In [127]
Now we will convert the tags column to a vector using the text-to-vector technique. For this technique we will combine the tags of each row and make it a large text, from this large text we will find out 5000 most frequently occurring words. Now for each movie, we will make the column as each of 5000 words and how many times each word has shown up in a particular movie tag we will find. Hence we will get a table of shapes (4806,5000) where 4806 is the number of movies and 5000 is the total number of words that are most commonly used in the tags column. Now each movie is a vector in this 5000-dimensional space.

Note- During the vectorization process we will not use stop words that help in the formulation of the sentence but have no meaning in themselves eg. are, and, of, to, etc.

For doing this text vectorisation process we will use the CountVectorizer from sklearn.

In [134]
Now we have 4806 vectors so we need to find similarities between vectors to get similar movies as output. But here we will not find out euclidian distance but rather cosine distance ie. The angle between two vectors and the lesser the angle, the more similar are the movies. We are not using euclidian distance as this is a very high dimensional space and euclidian distance fails in these high dimensional spaces.

For finding out the cosine distance we will use the cosine similarity function in sk learn. Now this cosine similarity when trained on the vectors will be of the shape 4806,4806 ie distance of every movie with every other movie. We will store it in a variable named similarity, here the similarity score of first movie with the itself will be 1.

In [145]
We will make a recommendation function that will give out the names of movies that are similar to the one given as input.
