# Java Collection Framework : List Interface & Its Sub-Classes

In this article, we will be focussing on the **List Interface** of the Collection Framework & Its Sub-Classes (**LinkedList** & **ArrayList**).

![](imgfiles\chap64\Collection.png)

## List Interface

- Extends the Collection Interface.
- It allows duplicate elements which can be accessed based on their index position.
- **Methods specific to list:**

![](imgfiles\chap65\2023-02-23-10-12-18.png)


## ArrayList Sub-Class

- Array implementation of List Interface.
- Allows random access as it works on the basis of index.
- Adding and removing the elements is time consuming.

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;
import java.util.ListIterator;

public class Main {
	public static void main (String args[]){

		// Creating an object of List interface using ArrayList class constructor.
		List list1 = new ArrayList<>();  

		// Adding values to list
		list1.add("Jack");
		list1.add("Jack");
		list1.add("Andrew");
		list1.add("Eric");
		
		// Adding value at specific index number
		list1.add(1, "Jerry");

		System.out.println("List is: "+list1);  
		// List is: [Jack, Jerry, Jack, Andrew, Eric]
		

		// Getting the value present at an index
		System.out.println("Value at index 1: " + list1.get(1));  
		// Value at index 1: Jerry

		// Deleting element form the list using index position
		String valueRemovedFromnIndex = (String) list1.remove(3); 
		System.out.println("Value deleted from the index 3 is: " + valueRemovedFromnIndex);  
		// Value deleted from the index 3 is: Andrew
		System.out.println("New List is: "+ list1); 
		// New List is: [Jack, Jerry, Jack, Eric] 

		// Checking if the list is containing a value
		System.out.println(list1.contains("Jacob"));  // false
		System.out.println(list1.contains("Jerry"));  // true


		// Creating a new ArrayList
		List list2 = new ArrayList<>();
		list2.add("Radhe");
		list2.add("Shyam");

		// Adding all the list2 elements to list1
		// list1.addAll(list2);
		// System.out.println("List1 after adding all elements of List2: " + list1);
		// List1 after adding all elements aof List2: [Jack, Jerry, Jack, Eric, Radhe, Shyam, Kaaju, Rocky]
		
		// Adding all the list2 elements to list1 at specified index position
		list1.addAll(2, list2);
		System.out.println("List1 after adding all elements of List2 at index position 2: " + list1);
		// List1 after adding all elements of List2 at index position 2: [Jack, Jerry, Radhe, Shyam, Jack, Eric]

		// Iterating through the list1 using For loop
		System.out.println("Iterated using For Loop:");
		System.out.println("-------------------------");
		for (int i=0; i<list1.size() ; i++){
			System.out.print(list1.get(i)+"\t");
		}
		System.out.println("\n");

		// Iterating through the list1 using Enhanced For loop
		System.out.println("Iterated using Enhanced For Loop:");
		System.out.println("---------------------------------");
		for (Object name : list1){
			System.out.print(name+"\t");
		}
		System.out.println("\n");

		// Iterating through the list1 using Iterator class of Collection Framework
		System.out.println("Iterated using Iterator:");
		System.out.println("------------------------");
		Iterator itr = list1.iterator();  // Creating Iterator object for list1
		while (itr.hasNext()){  
		// If next element is present in the list 'itr.hasNext()' returns 'true'
		// By default, the iterator starts from the position just before the first element of the list.
			String val = (String) itr.next();
			// 'itr.next()' moves the iterator to the next index position and returns the corresponding value at the index.
			System.out.print(val+"\t");
		}
		System.out.println("\n");

		// Iterating using ListIterator given by List Interface
		ListIterator lstItr = list1.listIterator();

		System.out.println("Iterated in forward direction using List Iterator");
		System.out.println("-------------------------------------------------");
		while (lstItr.hasNext()) {
			String name = (String)lstItr.next();
			System.out.print(name + "\t");
		}
		System.out.println("\n");
		
		// Iterating in Reverse Direction
		System.out.println("Iterated in reverse direction using List Iterator");
		System.out.println("-------------------------------------------------");
		while (lstItr.hasPrevious()) { 
		// hasPrevious() method is not available for normal iterator object.
		// hasPrevious() method check if there is any value present at the 'immediate previous index position' of the current index position - if so it returns 'true' otherwise 'false'.
		// In this case the 'listIterator' starts from the the position just after the last element of the list.
			String name = (String)lstItr.previous();
			// lstItr.previous() moves the listIterator to the previous index and returns the corresponding value at the index. 
			System.out.print(name + "\t");
		}
	}
}
```

## LinkedList Sub-Class

- It allows **sequential** access unlike ArrayList that allows **random** access - hence **slower access of elements**.
- Adding and removing elements is easier and faster.
- It has the following additional methods:

![](imgfiles\chap65\2023-02-23-12-28-28.png)

```java
import java.util.LinkedList;

