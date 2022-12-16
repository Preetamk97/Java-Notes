```java
// Program for Swapping Values Of Two Variables (x & y) in Java

public class Main {
	
	public static void main(String[] args) {
		
		String x = "Pritam";
		String y = "Rohit";
		
		// Before Swapping:
		System.out.println("x = " + x);
		System.out.println("y = " + y);
		//x = Pritam
		//y = Rohit
		
		// Swapping values of x & y
		//***************************
		
		// Creating an empty String type variable temp.
		String temp;
		
		// Storing the value of x inside temp.
		temp = x;
		
		// Replacing the current value of x with that of y.
		x = y;
		
		// Replacing the current value of y with that of temp.
		y=temp;
		
		System.out.println("x = " + x);
		System.out.println("y = " + y);
		//x = Rohit
		//y = Pritam	
	}
}
```