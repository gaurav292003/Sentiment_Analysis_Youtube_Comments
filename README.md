we used YouTube Data API (google-api-python-client) to fetch comments from a specified YouTube video. After importing necessary libraries and initializing the YouTube API client with an API key, the `get_comments` function is defined to retrieve comments iteratively, handling pagination with `next_page_token`. Each comment's text, author, and publication date are extracted and stored in a list. The gathered comments are then converted into a pandas DataFrame for easy manipulation and analysis. Finally, the DataFrame is printed and saved to a CSV file named `youtube_comments.csv`. This enables efficient storage and review of YouTube video comments.
we used Spark script orchestrates a comprehensive pipeline for YouTube comment processing. It commences by initializing a Spark session and loading comment data from a CSV file, followed by schema inspection for data structure comprehension.

For data cleaning, a custom UDF, `clean_comment`, is implemented to strip HTML tags and decode entities from comments. This function is registered and applied, resulting in a new column `cleaned_comment`.

Subsequently, the `Tokenizer` from Spark's MLlib segments comments into individual words, forming a `words` column. Then, the `StopWordsRemover` filters out common stop words, generating a `filtered_words` column.

Further transformations include joining elements of `filtered_words` into a single string in `filtered_words_str`, followed by deduplication to ensure unique records.

Processed data, enriched with author details, original comments, filtered words, and publication dates, is stored in a new CSV file. Existing output directories are removed beforehand to prevent conflicts.

Throughout the process, the script monitors record counts at each stage—initial load, after cleaning, tokenization, stop word removal, and final deduplication—to validate data integrity and track transformation effectiveness. This pipeline enhances data quality, facilitating subsequent analysis tasks like sentiment analysis or trend identification.
2 we have also worked with  spark script demonstrates a thorough workflow for analyzing sentiment in YouTube comments using Apache Spark and NLTK's VADER sentiment analysis tool. Initially, the processed YouTube comments are loaded into a DataFrame, where their schema and a sample of rows are inspected to verify data integrity.

Next, NLTK's VADER lexicon is downloaded and utilized to initialize a sentiment intensity analyzer (`sid`). A user-defined function (UDF), `analyze_sentiment`, applies VADER to classify each comment's sentiment as positive, negative, or neutral based on its compound score. This sentiment analysis is then applied to the DataFrame, creating a new column `sentiment`.

The script aggregates sentiment counts by grouping the DataFrame based on sentiment classifications (`positive`, `negative`, `neutral`). Visualizations are created using seaborn and matplotlib, showcasing sentiment distribution across YouTube comments through bar plots and sentiment score histograms.

Moreover, a function `get_sentiment_score` computes the sentiment score for each comment, which represents the overall sentiment intensity. This score distribution is visualized to depict the spread and intensity of sentiments within the dataset.

Overall, the script provides comprehensive sentiment analysis capabilities for YouTube comments, facilitating deeper insights into audience opinions and emotional responses.
