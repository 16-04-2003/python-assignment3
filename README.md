1.# underscore to omit the label arrays
(train_images, train_labels), (_, _) = tf.keras.datasets.mnist.load_data() 


train_images = train_images.reshape(train_images.shape[0], 28, 28, 1).astype('float32')
train_images = (train_images - 127.5) / 127.5 # Normalize the images to [-1, 1]

BUFFER_SIZE = 60000
BATCH_SIZE = 256

 2.# Batch and shuffle the data
train_dataset = tf.data.Dataset.from_tensor_slices(train_images).shuffle(BUFFER_SIZE).batch(BATCH_SIZBig data sets are often stored, or extracted as JSON.

JSON is plain text, but has the format of an object, and is well known in the world of programming, including Pandas.

In our examples we will be using a JSON file called 'data.json'.

Open data.json.

Example
Load the JSON file into a DataFrame:

import pandas as pd

df = pd.read_json('data.json')

 3.print(df.to_string()) A Dask DataFrame is a large parallel DataFrame composed of many smaller Pandas DataFrames, split along the index. These Pandas DataFrames may live on disk for larger-than-memory computing on a single machine, or on many different machines in a cluster. One Dask DataFrame operation triggers many operations on the constituent Pandas DataFrames.
4.Dask is a library that supports parallel computing in python. It provides features like-

Dynamic task scheduling which is optimized for interactive computational workloads
Big data collections of dask extends the common interfaces like NumPy, Pandas etc.
Why Dask?
Most of the BigData analytics will be using Pandas, NumPy for analyzing big data. All the mentioned packages support a wide variety of computations. But when the dataset doesn’t fit in the memory these packages will not scale. Here comes dask. When the dataset doesn’t “fit in memory” dask extends the dataset to “fit into disk”. Dask allows us to easily scale out to clusters or scale down to single machine based on the size of the dataset. 

Installation
To install this module type the below command in the terminal – 

python -m pip install "dask[complete]" 
Let’s see an example comparing dask and pandas. To download the dataset used in the below examples, click here.

1. Pandas Performance: Read the dataset using pd.read_csv()

import pandas as pd
5.Features of Cassandra
Difficulty Level : Basic
Last Updated : 15 Nov, 2021
Apache Cassandra is an open source, user-available, distributed, NoSQL DBMS which is designed to handle large amounts of data across many servers. It provides zero point of failure. Cassandra offers massive support for clusters spanning multiple datacentres. 

There are some massive features of Cassandra. Here are some of the features described below: 

Distributed: 
Each node in the cluster has has same role. There’s no question of failure & the data set is distributed across the cluster but one issue is there that is the master isn’t present in each node to support request for service.
Supports replication & Multi data center replication: 
Replication factor comes with best configurations in cassandra. Cassandra is designed to have a distributed system, for the deployment of large number of nodes for across multiple data centers and other key features too.
Scalability: 
It is designed to r/w throughput, Increase gradually as new machines are added without interrupting other applications.
Fault-tolerance: 
Data is automatically stored & replicated for fault-tolerance. If a node Fails, then it is replaced within no time.
MapReduce Support: 
It supports Hadoop integration with MapReduce support.Apache Hive & Apache Pig is also supported.
Query Language: 
Cassandra has introduced the CQL (Cassandra Query Language). Its a simple interface for accessing the Cassandra.
Cassandra Query Language (CQL) : 
CQL has simple interface for accessing the Cassandra, also an alternative for the traditional SQL. CQL adds an abstraction layer to hide the implementation of structure & also provides the native syntax for collections. 

For example please follow the given sample which shows how to create a keyspace including column family in CQL 3.0- 

CREATE KEYSPACE MyKeySpace
WITH REPLICATION = { 'class' : 'SimpleStrategy', 
                     'replication_factor' : 3 };

USE MyKeySpace;

CREATE COLUMNFAMILY MyColumns (id text, Last text, 
                               First text, PRIMARY KEY(id));

INSERT INTO MyColumns (id, Last, First) 
VALUES ('1', 'Doe', 'John'); 
Query:  

SELECT * FROM MyColumns; 
Which gives:  

id | First | Last
----+-------+------
1 | Ratul | Sarkar 
(1 rows) 

Some facts regarding Cassandra are as follows:  

Before the updates of versions of Cassandra, upto Cassandra 1.0, Cassandra wasn’t row level consistent, which means inserting & updating the table. It may affect the same row that are processed at approximately the same time may affect the non-key columns in a inconsistent manner. 
Cassandra 1.1 solved this using row level isolation.
Deletion of markers called the Tombstones (source Internet) are also known to causes performance degradation upto severe consequence levels.
Cassandra, essentially a hybrid between a key-value & a organised tabular DBMS.Tables can be created, dropped and altered at run time without blocking updates & queries.
A column family called table represents a RDBMS. Each row is specifically identified by a row & key, name, value, timestamp etc. A table in Cassandra is a disturbed multi dimensional map monitored by a key. Further more applications are specified by a super column family.
 
