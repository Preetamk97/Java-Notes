```java
// object = An instance of a class that contains attributes and methods.
// example - phone, desk, dog, cat, etc.

public class Car {
	String maker = "Chevrolet";
	String model = "Corvette";
	int year = 2020;
	String color = "blue";
	double price = 50000.00;
	
	void drive() {
		System.out.println("You drive the car");
	}
	void brake() {
		System.out.println("You step on the brakes");
	}
}

public class Main {

	public static void main(String[] args) {
		// Creating Car class objects 'myCar1' & 'myCar2'
		Car myCar1 = new Car();
		Car myCar2 = new Car();
		
		// Accessing member variables of objects through objects.
		System.out.println(myCar1.maker);
		System.out.println(myCar1.model);
        System.out.println(myCar2.maker);
		System.out.println(myCar2.model);
		
		// Accessing member methods of the class through objects.
		myCar1.drive();
		myCar1.brake();
	}
}
```