Book Recommender System 📚
This project is a book recommendation system developed in a Jupyter Notebook. It uses a dataset from the Book-Crossing community to suggest books to users. The system implements two primary recommendation strategies: a popularity-based model and a collaborative filtering model.

📖 Project Overview
The main objective of this project is to build a system that can recommend books to users. It starts with raw data from three separate files (books.csv, users.csv, ratings.csv), processes and cleans this data, and then builds two different types of recommendation engines.

Key Features:
Data Preprocessing & Cleaning: The notebook includes steps for cleaning the data, handling missing values, and ensuring data consistency.

Popularity-Based Filtering: A simple yet effective model that suggests books based on their overall popularity. It identifies the top-rated books that have been reviewed by a significant number of users.

Collaborative Filtering: A more personalized model that recommends books by finding similarities between them based on user ratings. It uses the cosine similarity metric to identify books that are often rated similarly by different users.

Model Persistence: The final processed dataframes and the similarity matrix are saved using pickle for easy use in a web application or other deployments.

⚙️ How It Works
The project is broken down into two main parts:

1. Popularity-Based Recommender
This model calculates the average rating for each book and considers only those books that have received at least 250 ratings. The final output is a list of the top 50 books sorted by their average rating, providing a general list of highly-regarded books.

2. Collaborative Filtering Recommender
This approach provides more personalized recommendations.

Filtering: The dataset is first filtered to create a more reliable user-item matrix. It considers only users who have rated more than 200 books and books that have been rated at least 50 times.

Creating the User-Item Matrix: A pivot table is created where the rows are book titles, the columns are user IDs, and the values are the ratings.

Calculating Similarity: The cosine_similarity from scikit-learn is used to compute the similarity score between every pair of books in the matrix.

Making Recommendations: A function recommend(book_name) is defined. When you provide a book title, it finds the most similar books based on the cosine similarity scores and returns a list of the top 4 recommendations, including their author and cover image URL.

For instance, a recommendation for the book 1984 yields:

Animal Farm

The Handmaid's Tale

Brave New World

The Vampire Lestat (Vampire Chronicles, Book II)

🛠️ Tech Stack
Python

Pandas: For data manipulation and analysis.

NumPy: For numerical operations.

Scikit-learn: For calculating cosine similarity.

Pickle: For saving and loading the model and dataframes.

Jupyter Notebook: As the development environment.

💾 Dataset
The project uses the Book-Crossing Dataset, which is comprised of three files:

books.csv: Contains book details such as ISBN, Book-Title, Book-Author, Year-Of-Publication, and Publisher.

users.csv: Contains user information like User-ID, Location, and Age.

ratings.csv: Contains book ratings given by users, linking User-ID to ISBN.

🚀 How to Run the Project
Clone the repository:

git clone https://github.com/your-username/your-repository-name.git

Place the Datasets: Make sure the books.csv, users.csv, and ratings.csv files are in the same directory as the notebook.

Install dependencies:

pip install numpy pandas scikit-learn jupyterlab

Launch Jupyter Notebook:

jupyter notebook Book_recommender_system.ipynb

Run the cells: Execute the cells in the notebook sequentially to train the models and see the recommendations. The notebook will also generate the following .pkl files:

popular.pkl

pt.pkl

books.pkl

similarity_scores.pkl
