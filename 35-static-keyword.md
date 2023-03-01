```java
public class Friend {
	String name;

    // static variable
    static int numberOfFriends;  // Default value = 0

    Friend(String name) {
        this.name = name;
        numberOfFriends++;
    }

    // static method
    static void displayFriends() {
        System.out.println("You have " + Friend.numberOfFriends + " friends.");
    }

    // A static method can only use static member variables.
    // However, a non-static method can use both static as well as non-static
    // variables.
}

public class Main {

	public static void main(String[] args) {
		// static = modifier. A single copy of a variable/method is created and shared.
		// The class "owns" the static member.
		
		Friend friend1 = new Friend("Sponegbob");
		// We can access the static variable of a class using the class name directly.
		System.out.println(Friend.numberOfFriends);  // 1
		// We can also access the static variable of a class using the class object. But, this practise is not recomended.
		System.out.println(friend1.numberOfFriends);  // 1

		Friend friend2 = new Friend("Patrick");
		System.out.println(friend2.numberOfFriends);  // 2

		Friend friend3 = new Friend("Gary");
		System.out.println(friend3.numberOfFriends);  // 3
		
		// Calling a static method.
		Friend.displayFriends();  // 3
	}
}
```