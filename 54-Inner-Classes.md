```java
/* In Java, it is perfectly okay and legal to have a class inside another class. Inside class is called Inner Class.

inner class = 	- A class inside of another class.
				- usually private, but not necessary
				- helps group classes that belong together
*/

// Outer class
public class Outside {
	String x = "Hello ";
	
	// inner class
	public class Inside{
		
		String y = "World!";
		
		public void Greeting()
		{
			System.out.println(x+y);
		}
	}
}

public class Main {

	public static void main(String[] args) {
		
		Outside out = new Outside();  // Instance of Outer class
		Outside.Inside in = out.new Inside();  // Instance of Inner class
		System.out.println(out.x + in.y);	// Accessing attributes of both outer and inner class
		in.Greeting(); // invoking inner class function through inner class object.
	}
}
```