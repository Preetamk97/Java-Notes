```java
public class Friend {
	String name;
	
    //static variable
	static int numberOfFriends;
	
	Friend(String name){
		this.name=name;
		numberOfFriends++;
	}	
	
    // static method
	static void displayFriends() {
		System.out.println("You have "+numberOfFriends+" friends.");
	}
	
	// A static method can only use static member variables.
	// However, a non-static method can use both static as well as non-static variables.
}

public class Main {

	public static void main(String[] args) {
		
		// static = modifier. A single copy of a variable/method is created and shared.
		// The class "owns" the static member.
		
		Friend friend1 = new Friend("Sponegbob");
		Friend friend2 = new Friend("Patrick");
		Friend friend3 = new Friend("Gary");
		
		// We can access the static variable of a class using the class name directly.
		System.out.println(Friend.numberOfFriends);
		
		// We can also access the static variable of a class using the class object. But, this practise is not recomended.
		System.out.println(friend1.numberOfFriends);
		
		// Calling a static method.
		Friend.displayFriends();
	}
}
```