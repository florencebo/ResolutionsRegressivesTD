ResolutionsRegressivesTD
========================

package objectorientedfiguration;

import processing.core.PApplet;
import processing.core.PImage;


public class Objectorientedfiguration extends PApplet {

	
	private PImage img;
	boolean recordP; 
	boolean recordI;

	Ligne maligne;
	
	
	public void setup() {
		
		size(400, 598, P2D);
		  img = loadImage("_BRU0276 petit.jpg");
		  img.resize(width, height); 
		  img.loadPixels();

		  maligne = new Ligne(this);
	}

	public void draw() {
		 maligne.run();
	}
	
	public static void main(String _args[]) {
		PApplet.main(new String[] { objectorientedfiguration.Objectorientedfiguration.class.getName() });
	}
}

package objectorientedfiguration;

import processing.core.PApplet;

public class Ligne {
	 float tour;
	  float m;
	  Objectorientedfiguration p5;
	  
	  Ligne(Objectorientedfiguration _p5){
		  p5 = _p5;
		  
	  }
	  
	  void run () {
	    display ();
	  }


	  void display () {

	    int width;
		for ( int i = 0; i<width; i = i+12) {
	      int height;
		for ( int y = 0; y<height; y = y+10) {
	       // rectMode(CENTER);
	        p5.noStroke();
	        p5.smooth();
	        
	        p5.pushMatrix();
	        
	        tour = tour/255;
	        tour = tour*12; 
	        
	        p5.translate(i, y);
	        p5.color pix = img.get(i, y);
	        float phase = (i+y/2)/(tour+1)*2;
	        float PI = 3.1415f;
			if (millis()<5000) {
	          p5.rotate((float) (millis() * 0.00005 * PI) );
	          //if ( rotate == PI) {
	          // rotate(millis() * 0.00005 * -PI);;
	          // }
	        } 
	        else {
	          p5.rotate((millis() * 0.00005 * -PI));
	        }
	        p5.rotate(PApplet.radians(m*1)+phase); 
	        p5.translate(-i, -y);
	        fill(pix);
	        println(millis());

	        p5.rect(i, y, 20, 2);

	        p5.popMatrix();
	      }
	    }
	  }

	private void println(int millis) {
		// TODO Auto-generated method stub
	}

	private int millis() {
		// TODO Auto-generated method stub
		return 0;
	}

}

