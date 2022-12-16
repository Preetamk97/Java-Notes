```java
//super = 	keyword refers to the superclass (parent) of an object
//			very similar to the "this" keyword

public class Person {
	String name;
	int age;
	
	Person(String name,int age){
		this.name = name;
		this.age = age;
	}
	
	public String toString() {
		return this.name + "\n" + this.age + "\n";
		// "\n" = new line.
	}
}

public class Hero extends Person {
	String power;
	
	Hero(String name,int age,String power){	
//		this.name = name;
//		this.age = age;
		super(name,age);	// Parent class constructor is summoned.
		this.power = power;
	}
	
	public String toString() {
		return super.toString()+this.power;
		// super.toString() = Parent class toString() method in summoned.
	}
}

public class Main {

	public static void main(String[] args) {
		
		Hero hero1 = new Hero("Batman",42,"$$$");
		Hero hero2 = new Hero("Superman",43,"everything");
		
		System.out.println(hero2.toString());
		
	}
}
```