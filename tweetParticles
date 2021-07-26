class tweetParticles {
  
// Reference to Stroke Generation in the documentation for more information 
 
// ******** COLOR PALLETTES ********  
  color[] emotionC = {color(24, 78, 119),color(30, 96, 145),color(26, 117, 159),
          color(22, 138, 173),color(52, 160, 164), color(82, 182, 154), 
          color(118, 200, 147), color(153, 217, 140), 
          color(181, 228, 140),color(217, 237, 146)}; // https://coolors.co/d9ed92-b5e48c-99d98c-76c893-52b69a-34a0a4-168aad-1a759f-1e6091-184e77
 
  color[] emotionC2 = {color(116, 0, 184), color(105, 48, 195), color(94, 96, 206), 
  color(83, 144, 217), color(78, 168, 222), color(72, 191, 227),
  color(86, 207, 225), color(100, 223, 223), 
  color(114, 239, 221), color(128, 255, 219)}; // https://coolors.co/7400b8-6930c3-5e60ce-5390d9-4ea8de-48bfe3-56cfe1-64dfdf-72efdd-80ffdb

  color[] emotionC3 = {color(8, 28, 21), color(27, 67, 50), color(45, 106, 79),
  color(64, 145, 108), color(82, 183, 136), color(116, 198, 157),
  color(149, 213, 178), color(183, 228, 199), 
  color(216, 243, 220), color(216, 243, 220)}; // https://coolors.co/d8f3dc-b7e4c7-95d5b2-74c69d-52b788-40916c-2d6a4f-1b4332-081c15
  
  color[] emotionC4 = {color(3, 7, 30), color(55, 6, 23), color(106, 4, 15),
  color(157, 2, 8), color(208, 0, 0), color(220, 47, 2),
  color(232, 93, 4), color(244, 140, 6), 
  color(250, 163, 7), color(255, 186, 8)};  // https://coolors.co/03071e-370617-6a040f-9d0208-d00000-dc2f02-e85d04-f48c06-faa307-ffba08
  
  color[] emotionC5 = {color(255, 123, 0), color(255, 136, 0), color(255, 149, 0),
  color(255, 162, 0), color(255, 170, 0), color(255, 183, 0),
  color(255, 195, 0), color(255, 208, 0), 
  color(255, 221, 0), color(255, 234, 0)};  //https://coolors.co/ff7b00-ff8800-ff9500-ffa200-ffaa00-ffb700-ffc300-ffd000-ffdd00-ffea00
  
  color[] emotionC6 = {color(3, 4, 94), color(2, 62, 138), color(0, 119, 182),
  color(0, 150, 199), color(0, 180, 216), color(72, 202, 228),
  color(144, 224, 239), color(173, 232, 244), 
  color(202, 240, 248), color(215, 243, 248)};  //https://coolors.co/ff7b00-ff8800-ff9500-ffa200-ffaa00-ffb700-ffc300-ffd000-ffdd00-ffea00

// ******** ARRAY OF ALL PALLETTES ******** 
  color[][] mainPallete = {emotionC, emotionC2, 
    emotionC3, emotionC4,
    emotionC5, emotionC6};
  
// Initialize variables 
  int index;
  float x;
  float y;
  float deg = 0;
  float radius = 50;                  // starting point  
  float radiusStep = random(0.5, 3);  // slow or fast
  float size = 5;                     // size of each circle
  float sizeT = 0.0;
  float sizeTs = random(0.1, 0.5);
  float tn = 0.0;  
  float tns = random(0.001, 0.005);
  float alpha = 70;
  int colorIndex;
  
  // Mirrored values
  float x1;
  float y1;
  float deg1 = 0;
  float size1 = 5;
  float sizeT1 = 0.0;
  float sizeTs1 = random(0.1, 0.5);
  float tn1 = 0.0;  
  float tns1 = random(0.001, 0.005);

 
  // Main Constructor
  tweetParticles(int x, int c){
     index = x;
     colorIndex = c;
  }
  
  void step(){
   // **** Movement for the line ****
   deg = map(noise(tn + index), 0, 1, -360, 360);  // random degree value
   x = radius*sin(radians(deg))+ width/2;          // X movement
   y = radius*cos(radians(deg))+height/2;          // Y movement
   tn += tns;                                      // increasing noise variable
   size = 10 * noise(sizeT + index);               // adjusting size of the circles
   sizeT += sizeTs;                                // increasing noise variable
   radius += radiusStep;                           // growing the radius that the
                                                   // movement is based on
     
   // **** Movement for the mirrored line ****
   deg1 = map(noise(tn1 + index), 0, 1, -360, 360);
   x1 = radius*cos(radians(deg))+width/2;          // Only difference is 
   y1 = radius*sin(radians(deg))+height/2;         // swapped cos/sin
   tn1 += tns1;  
   size1 = 10 * noise(sizeT1 + index);
   sizeT1 += sizeTs1;

  }   
  
  // ******** DRAW ********  
  void display(){
   // rotate(radians(random(360)));  //experimental 
   // rotate(radians(180));          //experimental 
    noStroke();
    fill(mainPallete[cI][colorIndex]); 
    ellipse(x, y, size, size);
    ellipse(x1, y1, size1, size1);
  } 
  
}
