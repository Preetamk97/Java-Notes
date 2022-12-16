Lambda Expressions were added in Java 8.

A lambda expression is a short block of code which takes in parameters and returns a value. Lambda expressions are similar to methods, but they do not need a name.

The simplest lambda expression contains a single parameter and an expression:

`parameter -> expression`

To use more than one parameter, wrap them in parentheses:

`(parameter1, parameter2) -> expression`

Expressions are limited. They have to immediately return a value, and they cannot contain variables, assignments or statements such as if or for. In order to do more complex operations, a code block can be used with curly braces. If the lambda expression needs to return a value, then the code block should have a return statement.

`(parameter1, parameter2) -> { code block }`

## Example 1: Use a lambda expression in the ArrayList's forEach() method to print every item in the list:

```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(5);
    numbers.add(9);
    numbers.add(8);
    numbers.add(1);
    numbers.forEach( (n) -> { System.out.println(n); } );
  }
}
```

Lambda expressions can be stored in variables if the variable's type is an interface which has only one method. The lambda expression should have the same number of parameters and the same return type as that method.

## Example 2

```java
//A Functional Interface is an interface which contains only one abstract method/function.

@FunctionalInterface
public interface MyInterface {
	public void calculator(int a, int b);
}

// Writing the @FunctionalInterface over interface declaration lets others know that this Interface is a @FunctionalInterface.

public class Main {

	public static void main(String[] args) {
		
		// We are creating an instance 'sum' of functional interface 'MyInterface' which contains only one method 'void calculator(int a, iny b) 
		// Inside this instance we are storing a lamba expression which actually provides the definition for method 'void calculator(int a, int b)' of the functional interface 'MyInterface'.
		// So, this lambda expression must have the same parameter signature and return type as of the method 'void calculator(int a, int b)'.
		MyInterface sum = (x,y) -> {
			System.out.println("Value of (x + y) = "+ (x+y));
		};
		
		// We can create multiple instances of the 'MyInterface' inteface and for each instance, we can define the method 'void calculator(int, int)' in a different way, using lambda expressions, as per our needs.
		MyInterface product = (x,y) -> {
			System.out.println("Product of xy = "+(x*y));
		};
			
		sum.calculator(2,5); //Value of (x + y) = 7
		product.calculator(2,5); //Product of xy = 10
		
		
		// Doing the same thing using anonymous inner class.
		MyInterface modulus = new MyInterface(){
			public void calculator(int a, int b) {
				System.out.println("Modulus x%y = "+(a%b));
			}
		};
		
		modulus.calculator(20, 6); //Modulus x%y = 2		
	}
}
```