```java
public class Main {

	public static void main(String[] args) {
			
		// array = used to store multiple values within a single variable
		
		// Simplest way of making an array in Java.
		//*****************************************
// 		String[] cars = {"Camaro", "Corvette", "Tesla"};
		
		// Note: If you have a String datatype array, you can add only string type values to it.
		
		// We can also access and change the values of this array as per our requirement like this -
//		cars[0] = "Bugati";
//		cars[1] = "Cadillac";
//		cars[2] = "Porsche";
		
//		System.out.println(cars);
//		System.out.println(cars[0]);
//		System.out.println(cars[1]);
//		System.out.println(cars[2]);

		// Another Way of making an Array.
		//***********************************
		String[] cars = new String[3];
		// Argument 3 in `new String[3]` means that there will be 3 strings in our array.
		
		cars[0] = "Camaro";
		cars[1] = "Corvette";
		cars[2] = "Tesla";
		
		// Using a for loop to iterate through the elements of the array.
		for(int i=0; i<cars.length; i++) {
			System.out.println(cars[i]);
		}	
	}
}
```