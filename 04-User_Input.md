```java
// Java program to read data of various types using Scanner class.

import java.util.Scanner;
// To take User Inputs we need to import Scanner class 
// from the the utility package of Java Library.

public class Main {
	
	public static void main(String[] args) {
		
		// Creating a Scanner class object 
		// Taking System.in as argument.
		Scanner scanner = new Scanner(System.in);

		//-----------------------------------------------------------------------------
		// Taking a single word as string input
		System.out.println("Type \"start\" and press ENTER !");
		String response = scanner.next();
		// // .next() will store the next complete word that you enter.
		// // If we enter "Java Programming Is a Pain!" as user input, 
		// // .next() will take only the first word "Java" and store it inside `String response` variable.
		// // But .nextLine() takes the complete line of "Java Programming Is a Pain!" as a value 
		// // and stores it inside the assigned variable.
		System.out.println("Your response is : "+response);
		//-----------------------------------------------------------------------------

		
		// Important Step : Before using a scanner operation again after using scanner.next()
		scanner.nextLine();
		// If you comment out the above line of code, this program will skip the execution of the next scanner operation.
		

		//-----------------------------------------------------------------------------
		// Taking a complete sentence as a string input
		System.out.println("Tell me your name?");

		// String Input
		String name = scanner.nextLine();
		// Using Scanner class object scanner.
		// And storing the recieved value inside the String type variable name.
		//.nextLine signifies that we are going to take a complete line as a String value.
		//--------------------------------------------------------------------------------
		
		// -----------------------------------------------------------------------------------
		// Integer Input
		System.out.println("How old are you?");
		int age = scanner.nextInt();
		// .nextInt signifies that we are going to take an int type value.
		//----------------------------------------------------------------------------------
		
		//----------------------------------------------------------------------------------
		// A Common Problem of Using scanner.nextLine() or any other scanner method() after using scanner.nextInt()
		//*************************************************************************************
		
		// Important
		scanner.nextLine();
		// Adding the above line of code is an essential step 
		// when we want to use scanner.nextLine() or any other scanner method() after using scanner.nextInt() 

		System.out.println("What is your favourite food?");
		// If we comment out the code scanner.nextLine() above this line of code;
		// then you will not see the execution of the below line of code
		// which uses a scanner.nextLine() to take a string value from the user.
		String food = scanner.nextLine();
		//-------------------------------------------------------------------------------------

		//--------------------------------------------------------------------------------------
		System.out.println("What is your Gender?");
		// Char Input
		char gender = scanner.next().charAt(0);
		//----------------------------------------------------------------------------------------

		//----------------------------------------------------------------------------------------
		System.out.println("What is your Phone Number?");
		// Long Input
		long phoneNumber = scanner.nextLong();
		//----------------------------------------------------------------------------------------

		//----------------------------------------------------------------------------------------
		System.out.println("What is your cgpa?");
		// Double Input
		double cgpa = scanner.nextDouble();
		//----------------------------------------------------------------------------------------

		// Prints
		System.out.println("Hello " + name);
		System.out.println("You are " + age + " years old.");
		System.out.println("Your favorite foods is " + food);
		System.out.println("Your gender is " + gender);
		System.out.println("Your phone number is " + phoneNumber);
		System.out.println("Your cgpa is " + cgpa);
		
		
		// Closing the scanner object. This is very important step.
		scanner.close();
	}
}
```