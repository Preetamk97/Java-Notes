```java
public class Main {

 public static void main(String[] args) {
  
  // String = a reference data type that can store one or more characters
  // reference data types have access to useful methods
  
  String name = "Bro";
  
  //.equals()
  boolean result1 = name.equals("bro");   
  System.out.println("result1: " + result1);	// false
  
  //.equalsIgnoreCase()
  boolean result2 = name.equalsIgnoreCase("bro");   
  System.out.println("result2: " + result2);	// true
  
  // .length()
  int result3 = name.length();   
  System.out.println("result3: " + result3);	// 3
  
  // .charAt()
  char result4 = name.charAt(0);   
  System.out.println("result4: " + result4);	// B
  
  // .indexOf()
  int result5 = name.indexOf("B");   
  System.out.println("result5: " + result5);	// 0
  
  // .isEmpty() : returns 'true' if what we have is an empty string. 
  boolean result6 = name.isEmpty();   
  System.out.println("result6: " + result6);	// false
  
  // .toUpperCase(): converts all the letters of the string to upper case.
  String result7 = name.toUpperCase();
  System.out.println("result7: " + result7);	// BRO
  
  // .trim(): The trim() method removes whitespace from both ends of a string. Note: This method does not change the original string.
  String hello = "      hello       ";
  String helloTrimmed = hello.trim();
  System.out.println("result8:");
  System.out.println(hello);
  System.out.println(helloTrimmed);
   
  // .replace(): replace() method returns a string replacing all the old char or CharSequence to a new char or CharSequence.
  String movie = "Ironman is awesome!";
  String movieReplaced1 = movie.replace('m', 'g' ); // This will replace all the 'm' characters with 'g' in the complete string.
  System.out.println("result9: " + movieReplaced1); // Irongan is awesoge!
 }
 
}
```