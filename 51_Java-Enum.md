```java
// An 'enum' is like a class which has got a fixed (constant) & limited number of objects. In the below example (enum Planet), ,we have used only 1 int type attribute (int number) to associate with the enum objects. But in practise, each object can be associated with any number of attributes & of any dataType.

public enum Planet {
	//enum = enumerated (ordered listing of items/constants in a collection) = similar to a class.
	//enum constants cannot be changed after the program compiles/runs.
	//grouping of constants that behave similarly to objects
	//We can associate a number with each of the enum constants/objects.
	
	//Planet enum constants/objects.
    //All the enum constants must be written in CAPITAL LETTERS.
	MERCURY(1), VENUS(2), EARTH(3), MARS(4), JUPITER(5), SATURN(6), URANUS(7), NEPTUNE(8), PLUTO(9);
	
	//attribute for the associated value of the enum constants.
	int number;
	
	//enum constant constructor
	Planet(int number){
		this.number = number;
	}
}

public class Main {

	public static void main(String[] args) {
        
        //creating an instance of enum Planet
		Planet myPlanet = Planet.PLUTO;
		
		canILiveHere(myPlanet);
	}
	
	static void canILiveHere(Planet myPlanet){
		
		switch(myPlanet) {
		case EARTH:
			System.out.println("You can live here :)");
			System.out.println("This is planet #"+myPlanet.number);
			break;
		default:
			System.out.println("You can't live here...yet");
			System.out.println("This is planet #"+myPlanet.number);
			break;
		}
	}
}
```