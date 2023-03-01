```java
// polymorphism = 	greek word for poly-"many", morph-"form"
//					The ability of an object to identify as more than one type.

public abstract class Vehicle {

	public abstract void go();
}

public class Car extends Vehicle{

	@Override
	public void go() {
		System.out.println("*The car begins moving*");
	}
}

public class Bicycle extends Vehicle{

	@Override
	public void go() {
		System.out.println("*The bicycle begins moving*");
	}
}

public class Boat extends Vehicle{

	@Override
	public void go() {
		System.out.println("*The boat begins moving*");
	}
}

public class Main {

	public static void main(String[] args) {
		
		Car car = new Car();
		Bicycle bicycle = new Bicycle();
		Boat boat = new Boat();
		
		Vehicle[] racers = {car,bicycle,boat};
		// Since all the 3 classes (Car, Bicycle, Boat) inherits from the Vehicle class, therefore, all the 3 objects (car of Car class, bicycle of Bicycle class, and boat of Boat class) can be stored inside an array of Vehicle class objects.  

        // This phenomenen of an object of being able to be identified as an object of more than one class is called polymorphism.
		
		// Now, the objects car, bicycle, and boat - apart from being objects of their own respective class (Car, Bicycle, Boat) are also objects of the Vehicle class -- and if we go one step further -- are also the objects of java.Object class.
		
		for(Vehicle x : racers) {
			x.go();
			//*The car begins moving*
			//*The bicycle begins moving*
			//*The boat begins moving*
			
			// For each x (which might be an object of any 1 of the 3 classes - Car, Bicycle, and Boat) - The selection of the correct go() method which is to be applied on the object x (i.e the exact go() method which belongs the parent class of object x) - Is decided during the compile time.

			// This is an example of Static Polymorphism / CompileTime Polymorphism.

			// Static (compile time) polymorphism is the polymorphism exhibited at compile time. Here, Java compiler knows which method is called. 
		}
	}
}
```