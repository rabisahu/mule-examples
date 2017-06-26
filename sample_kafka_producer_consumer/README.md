About:
------
This is a sample mule project connects to Apache kafka with producer & consumer flows.
Go through below setup steps to install kafka in your local(windows OS) Anypoint Studio and quickly test your mule flow.


Installation: 
-------------
As per Mulesoft release notes current Apache Kafka Connector 1.0.2 released on March 31, 2017 needs 3.7.0 and higher enterprise edition compatible with Apache Kafa 0.9.0.0
You can install Apache Kafka Connector (Mule 3.7+)

Next you need to download kafka_2.11-0.9.0.0.tgz from https://kafka.apache.org/downloads. Explode the package to a windows directory (say D:\ drive).

Start Zookeeper:
---------------
Go to – D:\kafka_2.11-0.9.0.0 and open command prompts to execute below:-
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

Start Kafka Server:
----------------------
Go to – D:\kafka_2.11-0.9.0.0 and open command prompts to execute below:-
 .\bin\windows\kafka-server-start.bat .\config\server.properties
 
Create a Topic:
----------------
Go to D:\kafka_2.11-0.9.0.0\bin\windows and open command prompt to execute below
kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 2 --topic mykafkatopic

Test the flow: 
------------
Once Mule project is up and running, you can publish some test messages to http://localhost:8081/kafka and see the message being pushed to Topic by producer flow and being consumed by Consumer flow.
