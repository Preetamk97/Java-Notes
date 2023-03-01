# Java Collection Framework : Set Interface & Its Sub Classes

A **Set** is a **collection that cannot contain duplicate elements**.

![](imgfiles\chap66\2023-02-23-13-51-45.png)

![](imgfiles\chap66\2023-02-23-13-41-53.png)

## HashSet Class

### Creating a HashSet class object

![](imgfiles\chap66\2023-02-23-13-44-51.png)

### Methods of HashSet Class

![](imgfiles\chap66\2023-02-23-13-46-20.png)


```java
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;


public class Main {
	public static void main (String args[]){

		// Creating a Set object for holding Integer objects using HashSet class constructer.
		Set<Integer> set = new HashSet<>();

		// Adding elements to HashSet
		set.add(10);
		set.add(20);
		set.add(30);
		set.add(40);
		set.add(40);

		System.out.println(set);  // [20, 40, 10, 30]

		// Note:
		//******
		// HashSet does not take care of the order of insertion of the elements.

		// Printing elements of HashSet using an iterator
		Iterator<Integer> iterator = set.iterator();
		System.out.println("Displaying HashSet using Iterator:");
		while(iterator.hasNext()){
			System.out.println(iterator.next());
		}
		// Displaying HashSet using Iterator:
		// 20
		// 40
		// 10
		// 30
		
		
		//.contains()
		System.out.println("Value of set.contains(110) is : " + set.contains(110));  // false

		//.remove()
		set.remove(10);
		System.out.println("Value of set after doing set.remove(10) is : " + set);  // Value of set after doing set.remove(10) is : [20, 40, 30]

		// isEmpty() - returns 'true' if the set is empty
		System.out.println("Checking if the set is empty : " + set.isEmpty());  // false
	}
}
```

## LinkedHashSet Class

```java
import java.util.Iterator;
import java.util.LinkedHashSet;
import java.util.Set;

public class Main {
	public static void main(String args[]) {
		// Creating a Set object for holding Integer class objects using LinkedHashSet
		// class constructer.
		Set<Integer> set = new LinkedHashSet<>();

		// Adding elements to LinkedHashSet
		set.add(20);
		set.add(30);
		set.add(10);
		set.add(40);
		set.add(40);

		System.out.println(set); // [20, 30, 10, 40]

		// Note:
		// ******
		// Set does not allow duplicate elements.
		// LinkedHashSet takes care of the order of insertion of the elements.

		// Printing elements of LinkedHashSet using an iterator
		Iterator<Integer> iterator = set.iterator();
		System.out.println("Displaying LinkedHashSet using Iterator:");
		while (iterator.hasNext()) {
			System.out.println(iterator.next());
		}
		// Displaying LinkedHashSet using Iterator:
		// 20
		// 30
		// 10
		// 40

		// .contains()
		System.out.println("Value of set.contains(110) is : " + set.contains(110)); // false

		// .remove()
		set.remove(10);
		System.out.println("Value of set after doing set.remove(10) is : " + set); // Value of set after doing
																					// set.remove(10) is : [20, 30, 40]

		// isEmpty() - returns 'true' if the set is empty
		System.out.println("Checking if the set is empty : " + set.isEmpty()); // false
	}
}
```

## TreeSet Class

```java
import java.util.TreeSet;
import java.util.Iterator;
import java.util.Set;


public class Main {
	public static void main (String args[]){

		// Creating a Set object for holding Integer objects using TreeSet class constructer.
		Set<Integer> set = new TreeSet<>();

		// Adding elements to TreeSet
		set.add(20);
		set.add(30);
		set.add(10);
		set.add(40);
		set.add(40);

		System.out.println(set);  // [10, 20, 30, 40]

		// Note:
		// ******
		// Set does not allow duplicate elements.
		// TreeSet orders the elements according to supplied Comparator. If no comparator is supplied, elements will be placed in their natural ascending order.


		// Printing elements of Set using an iterator
		Iterator<Integer> iterator = set.iterator();
		System.out.println("Displaying TreeSet using Iterator:");
		while(iterator.hasNext()){
			System.out.println(iterator.next());
		}
		// Displaying Set using Iterator:
		// 10
		// 20
		// 30
		// 40
		
		//.contains()
		System.out.println("Value of set.contains(110) is : " + set.contains(110));  // false

		//.remove()
		set.remove(10);
		System.out.println("Value of set after doing set.remove(10) is : " + set);  // Value of set after doing set.remove(10) is : [20, 30, 40]

		// isEmpty() - returns 'true' if the set is empty
		System.out.println("Checking if the set is empty : " + set.isEmpty());  // false
	}
}
```