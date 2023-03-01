```java
public class Main {

    // method = a block of code that is executed whenever it is called upon

    // Since we are calling the add(int, int) function inside the main() method which is a STATIC method, therefore, we also need to make the add() method STATIC.
	static int add(int x, int y) {
		
		int z = x + y;
		return z;	
	}
    // In the above function definition, (int x, int y) are called parameters.
	
	// Since we are calling the hello(String, int) function inside the main() method which is a STATIC method, therefore, we also need to make the hello(String, int) method STATIC.
	static void hello(String name, int age) {
		System.out.println("Hello "+name);
		System.out.println("Your age is "+age);
	}
    // In the above function definition, (String name, int age) are called parameters.
	
	// Driver Code:
	public static void main(String[] args) {
		
		int x = 3;
		int y = 4;
		
		// Calling method add(int , int)
		int z = add(x,y);  
		// In add(x,y), x & y are called arguments.
        // z = 7
		System.out.println(z);
		
		// Calling method hello(String, int)
		hello("Pritam", 25);  
		// Hello Pritam
		// Your age is 25.
		// In hello("Pritam", 25), "Pritam" & 25 are called an arguments.
	}	
}

// Important Difference Between Argument and String.
//*************************************************
// The values that are declared within a function when the function is called are known as an arguments. Wherease, the variables that are defined when the function is declared are known as a parameters.
```