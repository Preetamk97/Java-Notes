```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		// nested loop = a loop inside of a loop
		
		Scanner scanner = new Scanner(System.in);
		int rows;
		int columns;
		String symbol = "";
		
		System.out.println("Enter # of rows: ");
		rows = scanner.nextInt();
		System.out.println("Enter # of columns: ");
		columns = scanner.nextInt();
		System.out.println("Enter symbol to use: ");
		symbol = scanner.next();
		// .next() will store the next token that we type until we hit space.
		
		for(int i=1; i<=rows; i++) {
			// Nested Loop Used Below.
			for(int j=1; j<=columns;j++) {
				System.out.print(symbol);
			}
			
			System.out.println();  // new line in console.
		}	
	}
}
```