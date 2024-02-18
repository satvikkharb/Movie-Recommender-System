# Movie-Recommender-System
A recommender system, or a recommendation system, is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item. They are primarily used in commercial applications. (source - Wikipedia)

Mainly three types of recommendation systems in machine learning based on filtering are used to suggest product and services to the consumers.


1.Content Filtering

2.Collaborative Filtering

3.Hybrid Filtering


##Content Filtering:

In this algorithm, we try finding items look alike. Once we have item look like matrix,

we can easily recommend alike items to a customer, who has purchased any item from the store.

##Collaborative Filtering:

Here, we try to search for look alike customers and offer products based on what his/her lookalike has chosen.

This algorithm is very effective but takes a lot of time and resources.

##Hybrid Filtering (Content Filtering + Collaborative Filtering):

Both Content Filtering & Collaborative Filtering is used for the purpose. you-tube uses this algorithm for their strong recommendation system.

For this project, Content based filtering model more specifically item-based filtering concept has been used. Concept of Clustering, a subset of unsupervised machine learning has been used to build this recommendation system. CountVectorizer of sklearn library has been used to count the frequency of the genres types. Hyper parameter of CountVectorizer gives better result. 
