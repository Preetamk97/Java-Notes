```java
// Creating a Basic GUI Application in Java.

// Necessary Import
import javax.swing.JOptionPane;

public class Main {
	
	public static void main(String[] args) {
		
		// Creating an Input Dialog Box for 
		// Taking the User Input and storing it inside name variable.
		String name = JOptionPane.showInputDialog("Enter Your Name:");
		
		// Creating a Message Dialog Box for
		// Displaying out the name entered with a string message.
		JOptionPane.showMessageDialog(null, "Hello " + name + "!");
		
		// Creating an Input Dialog Box for 
		// Taking User Input and storing it inside int age variable.
		int age = Integer.parseInt(JOptionPane.showInputDialog("Enter your age:"));
		// The code `JOptionPane.showInputDialog("Enter your age:")` 
		// is going to return us a string value.
		// Now, a string value cannot be stored inside a int data type variable (int age) directly.
		// First, we have to convert the string 
		// recieved from `JOptionPane.showInputDialog("Enter your age:")` using the 
		// parseInt() method of Integer Wrapper Class.
		// And then, we can store the value we get out of Integer.parseInt() inside the 
		// int age variable.
		
		// Creating a Message Dialog Box for
		// Displaying out the age entered with a string message.
		JOptionPane.showMessageDialog(null, "Your age is " + age + " years old.");
		
		// Creating an Input Dialog Box for 
		// aking User Input and storing it inside double height variable.
		double height = Double.parseDouble(JOptionPane.showInputDialog("Enter Your Height:"));
		// Creating a Message Dialog Box for
		// Displaying out the height entered with a string message.
		JOptionPane.showMessageDialog(null, "You are " + height + " cm tall.");
	}
}
```









