# Book_Recommender
A book recommender that uses web scraped data from GoodReads, NLP, and clustering techniques to recommend books.
The book recommender has been deployed! 
Check it out at [gr-bookrec.herokuapp.com](gr-bookrec.herokuapp.com)

![image](https://user-images.githubusercontent.com/59543579/122368560-7184bd00-cf2b-11eb-8353-16e8a6a7adf0.png)


Check out the Book Recommender at [gr-bookrec.herokuapp.com](https://gr-bookrec.herokuapp.com) 

The Book Recommender uses metadata scraped from [GoodReads](https://www.goodreads.com) to recommend interesting and relevant books. 

**How to use:** The easiest way to use it is at the web app above. The database is updated regularly so if you cannot find your recommendations now, be sure to check back in 24 hours. You can also run it on google colab by scraping any GoodReads book list and run your query at the bottom of the notebook. The recommender can also take in book names to build the dataset.

The web scraper collects title, author, reviews, ratings, plot summaries, and tags data to create the website's database. Goodreads is a wealth of information on books but not very accessible in an analyzable format. For example, a typical booklist looks like this:

![image](https://user-images.githubusercontent.com/59543579/123773613-c95fe400-d89a-11eb-95b0-855072560a39.png)

And although the information is available to create a recommendetion algorithm, the dataset would be better served in a tabular format. To create the recommender, I first built a web-scraping tool to download Goodreads lists or a list of book titles into a dataframe. Here's the same book list scraped and transformed into a tabular format:

![image](https://user-images.githubusercontent.com/59543579/123776724-8c492100-d89d-11eb-9159-4493e12cae7d.png)




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

Using the website, the recommendations page looks like the following:

![image](https://user-images.githubusercontent.com/59543579/122615577-beb17d80-d056-11eb-8a50-36432793edba.png)

Happy hunting!

