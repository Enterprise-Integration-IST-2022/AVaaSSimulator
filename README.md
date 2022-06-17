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
java -jar AVaaSSimulator.jar 
```
```
The usage of the Message Producer for AVaaS is the following.

AVaaSSimulator --broker-list <brokers> --throughput <value> --typeMessage <value> --filterprefix <value> 
where, 
--broker-list: is a broker list with ports (e.g.: kafka02.example.com:9092,kafka03.example.com:9092), default value is localhost:9092
--throughput: is the approximate maximum messages to be produced by minute, default value is 10
--typeMessage: is the type of message to be produced: JSON or XML, default value is JSON
--filterprefix: is the prefix to be filtered. Only the topics starting with this prefix will be considered to sending messages.
```

One example of an AV_Event message sent, in JSON, to the dicovered topic in Kafka is:
```
{"AV_Event":
	{
		"TimeStamp":"2022-02-04 14:49:07.401",
		"AV_ID":"Toyota-with-driver259876",
		"Speed":"49",
		"BatteryLevel":"10",
		"DriverTirenessLevel":"85",
		"Location":"38.735330392 -9.13666612",
		"EnvironmentalLightning":"Good",
		"RainConditions":"Light Rain",
		"FogConditions":"None",
		"TractionWheelsLevel":"25"
	}
}
```
