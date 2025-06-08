Week8
Tutorial 1: Kafka
1. build c5.Large Ubuntu standard
2. initiate 4 connection terminals
3. run code
   curl -o kafka_2.13-3.4.0.tgz http://dlcdn.apache.org/kafka/3.4.0/kafka_2.13-3.4.0.tgz
   tar -xzf kafka_2.13-3.4.0.tgz
   cd kafka_2.13-3.4.0/
   sudo apt update
   sudo apt install default-jre
   java -version
   bin/zookeeper-server-start.sh config/zookeeper.properties
4. switch to terminal 2
5. run code
   cd kafka_2.13-3.4.0/
   bin/faka-server-start.sh config/server.properties
6. switch to terminal 3
7. run code
   cd kafka_2.13-3.4.0/
   bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
8. switch to terminal 4
9. run code
    cd kafka_2.13-3.4.0/
   bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
10. back to terminal 3
11. test a message
12. demonstrate consuption in terminal 4 & exit
13. back to T3 and exit
14. run code
    sudo apt install golang-go
    vi prod.go
    #paste script (replace dns)
15. fix security roles
16. finish build
    go mod init kafka-golang
    go mod tidy
    vi cons.go
    #paste script
    go run prod.go
17. switch to terminal 4
18. run code
    go run cons.go
