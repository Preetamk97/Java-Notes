```java
public class Human {
	String name;
	int age;
	double weight;
	
	// Constructor = special method of the class that is used to instantiate/create an object of the class.
	// Constructor is given the same name as the class (in this case 'Human').
	
	// Parametrized Constructor
	Human(String name,int age,double weight){
		
		this.name = name;
		this.age = age;
		this.weight = weight;
	}
	
	void eat() {
		System.out.println(this.name+" is eating");
		// In order to access any attribute value of an object that belongs to this class, inside a member method of this class, we have to use 'this' keyword. 
	}
	void drink() {
		System.out.println(this.name+" is drinking *burp*");
        // In order to access any attribute value of an object that belongs to this class, inside a member method of this class, we have to use 'this' keyword.
	}
}

public class Main {

	public static void main(String[] args) {
		
		Human human1 = new Human("Rick",65,70);
		Human human2 = new Human("Morty",16,50);
			
		human1.eat();
		human2.drink();
	}

}
```