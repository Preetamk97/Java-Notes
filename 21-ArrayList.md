```java
import java.util.ArrayList;  // Importing ArrayList class from java.util package.

public class Main {
	public static void main (String[] args) {
		// ArrayList = 	a resizable array. 
		//				Elements can be added and removed after compilation phase
		//				store only reference data type values
		
		// Creating an ArrayList
		ArrayList<String> food = new ArrayList<String>(); 
		
		// Adding items to ArrayList
		// .add()
		food.add("pizza");
		food.add("sandwidch");
		food.add("burger");
		
		//.set(index, value)
		food.set(0, "sushi");  
		// Replacing the value at index 0 ("pizza") with "sushi".
		
		// .remove(index) 
		food.remove(1);
		// removed the value at index position 1 ("sandwidch").
		
		// .clear()
//		food.clear();
		// deletes all the values of the ArrayList.
		
		for(int i=0; i<food.size(); i++) {	// like length() method for arrays, we use size() method for ArrayLists.
			System.out.println(food.get(i));
		}
	}
}
```