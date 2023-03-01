# Java Collection Framework : Map Interface & Its Sub Classes

## Map Interface : 

![](imgfiles\chap67\2023-02-25-13-50-52.png)

- It is an interface which maps unique keys to values. These unique keys are used to retrieve the values.
- **Map Interface** is a part of the **Collection Framework** but **does not inherit** from the **Collection interface**.
- **Hashmap** : No guarantee to the order of the elements.
- **LinkedHashMap** : Order of insertion of the elements is maintained.
- **TreeMap** : Elements are ordered based on the ascending order of the keys.

## HashMap

- ### Creating an Object of HashMap

    ![](imgfiles\chap67\2023-02-25-14-00-01.png)

- ### Some Common Methods:

    ![](imgfiles\chap67\2023-02-25-14-07-45.png)

```java
import java.util.HashMap;
import java.util.Map;
import java.util.Set;

class Main {
	public static void main(String[] args) {
		Map<Integer, String> map  = new HashMap<Integer, String>();

		map.put(10, "Pritam");
		map.put(20, "Rohit");
		map.put(30, "Pradhugyna");
		map.put(30, "Bikash");  // Adding a duplicate key with a different value simply overwrites the existing value.
		map.put(40, "Bikash");  // However, Map accepts duplicate values.

		System.out.println("Printing out the map : "+map); 
		// Printing out the map : {20=Rohit, 40=Bikash, 10=Pritam, 30=Bikash}
		// All the keys in the Map must be unique. It does not accept duplicate keys. However, values can be duplicate.
		
		// Note: HashMap does not maintain the order of insertion of elements.
		
		System.out.println("Displaying Values of HashMap");
		Set<Integer> set = map.keySet();
		for (Integer i : set){
			System.out.println(map.get(i));
		}
		// Rohit
		// Bikash
		// Pritam
		// Bikash

		//.remove(key) - removes the complete element associated with the key (including the value) from the map.
		map.remove(10);
		System.out.println("HashMap after removing key-value for key 10 : "+map);
		// HashMap after removing key-value for key 10 : {20=Rohit, 40=Bikash, 30=Bikash}

		//.containsKey()
		System.out.println("Checking if the HashMap contains the key 10 : " + map.containsKey(10));  // false

		//.containsValue()
		System.out.println("Checking if the HashMap contains the value \"Rohit\" : " + map.containsValue("Rohit"));  // true 

		//.isEmpty()
		System.out.println("Checking if the HashMap is empty : " + map.isEmpty()); // false

		//.size()
		System.out.println("Checking the HashMap size : " + map.size()); // 3
	}
}
```

## LinkedHashMap

```java
import java.util.LinkedHashMap;
import java.util.Map;
import java.util.Set;

class Main {
	public static void main(String[] args) {
		Map<Integer, String> map  = new LinkedHashMap<Integer, String>();

		map.put(20, "Rohit");
		map.put(30, "Pradhugyna");
		map.put(10, "Pritam");
		map.put(30, "Bikash");  // Adding a duplicate key with a different value simply overwrites the existing value.
		map.put(40, "Bikash");  // However, Map accepts duplicate values.

		System.out.println("Printing out the map : "+map); 
		// Printing out the map : {20=Rohit, 30=Bikash, 10=Pritam, 40=Bikash}
		// All the keys in the Map must be unique. It does not accept duplicate keys. However, values can be duplicate.
		
		// Note: LinkedHashMap maintains the order of insertion of elements.
		
		System.out.println("Displaying Values of LinkedHashMap");
		Set<Integer> set = map.keySet();
		for (Integer i : set){
			System.out.println(map.get(i));
		}
		// Rohit
		// Bikash
		// Pritam
		// Bikash

		//.remove(key) - removes the complete element associated with the key (including the value) from the map.
		map.remove(10);
		System.out.println("LinkedHashMap after removing key-value for key 10 : "+map);
		// LinkedHashMap after removing key-value for key 10 : {20=Rohit, 30=Bikash, 40=Bikash}

		//.containsKey()
		System.out.println("Checking if the LinkedHashMap contains the key 10 : " + map.containsKey(10));  // false

		//.containsValue()
		System.out.println("Checking if the LinkedHashMap contains the value \"Rohit\" : " + map.containsValue("Rohit"));  // true 

		//.isEmpty()
		System.out.println("Checking if the LinkedHashMap is empty : " + map.isEmpty()); // false

		//.size()
		System.out.println("Checking the LinkedHashMap size : " + map.size()); // 3
	}
}
```

