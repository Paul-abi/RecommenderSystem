# MoviePairing

# Download IMDb Dataset
The project needs the dowload of 
* https://datasets.imdbws.com/name.basics.tsv.gz
* https://datasets.imdbws.com/title.basics.tsv.gz

inside the data folder

## Data Collection and Preparation

#### MovieLens Dataset:
Utilized the MovieLens dataset, which includes user ratings for various movies. The dataset was loaded using pandas, and necessary preprocessing steps were taken to clean and format the data correctly.
* Data Cleaning and Transformation
Implemented a custom function clean_movie_title to clean up movie titles, including removing years in parentheses and correcting capitalization for articles like 'The' and 'A'.
Merged the cleaned MovieLens and IMDb datasets based on movie titles and release years to create a comprehensive dataset.
#### IMDb Dataset:
Additionally, the IMDb dataset was used to enrich the movie metadata. This included filtering for movies only, dropping unnecessary columns, and ensuring consistent naming conventions across datasets.

## Data Visualization
Conducted exploratory data analysis through visualization, focusing on the distribution of movies by release year.


##  Combination user data
Merge the rating profiles of two users of the user-item interaction matrix

## Model Building
Split the dataset into training and testing sets to evaluate the model's performance.

The core of our recommendation system is built upon 
matrix factorization, specifically using 
the Alternating Least Squares (ALS) method.
This approach decomposes the user-movie interaction 
matrix into the product of two lower-dimensional 
rectangular matrices, one representing users and
the other representing movies.

#### Matrix Factorization
Alternating Least Squares (ALS): Implemented to learn latent features for both users and movies. The ALS algorithm iteratively updates these features to minimize the difference between the predicted and actual ratings.
##### Rating Prediction
After obtaining the latent feature matrices, we predict user ratings for unseen movies using a dot product operation.
#### Recommendations Generation
Based on the learned latent features, we generate recommendations for each user by predicting how highly they would rate unseen movies. The top N predictions are selected as recommendations.

# Futher Amelioration

* Add content base filtering with writer, director, genre, crew...
* Do a better combination of data
* Do a couple score
* Add an evaluation for the models
* Try more complex recommendation algorithm
