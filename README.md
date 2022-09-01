# rdbms_stream_to_neo4j

**step one**

Create debezium.json for add conector POstgreSql to Kafka
![image](https://user-images.githubusercontent.com/77326619/159642013-79247407-3deb-49eb-9f0b-b3eee84833da.png)

post bebas.json to kafka
```
curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" localhost:8083/connectors/ --data "@debezium.json"
```
![image](https://user-images.githubusercontent.com/77326619/159642492-6b70832c-7952-4d77-b7ce-543fe6e1e1a6.png)

after post list of your table will show in kafka topic
![image](https://user-images.githubusercontent.com/77326619/159654557-d2052ac4-e020-4567-bfe7-2cc351e2cff5.png)


```
bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic ddi-Aspire-E5-553G.public.user --from-beginning  | jq
```
test insert new row to table
![image](https://user-images.githubusercontent.com/77326619/159654203-d09ece4e-33c3-43be-b062-c1b08a048d34.png)

**step two**
create bebas.json 
![image](https://user-images.githubusercontent.com/77326619/159654810-2b455320-5fb1-49a3-a66a-5d3414bf9afa.png)

after create you need to post the bebas.json
```
curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" localhost:8083/connectors/ --data "@bebas.json"
```
and i will use one topic for 2 instance neo4j and postgresql

after that you need to test inser table and neo4j will create new nodes