## TreeMap()

```java
import java.util.TreeMap;
import java.util.Map;
import java.util.Set;

class Main {
	public static void main(String[] args) {
		Map<Integer, String> map  = new TreeMap<Integer, String>();

		map.put(20, "Rohit");
		map.put(30, "Pradhugyna");
		map.put(10, "Pritam");
		map.put(30, "Bikash");  // Adding a duplicate key with a different value simply overwrites the existing value.
		map.put(40, "Bikash");  // However, Map accepts duplicate values.

		System.out.println("Printing out the map : "+map); 
		// Printing out the map : {10=Pritam, 20=Rohit, 30=Bikash, 40=Bikash}
		// All the keys in the Map must be unique. It does not accept duplicate keys. However, values can be duplicate.
		
		// Note: TreeMap arranges the elements according to the sorted (ascending) order of the keys.
		
		System.out.println("Displaying Values of TreeMap");
		Set<Integer> set = map.keySet();
		for (Integer i : set){
			System.out.println(map.get(i));
		}
		// Pritam
		// Rohit
		// Bikash
		// Bikash

		//.remove(key) - removes the complete element associated with the key (including the value) from the map.
		map.remove(10);
		System.out.println("TreeMap after removing key-value for key 10 : "+map);
		// TreeMap after removing key-value for key 10 : {20=Rohit, 30=Bikash, 40=Bikash}

		//.containsKey()
		System.out.println("Checking if the TreeMap contains the key 10 : " + map.containsKey(10));  // false

		//.containsValue()
		System.out.println("Checking if the TreeMap contains the value \"Rohit\" : " + map.containsValue("Rohit"));  // true 

		//.isEmpty()
		System.out.println("Checking if the TreeMap is empty : " + map.isEmpty()); // false

		//.size()
		System.out.println("Checking the TreeMap size : " + map.size()); // 3
	}
}
```

## Concurrent HashMap

```java
// Difference between HashMap and ConcurrentHashMap

import java.util.concurrent.ConcurrentHashMap;
import java.util.Map;
import java.util.Set;

class Main {
	public static void main(String[] args) {
		Map<Integer, String> map  = new ConcurrentHashMap<Integer, String>();

		map.put(10, "Pritam"); 
		map.put(20, "Rohit");
		map.put(30, "Pradhugyna");
		map.put(40, "Bikash");
		
		System.out.println("Printing out the map : "+map);
		
		// Difference between HashMap and ConcurrentHashMap
		Set<Integer> set = map.keySet();
		for (Integer i : set){
			map.remove(i);  
			// Normally, HashMap - does not allow us to modify the existing set at the same time while iterating through it.
			// If the 'set' object would have been a HashMap class object - the above line of code (map.remove(i);) would have given a runtime exception - "ConcurrentModificationException".
            // Hence, HashMap does not allow the - map.remove(i); - operation inside the for loop.
			// But that is where the ConcurrentHashMap comes into picture as it - allows us to modify the existing set at the same time while iterating through it.
			// Meaning , it allows the - map.remove(i); - operation inside the for loop.

            // HashMap is non-synchronised and not thread safe.
            // ConcurrentHashMap is synchronised and thread safe.
		}

		System.out.println(map.size());  // 0
	}
}
```