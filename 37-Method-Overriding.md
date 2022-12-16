```java
public class Animal {
	void speak() {
		System.out.println("The animal speaks");
	}
}

public class Dog extends Animal {
	
	@Override
	void speak() {
		System.out.println("The dog goes *bark*");
	}
}

public class Main {

	public static void main(String[] args) {
		
		// method overriding = 	Declaring a method in sub class,
		//						which is already present in the parent class.
		//						Done so that a child class can give its own implementation.
		
		Animal animal = new Animal();
		Dog dog = new Dog();
		Animal dog2 = new Dog();
		
		animal.speak(); // The animal speaks
		dog.speak(); // The dog goes *bark*
		dog2.speak(); // The dog goes *bark*
		
	}
}
```