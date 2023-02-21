# Realtime-bitcoin-pricepredictor-using-kafka
This is a real time Bitcoin Price Predictor using Apache Kafka,AWS S3 bucket for storage and LSTM(Machine Learning Model).

Tech Stack Required: Apache Kafka, AWS S3 Storage and retrival system, Neural Networks(LSTM), Python(Pandas,Numpy, Scikit-learn, Matplotlib etc)

#Seqeunce of Steps:

Step1: Create a Kafka Producer for reading data from CoinMarketCap REST API into Kafka.

Step2: Create a Kafka Consumer for reading data from Kafka and writing into S3 Bucket. Here I used S3 bucket for storing the data so it can used in the feature. If you          dont want to store you can skip S3 bucket and feed consumer output to LSTM Model.

Step3: This step is crucial in the project. It is expalined in the Model_FlowChart.png clearly.

       i) Initially I am using an external database for training the model.
       
       ii) Split the dataset for training and testing purpose and transform the data as per the model input.
       
       iii) Then create a LSTM Neural network model and train it.
       
       iv) Load the data from S3 buckets and do necessary transformations.
       
       v) now you can find real time streaming output.
       

#PitFalls:

**Note this is my first project of creating ETL Pipelines. So there are some mistakes taken place that I would correct. Few of they I observed are:

       1. The model is good at analyzing trend but predicted values are varying from real time values.
       
       2. I am using a local machine as my kafka server but this can be repalced with platforms like Confluent, EC2 instance where you can get more brokers
       
       3. There is a deficieny providing interactive dashboards. I will be adding in due course of time.


#Further Improvements:

       1. Add Twitter-Tweet Sentiment as most of investors follow twitter for latest updates.(This is another huge branch of proccess as it needs to get data from twitter API,    need cleaning and transforming data, need language conversions if not english , analyze sentiment etc)
       
       2. Improve the model for more cryto currencies
       
       3. Make the model train on new dataset periodically like training once a week so it get paced with data in timely manner.
       

