```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		// exception = 	an event that occurs during the execution of a program that,
		//				disrupts the normal flow of instructions.
		//			 =  an error.
		
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
		catch(ArithmeticException e) {	
			// ArithmeticException is the type of exception we want to catch.	
			System.out.println("You can't divide by zero! IDIOT!");
		}
		catch(InputMismatchException e) {
			// InputMismatchException is the type of exception we want to catch.
			System.out.println("PLEASE ENTER A NUMBER OMFG!!!");
		}
		catch(Exception e) {
			// This catch block catches any/all other type of exceptions.
			System.out.println("Something went wrong");
		}
		finally {
			// A finally block will always execute whether or not we catch an exception.
			scanner.close();
		}
	}
}
```