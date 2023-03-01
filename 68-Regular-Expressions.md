# Regular Expresisons:

- A **Regular Expresisons (regex)** is a sequence of characters that constitute a search pattern.
- The serach pattern is used in searching and editing a string.
- Regular expressions provides the following options:
    1. Character Classes
    1. Quantifiers
    1. Meta Characters
- The String class contains the following methods that support **regex**:
    - matches(), split(), replaceFirst(), replaceAll()


# Character Classes:

- Charachter Classes are used to match a character in a string. 
- Charachter Classes define what characters the string may contain.
- [] is used to represent a character class.

![](imgfiles\chap68\2023-02-26-12-34-35.png)

```java
public class Main {
	public static void main(String[] args) {

		String s1 = "1";
		String s2 = "A";
		String s3 = "b";

		// String pattern = "[0-9]";  // String can contain any character from 0-9
		String pattern = "[a-zA-Z]";  // String can contain any character from range a-z or A-Z

		System.out.println("Pattern is : " + pattern);
		System.out.println("-------------------------");
		System.out.println("Checking for s1 : " + s1.matches(pattern)); 
		System.out.println("Checking for s2 : " + s2.matches(pattern)); 
		System.out.println("Checking for s3 : " + s3.matches(pattern)); 
	}
}
```

# Quantifiers:

- Quantifiers define how many times a character can exist in a string.

![](imgfiles\chap68\2023-02-26-13-04-32.png)

```java
public class Main {
	public static void main(String[] args) {

		// String should contain only alphabets from A-Z or a-z
		String s1 = "Aa";
		String s2 = "Bb";
		String s3 = "C9";

		// String pattern = "[a-zA-Z]";  // Character Classes can only validate strings which have length of only 1 character. 
		// But what do we do when we need to validate strings with more than 1 character length.
		// Here comes into picture the Quantifiers.

		String pattern = "[a-zA-Z]+";  // + sign implies that the characters a-z or A-Z can exist 1 or more times.


		System.out.println("Pattern is : " + pattern);
		System.out.println("-------------------------");
		System.out.println("Checking for s1 : " + s1.matches(pattern)); 
		System.out.println("Checking for s2 : " + s2.matches(pattern)); 
		System.out.println("Checking for s3 : " + s3.matches(pattern)); 
	}
}
```

```java
public class Main {
	public static void main(String[] args) {

		// String should contain only alphabets from A-Z or a-z
		String s1 = "Apple";  // 5 characters
		String s2 = "Pineapple";  // 9 characters
		String s3 = "Orange";  // 6 characters

		// String pattern = "[a-zA-Z]";  // Character Classes can only validate strings which have length of only 1 character. 
		// But what do we do when we need to validate strings with more than 1 character length.
		// Here comes into picture the Quantifiers.

		String pattern = "[a-zA-Z]{1,6}";  // {1,6} implies that the string to be validated should have a minimum of 1 character to a maximum of 6 characters from the range of a-z & A-Z  - not more or less than that.


		System.out.println("Pattern is : " + pattern);
		System.out.println("-------------------------");
		System.out.println("Checking for s1 : " + s1.matches(pattern));  // true
		System.out.println("Checking for s2 : " + s2.matches(pattern));  // false
		System.out.println("Checking for s3 : " + s3.matches(pattern));  // true
	}
}
```

# Meta Characters:

- Meta Characters are a set of pre-defined patterns.

![](imgfiles\chap68\2023-02-26-13-23-39.png)

```java
public class Main {
	public static void main(String[] args) {

		// String should contain only alphabets from A-Z or a-z
		String s1 = "6ppl_"; // 5 Characters 
		String s2 = "Pineapple";  // 9 Characters 
		String s3 = "@boom"; // 5 Characters 

		// String pattern = "\\w{2,6}";  // First "\" is Escape Sequence. "\w" is a meta character that signifies any character form a-z, or A-Z, or 0-9, or Underscore ("_"). {2,6} means that the total number of characters must between 2 to 6.
		
		// Note: We can wrap the whole regex in circular brackets (). Output is going to be same.
		String pattern = "(\\w{2,6})";


		System.out.println("Pattern is : " + pattern);
		System.out.println("-------------------------");
		System.out.println("Checking for s1 : " + s1.matches(pattern));  // true
		System.out.println("Checking for s2 : " + s2.matches(pattern));  // false
		System.out.println("Checking for s3 : " + s3.matches(pattern));  // false
	}
}
```

--- 

# Regex API

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class Main {
	public boolean validateMobileNumber(String mobileNumber) {
		Pattern regex = Pattern.compile("\\d{3}-\\d{3}-\\d{4}");
		Matcher mobileMatcher = regex.matcher(mobileNumber);
		return mobileMatcher.matches();
	}

	public static void main(String[] args) {
		Main object = new Main();
		System.out.println(object.validateMobileNumber("111-222-3333"));  // true
	}
}
```