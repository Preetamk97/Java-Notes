```java
//abstract =  	abstract classes cannot be instantiated, but they can have a subclass which can be instantiated.
// abstract methods are declared without an implementation.

public abstract class Vehicle {
// If a class has any abstract member method, then the class must also be declared as abstract.
// 'abstract' classes cannot be instantiated but they can be inherited by other methods.
	
	abstract void go();
	// 'abstract' keyword suggests that this method will be defined later down the line inside a child class of this class.
	
	abstract void stop();
}

public class Car extends Vehicle {
// A child class (Car) that inherits an abstract class (Vehicle) must override all the abstract methods inherited from the abstract class.
	
	@Override
	void go() {
		System.out.println("The driver is driving the car");
	}
	
	@Override
	void stop(){
		System.out.println("The car stops.");
	}
}

public class Main {

	public static void main(String[] args) {
		
		//Vehicle vehicle = new Vehicle();  // abstract classes cannot be instantiated
		Car car = new Car();
		
		car.go();
	}
}
```