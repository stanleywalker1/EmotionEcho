// Connects to the public shiftr.io instance
// by Joël Gähwiler
// https://github.com/256dpi/processing-mqtt
// Since this adapter is provived by Shiftr.io so only need to make minimal changes 

import mqtt.*;
MQTTClient client;
float tV; // setiment compare value

         

class tAdapter implements MQTTListener {
  void clientConnected() {
    println("client connected");
    client.subscribe("tweets");        // connect to my server topic
  }

  void messageReceived(String topic, byte[] payload) {
    String tweet = new String(payload);
    println("new message: " + topic + " - " + tweet); 
    tV = int(tweet);      
    tweetOutput(tV);                   // run through value handler method
  }

  void connectionLost() {
    println("connection lost");
  }
}
