```java
// Encapsulation = 	attributes of a class will be hidden or private, 
// Can be accessed only through methods (getters & setters)
// You should make attributes private if you don't have a reason to make them public/protected

public class Car {
	private String make;
	private String model;
	private int year;
	
	Car(String make,String model,int year){
//		this.make = make;
//		this.model = model;
//		this.year = year;
		this.setMake(make);
		this.setModel(model);
		this.setYear(year);
	}
	
	// Getter Methods
	
	public String getMake() {
		return this.make;
	}
	
	public String getModel() {
		return this.model;
	}
	
	public int getYear() {
		return this.year;
	}
	
	// Setter Methods
	
	public void setMake(String make) {
		this.make = make;
	}
	
	public void setModel(String model) {
		this.model = model;
	}
	
	public void setYear(int year) {
		this.year = year;
	}
}

public class Main {

	public static void main(String[] args) {
		
		Car car = new Car("Chevrolet","Camaro",2021);
		
		car.setYear(2022);
		
		System.out.println(car.getMake());  // Chevrolet
		System.out.println(car.getModel());  // Camaro
		System.out.println(car.getYear());  // 2022
	}
}
```