```cpp
public class Main {
	
	public static void main(String[] args) {
		
		double x = 3.14;
		double y = -10;
		
		double a = Math.max(x, y);  // Math.max(x,y) returns the bigger value of x and y.
		System.out.println(a);	// 3.14
		
		double b = Math.abs(y); // Math.abs(y) gives Modulus of y. 
		System.out.println(b);	// 10.0
		
		double c = Math.sqrt(x); // Math.sqrt(x) gives the square root of x.
		System.out.println(c);  // 1.772004514666935
		
		double d = Math.round(x);  // Math.round(x) gives the rounded value of x.
		System.out.println(d); // 3.0 
		
		double e = Math.ceil(x); // Math.ceil(x) gives the ceiling value of x.
		System.out.println(e);  // 4.0

		double f = Math.floor(x); // Math.floor(x) gives the floor value of x.
		System.out.println(f);  // 3.0
	}
}
```

```java
// Program to calculate the hypoteneus of a right triangle.

import java.util.Scanner;

public class Main {
	
	public static void main(String[] args) {
		
		Scanner scanner = new Scanner(System.in);
		
		double x;
		double y;
		double z;
		
		System.out.println("Enter the 1st side length: ");
		x = scanner.nextDouble();
		
		System.out.println("Enter the 2nd side length: ");
		y = scanner.nextDouble();
		
		z = Math.sqrt((x*x) + (y*y));
		
		System.out.println("Length of hypoteneus is: " + z + " cms.");
		
		scanner.close();
	}		
}
```