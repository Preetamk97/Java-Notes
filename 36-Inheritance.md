```java
// inheritance = 	the process where one class acquires,
//					the attributes and methods of another.

public class Vehicle {
	double speed;

	void go(){
	System.out.println("This vehicle is moving");
	}
	void stop(){
	System.out.println("This vehicle is stopped");
	}
}

// Car class inherits Vehicle class.
public class Car extends Vehicle {
	int wheels = 4;
	int door = 4;
	
	// Overrided the methods of the parent class Vehicle.
	void go(){
	System.out.println("This car is moving");
	}
	void stop(){
	System.out.println("This car is stopped");
	}
}

// Bicycle class inherits Vehicle class.
public class Bicycle extends Vehicle {
	int wheels = 2;
	int pedals = 2;
}

public class Main {

	public static void main(String[] args) {
		
		Vehicle car1 = new Car();
		
		car1.go(); // This car is moving	
		car1.stop(); // This car is stopped
		
		// Object 'car1' is accessing the overided methods go() & stop() of Car class.
		
//		System.out.println(car1.wheels); // Error.
//		System.out.println(car1.door); // Error.
		System.out.println(car1.speed); // 0
		
		// Object 'car1' cannot access the member variables 'int wheels' and 'int door' of the Car class. But it can access the 'int speed' variable of the parent class Vehicle. 
		
		Car car2 = new Car();
		
		car2.go(); // This car is moving
		car2.stop(); // This car is stopped
		
		// Object 'car2' is accessing the overided methods go() & stop() of Car class.
		
		System.out.println(car2.wheels); // 4
		System.out.println(car2.door); // 4
		System.out.println(car1.speed); // 0
		
		// Object 'car2' can access the member variables 'int wheels' and 'int door' of the Car class and also the 'int speed' variable of the parent class Vehicle.
		
		Bicycle bike = new Bicycle();
		
		bike.go();  // This vehicle is moving
		bike.stop();  // This vehicle is stopped
		System.out.println(bike.wheels);  // 2
		System.out.println(bike.pedals);  // 2
		
		// Since Bicycle class has no overided methods, the go() & stop() methods that the object 'bike' executes those inherited from the parent Vehicle class. 	
	}
}
```