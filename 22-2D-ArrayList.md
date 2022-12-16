```java
import java.util.*;

public class Main {

	public static void main(String[] args) {
		
		// 2D ArrayList = a dynamic list of lists.
		// You can change the size of these lists during runtime.
		
		// First, lets us create 3 separate independent ArrayLists.
		
		ArrayList<String> bakeryList = new ArrayList();
		bakeryList.add("pasta");
		bakeryList.add("garlic bread");
		bakeryList.add("donuts");
		
		ArrayList<String> produceList = new ArrayList();
		produceList.add("tomatoes");
		produceList.add("zucchini");
		produceList.add("peppers");
		
		ArrayList<String> drinksList = new ArrayList();
		drinksList.add("soda");
		drinksList.add("coffee");
		
		// Creating a 2D ArrayList which holds all the 3 ArrayLists made above.
		ArrayList<ArrayList<String>> groceryList = new ArrayList();
		
		groceryList.add(bakeryList);
		groceryList.add(produceList);
		groceryList.add(drinksList);
		
		// Printing the 2D ArrayList 'groceryList'.
		System.out.println(groceryList);
		// [[pasta, garlic bread, donuts], [tomatoes, zucchini, peppers], [soda, coffee]]
		
		// Printing the list i.e at index 0 of the 2D ArrayList 'groceryList'.
		System.out.println(groceryList.get(0));
		// [pasta, garlic bread, donuts]
		
		// Printing the index 0 item on the list which is at index 0 of the 2D ArrayList 'groceryList'.
		System.out.println(groceryList.get(0).get(0));  // "pasta"
		
		// Printing the index 1 item on the list which is at index 2 of the 2D ArrayList 'groceryList'.
		System.out.println(groceryList.get(2).get(1));  // "coffee"
	}
}
```