public class Main {
	public static void main (String args[]){
		LinkedList list1 = new LinkedList<>();

		// Adding elements using the Collecition interface method add()
		list1.add("Jack");
		list1.add("Andrew");
		list1.add("Eric");
		System.out.println("List1 is " + list1);  // List1 is [Jack, Andrew, Eric]

		// Adding values using the LinkedList class method addFirst()
		list1.addFirst("Peter");
		System.out.println("List1 after adding value using addFirst() : " + list1);
		// List1 after adding value using addFirst() : [Peter, Jack, Andrew, Eric] 

		// Adding values using the LinkedList class method addLast()
		list1.addLast("Jerry");
		System.out.println("List1 after adding value using addLast() : " + list1);
		// List1 after adding value using addLast() : [Peter, Jack, Andrew, Eric, Jerry]

		// Getting the first value of the LinkedList
		String firstValue = (String) list1.getFirst(); // list1.getFirst() returns an Object that is typecasted to a String literal.
		System.out.println("First value of list1 is : "+firstValue);  // First value of list1 is : Peter

		// Getting the last value of the LinkedList
		String lastValue = (String) list1.getLast();
		System.out.println("Last value of list1 is : "+lastValue);  // Last value of list1 is : Jerry

		// Deleitng the first value from the LinkedList
		String valueRemovedFromFirst = (String)list1.removeFirst();
		System.out.println("Value removed from index 0 using removeFirst() : " + valueRemovedFromFirst);
		// Value removed from index 0 using removeFirst() : Peter
		System.out.println("List after removing value form index 0 : "+ list1);
		// List after removing value form index 0 : [Jack, Andrew, Eric, Jerry]

		// Deleitng the last value from the LinkedList
		String valueRemovedFromLast = (String)list1.removeLast();
		System.out.println("Value removed from last index using removeLast() : " + valueRemovedFromLast);
		// Value removed from last index using removeLast() : Jerry
		System.out.println("List after removing value form last index : "+ list1);
		// List after removing value form last index : [Jack, Andrew, Eric]
	}
}
```

```java
import java.util.List;
import java.util.Iterator;
import java.util.LinkedList;

class Course {
	String courseName;

	public Course(String courseName) {
		this.courseName = courseName;
	}

	@Override
	public String toString() {
		return courseName;
	}
}

class ListInterface {
	public static void main(String[] args) {
		List<Course> courseList = new LinkedList<>();
		courseList.add(new Course("Java"));
		courseList.add(new Course("Hibernate"));
		courseList.add(new Course("AngularJS"));

		// Accessing the list of courses Using Iterator
		Iterator<Course> courseIterator = courseList.iterator();
		System.out.println("Using Iterator to access the list of courses");
		while (courseIterator.hasNext()) {
			Course c = courseIterator.next();
			System.out.println(c); // toString() method has been overridden in the Course class
		}

		// Accessing the list of courses Using for loop
		System.out.println("Using for loop to access the list of courses");
		for (int index = 0; index < courseList.size(); index++) {
			System.out.println(courseList.get(index));
		}

		// Accessing the list of courses Using enhanced for loop (for-each)
		System.out.println("Using enhanced for loop to access the list of courses");
		for (Course c : courseList) { // Can be read as: for each Course c in courseList
			System.out.println(c);
		}
	}
}
```

## ArrayList vs LinkedList


| ArrayList | LinkedList |
|---|---|
|It is the array implementation of the List Interface| It is the Linked List implementation of the List Interface|
|Allow random access hence provides fast access| Allows sequential access of the list. Hence access is relatively slow|
|Adding and removing elements is slow and time consuming|Adding and removing elements is relatively fast|