tAdapter adapter;  // adapter to read from MQTT
tCenter center;
PFont f; 
int index = 0;
int tweetCount = 0;
int cI = (int)random(0,5);  // random Color pallette 


ArrayList<tweetParticles> human = new ArrayList<tweetParticles>();


void setup() 
{
  size(1400, 800);
//  size(1900, 1050);
  background(255);
  f = createFont("YuGo-Bold",30,true);
    
  adapter = new tAdapter();
  client = new MQTTClient(this, adapter);
  // connect to server
  client.connect("mqtt://tweets:WJf9NORARuu82yUA@tweets.cloud.shiftr.io", "processing");
  
  center = new tCenter();
}

// method for handling incoming values
  void tweetOutput(float tV) {
    
    int m = month();  // Months 1 - 12
    int d = day();    // Days 1 - 31
    int h = hour();    // Hours 0 - 23
    int mi = minute();  // Mins 0 - 59
    int s = second();  // Sec 0 - 59
      
   // depending on the setiment value received from Node-Red, 
   // create and object with the cooresponding color tone
      if(tV <= -8){                             
      human.add(new tweetParticles(index, 0)); 
      } else if ( tV <= -6 && tV > -8){
      human.add(new tweetParticles(index, 1));
      } else if (tV <= -4 && tV > -6) {
      human.add(new tweetParticles(index, 2));
      } else if (tV <= -2 && tV > -4){
      human.add(new tweetParticles(index, 3));
      } else if (tV <= 0 && tV > -2){
      human.add(new tweetParticles(index, 4));
      } else if (tV <= 2 && tV > 0){
      human.add(new tweetParticles(index, 5));
      } else if (tV <= 4 && tV > 2){
      human.add(new tweetParticles(index, 6));
      } else if (tV <= 6 && tV > 4){
      human.add(new tweetParticles(index, 7));
      } else if (tV <= 8 && tV > 6){
      human.add(new tweetParticles(index, 8));
      } else if (tV <= 10 && tV > 8){
      human.add(new tweetParticles(index, 9));
      } 
      
      // when 100 is received, clear the canvas
      if(tV == 100){                                    
      background(255);                 
      human.clear();
      tweetCount = 0;
      cI = (int)random(0,5);
      }
      
      // when 99 is received save image
      if(tV == 99){
        saveFrame(m+"-"+d+"-"+h+":"+mi+":"+s+"-"+"tweet.png");     
      }
      index++;
      tweetCount++;
  }
  
  void resetArt(){
    int m = month();  // Months 1 - 12
    int d = day();    // Days 1 - 31
    int h = hour();    // Hours 0 - 23
    int mi = minute();  // Mins 0 - 59
    int s = second();  // Sec 0 - 59
    
    // in order to avoid hitting twitters API rate limit, max out at 70 tweets
    // proceed to save and clear canvas
     if(tweetCount == 71){
          println("MAXED OUT");
          saveFrame(m+"-"+d+"-"+h+":"+mi+":"+s+"-"+"tweet.png");
          human.clear();
          delay(15000);
          background(255); 
          tweetCount = 0;
          cI = (int)random(0,5);
    }
  }
  

void draw() {  
    resetArt();
    center.setC();
    center.displayC();
    colorMode(RGB, 255, 255, 255);
    ellipseMode(CENTER);

    // as objects are added to the arrayList, draw them 
     for (int i = 0; i < human.size(); i++){
        human.get(i).step();
        human.get(i).display();
    // for the tweet counter in top left
        fill(255);
        rect(0, 0, 60, 32);
        textFont(f,30);
        fill(60, 50);
        text(tweetCount, 10, 30);   
    }

}
