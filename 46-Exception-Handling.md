```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		// exception = 	an event that occurs during the execution of a program that,
		//				disrupts the normal flow of instructions.
		//			 =  an error.
		// Examples = ArithmeticException, ArrayIndexOutOfBoundsException, InputMismatchException, NullPointerException etc.
		
		Scanner scanner = new Scanner(System.in);
		
		try {
			// Inside try block we store the code lines in which there is a chance of occuring some error.
			
			System.out.println("Enter a whole number to divide: ");
			int x = scanner.nextInt();
		
			System.out.println("Enter a whole number to divide by: ");
			int y = scanner.nextInt();
		
			int z = x/y;
		
			System.out.println("result: " + z);
		}

		// catch(ArithmeticException e) {	
		// 	// ArithmeticException is the type of exception we want to catch.	
		// 	System.out.println("You can't divide by zero! IDIOT!");
		// }

		// catch(InputMismatchException e) {
		// 	// InputMismatchException is the type of exception we want to catch.
		// 	System.out.println("PLEASE ENTER A NUMBER OMFG!!!");
		// }

		// Multi-Catch Block
		catch(ArithmeticException | InputMismatchException e){
			System.out.println("Either you are trying to divide by zero OR you have entered a non-integer input - YOU DUMBASS !");
		}

		catch(Exception e) {
			// This catch block catches any/all other type of exceptions. Always put this block AFTER the specific exception blocks - otherwise this will give error.
			System.out.println("Something went wrong");
		}

		finally {
			// A finally block will always execute whether or not we catch an exception.
			scanner.close();

            System.out.println("Hey you are so awesome !");  // Hey you are so awesome !

			System.exit(-1);  //  when the program encounters System.exit(-1), the program execution stops right there.

			System.out.println("Hey you are so awesome !");  // This line of code will not execute.
		}
	}
}
```
