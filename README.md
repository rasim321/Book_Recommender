# Book_Recommender
A book recommender that uses web scraped data from GoodReads, NLP, and clustering techniques to recommend books.

**How to use:**
The easiest way to use it is to run it on google colab. The books.csv file is provided for the Part 1 recommender. 
For Part 2, you can scrape any GoodReads book list and run your query at the bottom of the notebook. 
The recommender also takes in book names to build the dataset. 


# Part 1: Simple Book Recommender using pre-downloaded data

We use KNN and a pre-downloaded dataset of books (books.csv) to recommend books. 
The number of books in this data is limited, and the KNN algorithm uses number of ratings and tags to find 
recommended books. 

Can we improve this recommender? 

# Part 2: Scraping GoodReads Data

By scraping data directly from GoodReads, we can get richer data on book lists or, given enough time, a much larger dataset of books. 
This part will allow us to scrape information using book titles or book list links from GoodReads. 

![image](https://user-images.githubusercontent.com/59543579/120947769-83d25000-c70e-11eb-9ebe-a2924d9258bc.png)


# Part 3: Book Recommender using summary embeddings and tags

We use BERT to produce embeddings of the plot_summaries of the books in the dataset. Either book list links or a list of book titles 
can be used to create a dataset of books from which the algorithm will choose recommendations. 

The cosine similarity score of the embeddings and the tags data score are used to create a 'z-score' with different weights for the 
two scores. 

The book recommender does not use ratings or review data, but uses the semantic similarity of the plot summary and the tags to 
recommend books.

Book Query: "Little Women"

Recommendations: 

![image](https://user-images.githubusercontent.com/59543579/120947854-bed48380-c70e-11eb-99a0-709c1cccc63a.png)

