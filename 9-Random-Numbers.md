```cpp
import java.util.Random; 
// importing Random Class from java.util package.

public class Main {
	
	public static void main(String[] args) {
		
		// Creating an instance of Random class
		Random random = new Random();
		
		int x = random.nextInt();
		// values of 'int x' will range from -2 billion to 2 billion.
		System.out.println(x);
		
		int y = random.nextInt(6);
		// values of 'int y' will range from 0 to 5
		System.out.println(y);
		
		double z = random.nextDouble();
		// values of 'double z' will range between 0.0 to 1.0.
		System.out.println(z);
		
		boolean p = random.nextBoolean();
		// values of p can be either true or false.
		System.out.println(p);
	}		
}
```