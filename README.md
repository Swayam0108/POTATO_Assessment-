# POTATO_Assessment-
# Tweet Querying System

# DataSet Link - https://drive.google.com/file/d/16y-dp_0Kn32B6L-1xTlSZjOGWfTp0AJZ/view?usp=sharing

# Overview
This project provides a system for analyzing tweet data based on specific search terms. It allows users to query various metrics related to tweets, such as the number of tweets containing a term, the most active users, and tweet engagement metrics. The system is built using Python and the Pandas library, making it efficient and user-friendly.

# Prerequisites
Before using this system, ensure you have the following installed on your computer:
   Python: Download and install from python.org.
   Jupyter Notebook: Install Jupyter Notebook, preferably via Anaconda. You can download it from Anaconda Distribution.

# Installation

To set up the system, follow these steps:

1. Install Required Libraries: Open your terminal or Anaconda prompt and run the following command to install the necessary library:
    pip install pandas

2. Create a Jupyter Notebook
    Launch Jupyter Notebook by typing jupyter notebook in your terminal.
    Create a new Python notebook.

3. Load the Data: Ensure your tweet data is in a .tsv format. Load your data into a Pandas DataFrame using the following code:
    import pandas as pd
    # Load the dataset
    df = pd.read_csv('your_data_file.tsv', sep='\t')
    # Display the first few rows
    print(df.head())

4. Preprocess Data
  Ensure your date columns are in the correct format, which will be essential for querying:
  # Convert 'created_at' to datetime format
  df['created_at'] = pd.to_datetime(df['created_at'], errors='coerce')

  # Check for any rows where conversion failed
  print(df[df['created_at'].isna()])

Query Functions

The system provides several functions to query the tweet data. Below are key functionalities available:
1. Search for Tweets by Date and Location
This function allows users to filter tweets based on a specified search term and view the number of tweets per day, along with their corresponding place IDs.
  def search_term_by_date_and_location(term, df):
    ...

2. Analyze Times of Day for Tweets
This function helps users understand the distribution of tweets by time of day for a specified search term.
  def search_term_by_time_of_day(term, df):
    ...
   
4. Find the Most Active User
Users can find which user posted the most tweets containing a specified term.
  def most_active_user(term, df):
    ...

4. Get Average Likes for Tweets
This function calculates the average number of likes for tweets containing the specified term.
  def average_likes_for_term(term, df):
    ...

5. Unique Users Posting the Term
This function counts the number of unique users who posted tweets containing the specified term.
  def count_unique_users(term, df):
    ...

Usage
After defining the functions, you can run queries by specifying a term. For example:

term = 'music'  # Replace with your search term

# Get tweets by date and location
date_location_result = search_term_by_date_and_location(term, df)
print(date_location_result)

# Find the most active user
active_user_result = most_active_user(term, df)
print(active_user_result)

# Get average likes for tweets containing the term
average_likes_result = average_likes_for_term(term, df)
print(average_likes_result)

# Important Design Choices

   Pandas DataFrame: The decision to use Pandas for data manipulation allows for powerful filtering, grouping, and aggregation, making it suitable for analyzing large datasets efficiently.
      
   Function Modularity: Each query is encapsulated in its own function. This modularity enhances code readability and maintainability, allowing users to easily modify or add functionality as needed.
      
   Error Handling: The use of errors='coerce' in date conversion ensures that invalid entries are handled gracefully, preventing the system from crashing due to unexpected data formats.
      
   Descriptive Outputs: The functions return clear and informative results, making it easy for users to interpret and utilize the findings from their queries.
      
   Reusability: By defining functions, users can easily adapt the system to analyze different search terms or datasets without rewriting code.

