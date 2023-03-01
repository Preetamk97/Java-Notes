# String Class

```java
public class Main {

	public static void main(String[] args) {

		// String class resides inside java.lang package
		// String = a reference data type that can store one or more characters
		// Reference data types have access to useful methods
		// Some useful methods of String class are: equals(), split(), indexOf(),trim(),
		// length().

		// Strings can be created by applying one of the following methods:

		String username1 = "Jeena";   // Literal

		String username2 = "Jeena";   // Literal

		String username3 = new String("Jeena");  // Object

		String username4 = new String("Jeena");  // Object

		// In  String username1 = "Jeena";  line of code, variable 'username' is representing a String literal "Jeena". String literals are created in a pool section of the heap memory. For example, if another String literal is created: String username2 = "Jeena", then both name and username point to the same literal in the pool - have same address.

		// Applying == on two Strings compares the address of the two Strings.
		System.out.println("== Test 1: "+ (username1 == username2));  // true
		// .equals() = checks the equality of content
		System.out.println(".equals() Test 1: " + (username1.equals(username2))); // true

		// In  String username3 = new String("Jeena");  line of code​​​​​​​ 'username' is representing a String class object. If we create another String: String username4 = new String("Jeena"); then both name and username point to two different objects in the memory - different adresses.

		// Applying == on two Strings compares the address of the two Strings.
		System.out.println("== Test 2: "+ (username3 == username4));  // false
		System.out.println("== Test 3: "+ (username2 == username3));  // false

		// string.equals(null) = checks the equality of content
		System.out.println(".equals() Test 2: " + (username2.equals(username3))); // true
		System.out.println(".equals() Test 3: " + (username3.equals(username4))); // true

		// string.equals(null) = false ---> Always
		System.out.println(".equals() Test 4: " + (username3.equals(null))); // false

		// Always remember that string literals are not eligible for garbage collection throughout the application. On the other hand, String objects can be garbage collected.

 
		String name = "Bro";

		// .equals() = checks the equality of content
		boolean result1 = name.equals("bro");
		System.out.println("result1: " + result1); // false

		// .equalsIgnoreCase()
		boolean result2 = name.equalsIgnoreCase("bro");
		System.out.println("result2: " + result2); // true

		// .length()
		int result3 = name.length();
		System.out.println("result3: " + result3); // 3

		// .charAt()
		char result4 = name.charAt(0);
		System.out.println("result4: " + result4); // B

		// .indexOf()
		int result5 = name.indexOf("B");
		System.out.println("result5: " + result5); // 0

		// .isEmpty() : returns 'true' if what we have is an empty string.
		boolean result6 = name.isEmpty();
		System.out.println("result6: " + result6); // false

		// .toUpperCase(): converts all the letters of the string to upper case.
		String result7 = name.toUpperCase();
		System.out.println("result7: " + result7); // BRO

		// .toLowerCase()
		String result8 = name.toLowerCase();
		System.out.println("result8: " + result8); // bro

		// .trim(): The trim() method removes whitespaces from both the ends of a
		// string. Note: This method does not change the original string.
		String hello = "      hello       ";
		String helloTrimmed = hello.trim();
		System.out.println("result9:");
		System.out.println(hello); // hello
		System.out.println(helloTrimmed); // hello

		// .replace(): replace() method returns a string replacing all the old char or
		// CharSequence to a new char or CharSequence.
		String movie = "Ironman is awesome!";
		String movieReplaced1 = movie.replace('m', 'g'); // This will replace all the 'm' characters with 'g' in the
															// complete string.
		System.out.println("result10: " + movieReplaced1); // Irongan is awesoge!


		// .toCharArray() : converts the string to character array
		char arr[]= name.toCharArray(); 
		for (char i : arr){
			System.out.print(i+", ");  // B, r, o,
		}


		System.out.println("");


		// Character.isLetter() : This method returns true if the passed character is really a character.
		System.out.println("result11: "+ Character.isLetter('c'));
      	System.out.println("result12: "+ Character.isLetter('5'));


		// .compareTo() Method:
		// The Java String class compareTo() method compares the given string with the current string lexicographically. It returns a positive number, negative number, or 0.
		// If the first string is lexicographically greater than the second string, it returns a positive number (difference of character value). If the first string is less than the second string lexicographically, it returns a negative number, and if the first string is lexicographically equal to the second string, it returns 0.
		// s1.compareTo(String s2)  
		// if s1 > s2, it returns positive number  
		// if s1 < s2, it returns negative number  
		// if s1 == s2, it returns 0   
		// It returns an integer value. It throws the following two exceptions:
		// ClassCastException: If this object cannot get compared with the specified object.
		// NullPointerException: If the specified object is null.
		String s1 = "hello";
		String s2 = "hello";
		String s3 = "meklo";
		String s4 = "hemlo";
		String s5 = "flag";
		System.out.println("result13: "+ s1.compareTo(s2));// 0 because both are equal
		System.out.println("result14: "+ s1.compareTo(s3));// -5 because "h" is 5 times lower than "m"
		System.out.println("result15: "+ s1.compareTo(s4));// -1 because "l" is 1 times lower than "m"
		System.out.println("result16: "+ s1.compareTo(s5));// 2 because "h" is 2 times greater than "f"

		// .compareTo() Case Sensitiveness:
		// input string in uppercase  
		String st1 = new String("INDIA IS MY COUNTRY");  
		// input string in lowercase  
		String st2 = new String("india is my country");  
		System.out.println("result17: "+ st1.compareTo(st2));  // -32 or some random value
		// Conclusion: It is obvious by looking at the output that the outcome is not equal to zero. Hence, the compareTo() method takes care of the case sensitiveness of characters.


		// .concat()
		String result18 = name.concat("MAN");
		System.out.println("result18: "+ result18);
	}

}
```

## **Note**:

In conditional statements, prefer writing "123".equals(stringValue) over stringValue.equals("123") as the latter one can lead to a NullPointerException when stringValue is null.

**Example:** Identify the issue with the below code

```java
public void drawShape(String shape){
    if(shape.equals("Square")){
      drawSquare();
    }
    if(shape.equals("Rectangle")){
      drawRectangle();
    }
}
```
The code has a potential for NullPointerException.

Hence should be re-written as:

```java
public void drawShape(String shape){
    if("Square".equals(shape)){
      drawSquare();
    }
    if("Rectangle".equals(shape)){
      drawRectangle();
    }
}
```