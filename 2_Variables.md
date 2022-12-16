```java
public class Main {
	
	public static void main(String[] args) {
		
		int x; // Variable Declaration
		
		x = 123; // Variable Assignment
		
		int y = 145; // Variable Initialization
		
		System.out.println("x");	// Printing a String Literal.
		System.out.println(x);	// Printing the value of variable x.
		System.out.println(y); 	// Printing the value of variable y.
		System.out.println("Value of x is : " + x); 	// Printing a String and Variable together: String + Variable Concatenation
	}
}
```

```java
public class Main {
	
	public static void main(String[] args) {
		
		// byte Datatype
		byte age = 127;
		// The byte datatype variable can hold values from -128 to 127.
		
		//short Datatype
		short rollno = 32767;
		// The byte datatype variable can hold values from -32,768 to 32,767.
		
		// int Datatype
		int x = 256;
		
		// long Datatype
		long y = 156234555555556L;
		//  Number value must be followed with a L.
		
		// float Datatype
		float z = 3.14f;
		
		// double Datatype
		double p = 26.5889;
		// Double datatype variable can store upto 15 digits after the decimal.
		// Also, we do not need to add an `f` after the literal value.
		
		//boolean Datatype
		boolean q = false;
		boolean r = true;
		// booleans only hold true or false values.
		
		// char Datatype
		char symbol = '@';
		char letter = 'a';
		// Always wrap a char literal within single-quotes ('')
		
		// String Datatype
		String name = "Pritam";
		// `String` starts with capital S because String is a Reference Datatype.
		// All other datatypes are Primitive Datatypes.
		
		System.out.println("My name is " + name); // String + String Variable Concatenation
	}
}
```
