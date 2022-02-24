# MongoDB_Kafka
In this project we used python to create a connction with 
#### MongoDB:
#Establish connection
connection = MongoClient('localhost' , 27017)
db = connection.EmployeeDB

and 

#### Kafka:
Producer = KafkaProducer(bootstrap_servers='localhost:9092',value_serializer=lambda x: x.encode('utf-8'))
Producer.send("Kafka-Topic", message)

After that, Insert new data into MongoDB Collection throw the same jupyter Notebook then retrieve the new updated collection, Convert it to dataframe use it as a kafka producer, Then create a consumer to read the streaming data.

**Note** : You have to run zookeeper and Establish a kafka connection at first of all and also run a MongoDB server of the needed collection:
from kafka dir > right click > choose run git bash:
$ bin/zookeeper-server-start.sh config/zookeeper.properties
$ bin/kafka-server-start.sh config/server.properties
Then create a topic ( This source is awesome for kafka starting: https://kafka.apache.org/quickstart )

And this is a source for inserting and retrieving data from a MongoDB collection: ( https://realpython.com/introduction-to-mongodb-and-python/ )
### Tools:
1. Jupyter Notebook Must:(pip install MongoClient,kafka-python)
2. MongoDB (shell or compass)
3. Apache Kafka
