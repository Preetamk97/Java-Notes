# Main.java

```java
public class Main {

	public static void main(String[] args) {
		
		//local =  declared inside a method
		//		   visible only to that method
		  
		//global = declared outside a method, but within a class
		//		   visible to all parts of a class
		  
		  DiceRoller diceRoller = new DiceRoller();
	}

}
```

# DiceRoller.java

```java
import java.util.Random;

public class DiceRoller {
		
	//Global Scope Variables : Declared inside the class but outside any method.
	//***********************
	 int number;
	 Random random = new Random();
	 
	 DiceRoller(){
		//Local Scope Variables : Declared inside a method.
		//**********************
//		 int number;
//		 Random random = new Random();
		// If we would have created these two variables inside the DiceRoller constructor method, their scope would have been local. So, they would not have been visible to the roll()  function. 
		 roll();
	 }
	 
	 void roll() {
	  number = random.nextInt(6)+1;  // 0-5 + 1
	  // Above line of code will give error if 'int number' variable & 'Random random' object would have been declared inside the DiceRoller() as their scope would have been local and they would have been only visible to the DiceRoller constructor method and not to roll() method. 
	  System.out.println(number);
	 }
}
```

# Alternative Code of DiceRoller.java  

```java
import java.util.Random;

public class DiceRoller {
	 
	 DiceRoller(){
		//Local Scope Variables
		//**********************
		 int number = 0;
		 Random random = new Random();

		 roll(number, random);
	 }
	 
	 void roll(int number, Random random) {
	  number = random.nextInt(6)+1;  // 0-5 + 1 
	  System.out.println(number);
	 }
}
```