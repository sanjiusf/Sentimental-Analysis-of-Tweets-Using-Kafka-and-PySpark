# Sentimental-Analysis-of-Tweets-Using-Kafka-and-PySpark

This project shows sentimental analysis of Twitter tweets using Python, Spark, Kafka and Twitter streaming API. Firstly the tweets are processed live using Apache Kafka, which is a message qeueuing service, Tweepy and Python. The tweets are stored in Kafka topic "Twitterstream". Secondly, sentimental analysis is performed on the tweets by accessing them from the Kafka topic using Python and Spark.

Step 1: Real time processing of tweets:

Kafka_to_twitter.py : This is the code file which performs step 1.

Twitter Developer keys:

For this we require twitter developer keys which are stored in file twitter-app-credentials.txt. To get the credentials please visit the https://developer.twitter.com/en/apps .

Kafka Installation:

To install Kafka please download from https://kafka.apache.org/downloads .

Steps to start Kafka in Windows(Open a command prompt and change the directory to the kafka directory):
1. Start the zookeeper : .\bin\windows\zookeeper-server-start.bat config\zookeeper.properties

2. Start Kafka server : .\bin\windows\kafka-server-start.bat config\server.properties

3. Create a topic named "Twitterstream" : .\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic twitterstream

You can also refer to https://www.tutorialspoint.com/apache_kafka/apache_kafka_basic_operations.htm to know about basic operations.

After this is done, run the file Kafka_to_twitter.py by exceuting : python Kafka_to_twitter.py

Step 2: Run sentimental Analysis on the tweets

This project has two datasets:
Positive.txt : Set of positive words
Negative.txt : Set of negative words
These help us identify the positive and negative tweets.

SentimentalAnalysis.py file has the code to apply sentimental analysis on the tweets.

Plot and Output.txt contain the plot of word counts vs time for positive and negative tweets and output has the counts of each positve ad negative tweets which are returned in the form of RDD.





