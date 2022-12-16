```java
// Taking User Input in Java.

import java.util.Scanner;
// To take User Inputs we need to import Scanner class 
// from the the utility package of Java Library.

public class Main {
	
	public static void main(String[] args) {
		
		// Creating a Scanner class object 
		// Taking System.in as argument.
		Scanner scanner = new Scanner(System.in);
		
		//-----------------------------------------------------------------------------
		// Taking a string value from the user 
		System.out.println("Tell me your name?");
		// Using Scanner class object scanner.
		// And storing the recieved value inside the String type variable name.
		String name = scanner.nextLine();
		//.nextLine signifies that we are going to take a String value.
		//--------------------------------------------------------------------------------
		
		// -----------------------------------------------------------------------------------
		// Taking an int value from the user.
		System.out.println("How old are you?");
		int age = scanner.nextInt();
		// .nextInt signifies that we are going to take an int type value.
		//----------------------------------------------------------------------------------
		
		//----------------------------------------------------------------------------------
		// A Common Problem of Using scanner.nextLine() after using scanner.nextInt() or anything other scanner method.
		//*************************************************************************************
		
		// Important
		scanner.nextLine();
		// Adding the above line of code is an essential step 
		// when we want to use scanner.nextLine() 
		// after using the scanner.nextInt() or anything other scanner method.
		// somewhere in the program before (line 35 above).
		System.out.println("What is your favourite food?");
		// If we comment out the code in line 35 (i.e. scanner.nextLine();)
		// then you will not see the execution of the below line of code
		// which uses a scanner.nextLine() to take a string value from the user.
		String food = scanner.nextLine();
		//-------------------------------------------------------------------------------------
		
		// Prints
		System.out.println("Hello " + name);
		System.out.println("You are " + age + " years old.");
		System.out.println("Your favorite foods is " + food);
		
		
		// Closing the scanner object. This is very important step.
		scanner.close();
	}
}
```