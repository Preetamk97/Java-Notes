```java
public class Animal {

	 public void speak() {
	  System.out.println("animal goes *brrrr*");
	 }
}

public class Dog extends Animal{

	 @Override
	 public void speak() {
	  System.out.println("dog goes *bark*");
	 }
}

public class Cat extends Animal{

	 @Override
	 public void speak() {
	  System.out.println("cat goes *meow*");
	 }
}


// Driver Code:
import java.util.Scanner;
public class Main {

 public static void main(String[] args) {
  
  //Dynamic Polymorphism
  // Dynamic (run time) polymorphism is the polymorphism existed at run-time. Here, Java compiler does not know which method is called during compilation time. Only JVM decides which method is called at run-time.
  
  Scanner scanner = new Scanner(System.in);
  Animal animal;
  //Declaring an 'Animal animal' object reserves space for it in memory.	
  //But the compiler still does not know what type of Animal we want. 
  
  //Taking user choice for type of animal
  System.out.println("What animal do you want?"); 
  System.out.print("(1=dog) or (2=cat): ");
  int choice = scanner.nextInt();
  
  
  if(choice==1) {
   animal = new Dog();	// construct Animal class animal object as a Dog class object.
   animal.speak();
  }
  else if(choice==2) {
   animal = new Cat();	// construct Animal class animal object as a Cat class object.
   animal.speak();
  }
  else {
   animal = new Animal();	// construct Animal class animal object as a Animal class object.
   System.out.println("That choice was invalid");
   animal.speak();
  }
  
  // JVM decides the type of 'Animal animal' object that needs to be created - from user input - and which speak() method to apply on the recently created object during program runtime.
  // This is an example of Dynamic/Runtime Polymorphism.
  
  scanner.close();
 }
}
```