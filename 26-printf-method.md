```java
public class Main {

	public static void main(String[] args) {

		// printf() = 	an optional method to control, format, and display text to the console window
		// It takes two arguments = string + (object/variable/value)
		// % [flags] [precision] [width] [conversion-character]
				
		boolean myBoolean = true;
		char myChar = '@';
		String myString = "Bro";
		int myInt = 50;
		double myDouble = -1000;
			
		
		System.out.println("conversion-character");
		System.out.println("**********************");	
		// [conversion-character]
		System.out.printf("This is my boolean %b.",myBoolean);
		System.out.println();
		System.out.printf("This is my character %c",myChar);
		System.out.println();
		System.out.printf("This is my string %s",myString);
		System.out.println();
		System.out.printf("This is my integer %d",myInt);
		System.out.println();
		System.out.printf("This is my double %f",myDouble);
		
		
		System.out.println();
		System.out.println();
		System.out.println("width");
		System.out.println("******");	
		//[width]
		//total number of character spaces to be acquired for printing the variable.
		System.out.printf("Hello %10s",myString);
		// In this case, myString = "Bro" contains and contains 3 characters and needs 3 character spaces for printing in console.
		// But instead, "bro" takes 10 total character spaces while getting printed in console.
		// "Hello        Bro"
		
		
		System.out.println();
		System.out.println();
		System.out.println("precision");
		System.out.println("***********");
		//[precision]
		// sets number of digits of precision when outputting floating-point values
		System.out.printf("You have this much money %.4f",myDouble);
        // "You have this much money -1000.0000"
		
		
		System.out.println();
		System.out.println();
		System.out.println("flags");
		System.out.println("********");
		// [flags]
		// adds an effect to output based on the flag added to format specifier
		
		// - : left-justify
		System.out.printf("Hello %-10s",myString);  // "Hello Bro       "
		System.out.println();
		
		// + : on putting a plus ( + ) sign before the conversion-character (only for a numeric value i.e %+d or %+f), this prints the number with a (+) sign if the number is positive and with a (-) sign if the number is negative.
		System.out.printf("This is my double %+f",myDouble); // "This is my double -1000.000000"
		System.out.println();
		
		// 0 : putting 0, infront of the [width] fills all the empty character spaces with zeroes(0's).
		System.out.printf("This is my double %20f",myDouble); // This is my double         -1000.000000
		System.out.println();
		System.out.printf("This is my double %020f",myDouble); // This is my double -000000001000.000000
		System.out.println();
		
		// , : comma grouping separator (for every 3 zeroes) if numbers > 1000
		System.out.printf("This is my double %,f",myDouble);  // This is my double -1,000.000000
	}
}
```