```java
public class Main {
	
	public static void main(String[] args) {
		
		// Expression = operand + operator
		// operand = values, variables, numbers, quantities
		// operator = + - * / % etc.
		
		int friends = 10;
		
		// Arithmetic Operators
		//**********************
		
		friends = friends + 1; // 11
		System.out.println(friends);

		friends = friends - 1; // 10
		System.out.println(friends);

		friends = friends * 2; // 20
		System.out.println(friends);

		friends = friends / 5; // 4
		System.out.println(friends);

		friends = friends % 2; // 0
		System.out.println(friends);

		friends += 10; // friends = friends + 10; // 10
		System.out.println(friends);

		friends -= 5; // friends = friends - 5;  // 5
		System.out.println(friends);

		friends *= 2; // friends = friends * 2;  // 10
		System.out.println(friends);

		friends /= 3; // friends = friends / 3;  // quotient  // 3
		System.out.println(friends);

		friends %= 2; // friends = friends % 2;  // remainder  // 1
		System.out.println(friends);

		
		// Increment - Decrement Operators
		//**********************************
		
		friends =  5;
		
		friends++ ; // Increment Operator
		System.out.println(friends); // 6
		
		++friends; // Increment Operator
		System.out.println(friends); // 7
		
		friends-- ; // Decrement Operator
		System.out.println(friends); // 6

		--friends; // Decrement Operator
		System.out.println(friends); // 5
	}
}
```