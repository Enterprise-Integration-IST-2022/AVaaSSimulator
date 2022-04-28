# AVaaSSimulator
IE 2021/2022 tool to simulate the Cars Activity for AVaaS, using Kafka Producer 

The tool starts by discovering all the topic available in the kafka cluster and then randomize messages for all that discoverd topics.
You are free to customize the tool accordingly with your needs. If so, create a pull request to change this repository.

Verify if JAVA 15 is available using the command: 

```
java -version
```

Then, to execute the generator of messages use the following command from the target directory:
```
java -jar .\AVaaSSimulator.jar 
```
```
The usage of the Message Producer for AVaaS is the following.

AVaaSSimulator --broker-list <brokers> --throughput <value> --typeMessage <value> 
where, 
--broker-list: is a broker list with ports (e.g.: kafka02.example.com:9092,kafka03.example.com:9092), default value is localhost:9092
--throughput: is the approximate maximum messages to be produced by minute, default value is 10
--typeMessage: is the type of message to be produced: JSON or XML, default value is JSON
```

One example of an AV_Event message sent, in JSON, to the dicovered topic in Kafka is:
```
{"AV_Event":{"TimeStamp":"2022-04-28 14:47:40.717","AV_ID":"StatusSIMCARD","Speed":"8","BatteryLevel":"62","DriverTirenessLevel":"33","Location":"38.73730834347317, -9.302641438338373","EnvironmentalLightning":"Very Good","RainConditions":"Light Rain","FogConditions":"Dense Fog","TractionWheelsLevel":"74"}}
```
One example of an AV_Event message sent, in XML, to the dicovered topic in Kafka is:
```
<AV_Event><TimeStamp>2022-04-28 15:06:56.58</TimeStamp><AV_ID>test</AV_ID><Speed>96</Speed><BatteryLevel>86</BatteryLevel><DriverTirenessLevel>50</DriverTirenessLevel><Location>38.73730834347317, -9.302641438338373</Location><EnvironmentalLightning>Sufficient</EnvironmentalLightning><RainConditions>Heavy Rain</RainConditions><FogConditions>Dense Fog</FogConditions><TractionWheelsLevel>4</TractionWheelsLevel></AV_Event>
```
