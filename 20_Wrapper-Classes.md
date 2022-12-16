```java
public class Main {

 public static void main(String[] args) {
  
    // wrapper class =  provides a way to use primitive data types (int, boolean, etc..) as reference data types (objects).
    // reference data types contain useful methods
    // Sometimes you must use wrapper classes, for example when working with Collection Framework objects, such as ArrayList, where primitive datatypes cannot be used.

    //primitive  //wrapper
    //---------  //-------
    // boolean  Boolean
    // char   Character
    // int   Integer
    // double  Double
    // byte   Byte
    // short   Short
    // long   Long
    // float  Float


    // autoboxing = the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes
    // unboxing = the reverse of autoboxing. Automatic conversion of wrapper class to primitive

    // Creating Wrapper Objects
    Boolean a = true;
    Character b = '@';
    Integer c = 123;
    Double d = 3.14;
    String e = "pritam";

    // Since you're now working with objects, you can use certain methods to get information about the specific object.

    // For example, the following methods are used to get the value associated with the corresponding wrapper object: intValue(), byteValue(), shortValue(), longValue(), floatValue(), doubleValue(), charValue(), booleanValue().
    System.out.println(b.charValue());
    System.out.println(c.intValue());
    System.out.println(d.doubleValue());

    // Another useful method is the toString() method, which is used to convert wrapper objects to strings.

    // In the following example, we convert an Integer to a String, and use the length() method of the String class to output the length of the "string":
    Integer myInt = 100;
    String myString = myInt.toString();
    System.out.println(myString.length());

    }
 
}
```