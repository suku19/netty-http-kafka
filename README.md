# netty-http-kafka

Apache Kafka Configuration:

Step 1: Download the code

Download the 1.0.1 release and un-tar it.
1
2
> tar -xzf kafka_2.11-1.0.1.tgz
> cd kafka_2.11-1.0.1


Step 2: Start the ZooKeeper server

C:\apache\kafka_2.11-1.0.1\bin\windows>kafka-server-start ..\..\config\server.properties
 
Start the Kafka server:

C:\apache\kafka_2.11-1.0.1\bin\windows>zookeeper-server-start C:\apache\kafka_2.11-1.0.1\config\zookeeper.properties
 

Step 3: Create a topic

C:\apache\kafka_2.11-1.0.1\bin\windows>kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
N.B. Topic name Should be test, or else need to modify in “/netty-http-kafka/src/main/resource/config.properties”

 

We can now see that topic if we run the list topic command:
C:\apache\kafka_2.11-1.0.1\bin\windows>kafka-topics --list --zookeeper localhost:2181

Step 4: Send some messages through comand prompt (Optional)

C:\apache\kafka_2.11-1.0.1\bin\windows>kafka-console-producer --broker-list localhost:9092 --topic test
This is a message
This is another message
 
Step 5: Start a consumer to verify message send

C:\apache\kafka_2.11-1.0.1\bin\windows>kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
This is a message
This is another message

 

Reference: https://kafka.apache.org/quickstart 
 

How to Run netty-http-kafka

Step 1: Setup Apache Kafka Configuration First
Step 2: Import “netty-http-kafka” as Existing maven Project
Step 3: Right Click -> Maven -> Update Project (Maven should be configured and system should be connected with internet)
Step 4: Run NettyWebServerMain.java. Right Click ->Run As -> Java application
Step 5: Access the server through brouser
 
Step 5: Verify Query parameter in Kafka Consumer Console
 



