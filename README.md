

## Introduction

This project showcases the creation of an SQLite database for a simplified social media platform. The database consists of five tables: User, Follower, Tweet, Reply, and Like. Each table has predefined columns to store relevant information.

## Features

- Creation of user profiles
- Ability to follow and unfollow other users
- Posting tweets and replies
- Liking tweets
- Retrieving and querying user-related data

## Getting Started

### Prerequisites

- SQLite3: Ensure you have SQLite3 installed on your system. You can download it from the [official SQLite website](https://www.sqlite.org/download.html).

### Installation

1. Clone the repository to your local machine.
2. Open a terminal and navigate to the project directory.

## Usage

### Populating Sample Data

1. Open the SQLite3 CLI by entering the following command in the terminal:
   ```
   sqlite3 social_media_db
   ```

2. Copy and paste the SQL commands from the `create_tables.sql` file to create the database schema and tables.

3. Copy and paste the SQL commands from the `insert_sample_data.sql` file to populate the tables with sample data.

### Querying the Database

You can execute SQL queries to interact with the database. For example:

- Retrieve user information:
  ```sql
  SELECT * FROM user;
  ```

- Find tweets and replies by a specific user:
  ```sql
  SELECT tweet.*, reply.reply FROM tweet
  LEFT JOIN reply ON tweet.tweet_id = reply.tweet_id
  WHERE tweet.user_id = 1;
  ```

- Get the number of likes for each tweet:
  ```sql
  SELECT tweet.tweet_id, tweet.tweet, COUNT(like.like_id) AS num_likes
  FROM tweet
  LEFT JOIN like ON tweet.tweet_id = like.tweet_id
  GROUP BY tweet.tweet_id;
  ```

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

---

