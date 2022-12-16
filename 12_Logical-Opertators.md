```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		// logical operators = used to connect two or more conditions
		//
		//						&& = (AND) both conditions must be true
		// 						|| = (OR) either condition must be true
		//						! = (NOT) reverses boolean value of condition

// -------------------------------- Example 1 --------------------------------

		// int temp = 15;
		
		// if(temp>30) {
		// 	System.out.println("It is hot outside");
		// }
		// else if(temp>=20 && temp<=30) {
		// 	System.out.println("It is warm outside");
		// }
		// else {
		// 	System.out.println("It is cold outside");
		// }


// -------------------------------- Example 2 --------------------------------

		// Scanner scanner = new Scanner(System.in);
		
		// System.out.println("You are playing a game! Press q or Q to quit");
       
		// String response = scanner.next();
		// // .next() will store the next complete word that you enter.
		// // If we enter "Java Programming Is a Pain!" as user input, 
		// // .next() will take only the first word "Java" and store it inside `String response` variable.
		// // But .nextLine() takes the complete line of "Java Programming Is a Pain!" as a value 
		// // and stores it inside the assigned variable.
		
		// if(response.equals("q") || response.equals("Q")) {
		// 	System.out.println("You quit the game");
		// }
		// else {
		// 	System.out.println("You are still playing the game *pew pew*");
		// }
		
// -------------------------------- Example 3 --------------------------------

		Scanner scanner = new Scanner(System.in);
		
		System.out.println("You are playing a game! Press q or Q to quit");
        
		String response = scanner.next();
		
		if(!response.equals("q") && !response.equals("Q")) {
			System.out.println("You are still playing the game *pew pew*");
		}
		else {
			System.out.println("You quit the game");
		}
		
		scanner.close();
	}
}
```