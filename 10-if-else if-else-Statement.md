```java
public class Main {

	public static void main(String[] args) {
		
		// if statement = performs a block of code if it's condition evaluates to be true
		
		int age = 75;
		
		if(age=>75) {
			System.out.println("Ok Boomer!");
		}
		// If the above condition (age>=75) holds to be true, then the compiler will execute the code inside the if block (System.out.println("Ok Boomer!");) and will skip going through rest of the elseif & else blocks.
		else if(age>=18) {
			System.out.println("You are an adult!");
		}
		else if(age>=13) {
			System.out.println("You are a teenager!");
		}
		else {
			System.out.println("You are just a child!");
		}
				
	}
}
```