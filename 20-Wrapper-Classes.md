```java
public class Main {

	public static void main(String[] args) {

		// wrapper class = provides a way to use primitive data types (int, boolean,
		// etc..) as reference data types (objects).
		// reference data types contain useful methods
		// Sometimes you must use wrapper classes, for example when working with
		// Collection Framework objects, such as ArrayList, where primitive datatypes
		// cannot be used.

		// primitive //wrapper
		// --------- //-------
		// boolean Boolean
		// char Character
		// int Integer
		// double Double
		// byte Byte
		// short Short
		// long Long
		// float Float

		// All of these Wrapper classes reside inside java.lang package.

		// autoboxing = the automatic conversion that the Java compiler makes between
		// the primitive types and their corresponding object wrapper classes.
		// unboxing = the reverse of autoboxing. Automatic conversion of wrapper class
		// to primitive data type.
		// Example :
		// Integer i1 = 3; // autoboxing
		// int i2 = i1; // unboxing

		// Creating Wrapper Objects
		Boolean a = true;
		Character b = '@';
		Integer c = 123;
		Double d = 3.14;
		String e = "pritam";

		// Since you're now working with objects, you can use certain methods to get
		// information about the specific object.

		// For example, the following methods are used to get the value associated with
		// the corresponding wrapper object: intValue(), byteValue(), shortValue(),
		// longValue(), floatValue(), doubleValue(), charValue(), booleanValue().
		System.out.println(b.charValue()); // @
		System.out.println(c.intValue()); // 123
		System.out.println(d.doubleValue()); // 3.14

		// Another useful method is the toString() method, which is used to convert
		// wrapper objects to strings.
		// In the following example, we convert an Integer to a String, and use the
		// length() method of the String class to output the length of the "string":
		Integer myInt = 100;
		String myString = myInt.toString();
		System.out.println(myString.length());

		// A numeric value stored in the format of a String variable can be modified to
		// any data type by using parseXXX() like parseInt(), parseDouble().
		String contact = "288978";
		int contactNo = Integer.parseInt(contact);
		System.out.println(contactNo);

		// Primitive types are faster than wrapper classes
		// As Wrappers are classes, they can be less efficient than a primitive that
		// stores only a single value
		// Whenever possible, we must use primitive types since they are much efficient
		// than wrapper classes
		// Comparing Wrappers using == is wrong because it compares the addresses of the
		// reference vobjects and not the value represented by the them.

		int i = 45;// primitive data int
		Integer integer = new Integer(i);// Integer wrapper class instantiation
		int i2 = integer.intValue();// unwrapping primitive data int from wrapper object
		System.out.println(i2); // 45

		Integer integer2 = new Integer("23");
		// all wrapper class except Character can take String in argument
		System.out.println(integer2); // 23

		// compareTo demo
		Integer intObj1 = new Integer(25);
		Integer intObj2 = new Integer("25");
		Integer intObj3 = new Integer(35);
		System.out.println("Comparing using compareTo Obj1 and Obj2: " + intObj1.compareTo(intObj2)); // 0
		System.out.println("Comparing using compareTo Obj1 and Obj3: " + intObj1.compareTo(intObj3)); // -1
		// Equals demo
		System.out.println("Comparing using equals Obj1 and Obj2: " + intObj1.equals(intObj2)); // true
		System.out.println("Comparing using equals Obj1 and Obj3: " + intObj1.equals(intObj3)); // false
		
		// compare() demo
		Float f1 = new Float("2.25f");
		Float f2 = new Float("20.43f");
		Float f3 = new Float(2.25f);
		System.out.println("Comparing using compare f1 and f2: " + Float.compare(f1, f2)); // -1
		System.out.println("Comparing using compare f1 and f3: " + Float.compare(f1, f3)); // 0

		// Addition of Integer with Float
		Float f = intObj1.floatValue() + f1;
		System.out.println("Addition of intObj1 and f1: " + intObj1 + "+" + f1 + "=" + f);  // 27.25

		int x = Integer.parseInt("34");
		System.out.println(x); // 34

		double y = Double.parseDouble("34.7");
		System.out.println(y);  // 34.7

	}

}
```