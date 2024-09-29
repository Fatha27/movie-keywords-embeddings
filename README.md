# Movie Rating Prediction Model

## Goal
The purpose of this notebook is to build a predictive model for movie ratings based on various features such as keywords, genres, director, and average user ratings. 
The model predicts how a particular user will rate a movie on a scale of 0.5 to 5.0.

## Steps

1. **Data Collection**
   - Fetch movie details like keywords, genres, average rating, title, and release date from the TMDB API using the movie name.
   
2. **Data Preparation**
   - Process and encode features like `keywords`, `genres` using label encoders.
   - **`Utilizing Embeddings`**: Since our data has has high cardinality features like *keywords* (1932) , simply using one-hot encoding will lead to probolems like *Dimensionality Curse, increase in model computational time, and space*.
     Instead , we use Embeddings for categorical features. This approach captures semantic relationships between categories and reduces dimensionality, leading to better performance and efficiency in training the model.
   - Prepare input data by padding keywords and genres to fixed lengths.
   

3. **Modeling**
   - Train a neural network with embedding layers for categorical features (`keywords`, `genres`) and fully connected layers for numerical features (like `average_rating`).
   - Use metrics like Mean Absolute Error (MAE) and R-squared (R²) score to evaluate model performance.

4. **Evaluation**
   - Predict movie ratings and compare them with actual ratings given by a user.
   - Investigate cases where the model's predicted rating deviates significantly from the given rating.

5. **Interpretation**
   - Display predictions along with the movie's title, release year, and detailed features.
   - Use the model to predict and print the rating for any given movie by name.

## Metrics
- **Mean Absolute Error (MAE)**: Measures the average absolute difference between predicted and actual ratings. A low value indicates a better fit.
- **R² Score**: Represents how well the model captures the variation in the actual ratings. An R² score close to 1 suggests the model fits well.

