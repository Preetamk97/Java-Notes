```java
import java.util.HashMap;

public class Main {

	public static void main(String[] args) {

		// HashMap implements the Map interface (need import)
		// HashMap is similar to ArrayList, but with key-value pairs
		// stores objects, need to use Wrapper Class
		// ex: (name,email),(username,userID),(country,capital)
		
		//Creating a HashMap
		HashMap<String,String> countries = new HashMap<String,String>();
		
		//add a key and value
		countries.put("USA","Washington DC");
		countries.put("India","New Delhi");
		countries.put("Russia","Moscow");
		countries.put("China","Beijing");
		
		System.out.println(countries);	//{USA=Washington DC, China=Beijing, India=New Delhi, Russia=Moscow}
		System.out.println(countries.size());  //4
		System.out.println(countries.get("India"));	//New Delhi
		System.out.println(countries.get("Russia"));  //Moscow
		countries.replace("USA", "Detroit"); 
		System.out.println(countries); //{USA=Detroit, China=Beijing, India=New Delhi, Russia=Moscow}
		countries.remove("USA"); 
		System.out.println(countries); //{China=Beijing, India=New Delhi, Russia=Moscow}
		System.out.println(countries.containsKey("England")); //false
		System.out.println(countries.containsValue("Beijing")); //true
		
		for(String i : countries.keySet()) {
			System.out.print(i+"\t"+"= ");
			System.out.println(countries.get(i)); //.get(key)
		}
		// China	= Beijing
		// India	= New Delhi
		// Russia	= Moscow

		countries.clear();
		System.out.println(countries); //{}
	}
}
```