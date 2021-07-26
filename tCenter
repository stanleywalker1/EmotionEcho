class tCenter{
  // draws the gradient circle in the center of the canvas 
  
  int dim; 

  void setC(){             
    dim = 100;
    colorMode(HSB, 360, 100, 100);  // need HSB color mode to acheive the right effect
    
    noStroke();
    ellipseMode(RADIUS);      
  }
  
  void displayC(){   
 // if(frameCount % 30 == 0) {         // Adjust FR if I decided to implement a changing gradient   
    drawGradient(width/2, height/2);   
  //  }
  }
  
 // set Gradient colors accordingly 
  void drawGradient(float x, float y){
    int radius = dim/2;
    float h = 180;
    for (int r = radius; r > 0; --r){
     fill(h, 90, 90);
     ellipse(x, y, r, r);
     h = (h+1)%360;
    }
  }
 
}
