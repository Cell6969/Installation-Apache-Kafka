# Installation-Apache-Kafka

This tutorial for installation apache kafka on Ubuntu

Requuirement : <br>
1. Java 11
2. Apache Kafka <br>

## Steps : <br>
1. Install Java
```
sudo apt install openjdk-11-jre-headless -y
```
2. Download Kafka
```
wget https://downloads.apache.org/kafka/3.4.0/kafka_2.12-3.4.0.tgz
```
3. Extract Kafka and rename kafka untar folder to Kafka
```
tar -xvf kafka_2.12-3.4.0.tgz
mv kafka_2.12-3.4.0.tgz kafka
```
4. Create "data" folder on Kafka folder
```
cd kafka
mkdir data
```
5. On data folder create "server" dan "zookeeper" folder
```
cd data
mkdir server
mkdir zookeeper
```
6. Open zookeeper.properties:
```
nano ~/kafka/config/zookeeper.properties
```
and edit this line according to your path
```
dataDir = /home/<your user>/kafka/data/zookeeper
```
after that save and exit <br>

7. Open server.properties
```
nano ~/kafka/config/server.properties
```
and edit this lines according to your path
```
log.dirs = /home/<your user>/kafka/data/server
```
after that save and exit <br>

## Start Kafka
for starting kafka, first you can start zookeeper service first. Go into kafka directory
```
cd kafka
```
go on superuser mode
```
sudo su
```
after that run this line:
```
bin/zookeeper-server-start.sh config/zookeeper.properties
```
the result will be displaying like this:
![image](https://github.com/Cell6969/Installation-Apache-Kafka/assets/78861020/c59bb6ec-a6df-422a-987f-01c977af3f72)

This mean the zookeeper already running. Then for kafka you can create new tab and go on superuse mode. After that run this line:
```
bin/kafka-server-start.sh config/server.properties
```
the result will be displaying like this:
![image](https://github.com/Cell6969/Installation-Apache-Kafka/assets/78861020/0bb408e5-784a-4fc1-bedb-52159500075b)

This mean the kafka already running. From this point you can start create topic, produce message or something like that.
