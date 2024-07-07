# Recommender System

# 📗 Table of Contents
- [🚀 Report](#report)
- [🛠 Dependencies](#dependencies)
- [💻 Usage](#usage)
- [👥 Author](#author)


## 🚀 Report <a name="report"></a>
The aim of the project is to build a recommender system to recommend a list of movies for two users.
1. The data sets used are:
    - MovieLens: ml-1m
    - IMDB: name.basic and title.basic

2. For our feature engineering, we created a merged DataFrame combining both datasets joining them on the title of the movies. But in our recommender system, we won't be needing all the information present in all the datasets because we'll be doing a collaborative filtering model so we won't be needing the extra metadata. Furthermore, by analyzing our data, we notice that our data is extremely sparsed. We need to take that into consideration when choosing our model for our recommendation system. 

3. The model I chose to build is a collaborative filtering based on SVD.
At first we did a simple matrix decomposition and obtained a reconstructed matrix that represents ratings of the movies but our data being extremely sparse we can't go foward with solely a regular SVD. We opted for Simon Funk's SVD algorithm. By using factorizing a matrix into two other ones and using gradient descent to find optimal values of features and weights we can create a model that has a RMSE of 0.86. which is sufficient for our recommendation system.

4. For our recommendation system we did the following:
    - predict the rating for movies for User1 and User2
    - get only the movies which User1 and User2 have not seen
    - do the average of both ratings to create a `couple score`
    - select the top n movies with the highest `couple score`
    
    this was the taken approach. Initialy we were thinking to make a sort of new user were we could combine both ratings and make a prediction but this doesn't represent well our two users.

5. For our model, we used a simple Root mean square error (RMNS)to evaluate our model. We can believe that this metric is enough for evaluating our model since we combine the predictions of two users to create our `couple score`. So the error on the prediction is sufficient and represents well the error of our model.


## 🛠 Dependencies <a name="dependencies"></a>
- python


## 💻 Usage <a name="usage"></a>
Here are the steps you'll need to follow in order to run the project

```sh
$ python -m venv .venv
$ source .venv/bin/activate
```
Then open and run the `notebook.ipynb` in src!



## 👥 Author <a name="author"></a>
- Maxime Buisson