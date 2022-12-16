```java
public class Car {
    private String make;
    private String model;
    private int year;
    
    Car(String make,String model,int year){
        this.setMake(make);
        this.setModel(model);
        this.setYear(year);
    }
    
    // Created an new Car class contructor (which trakes another Car class object as parameter) and used the copy() method within it.
    Car(Car x){
        this.copy(x);
    }
    
    public String getMake() {
        return make;
    }
    
    public String getModel() {
        return model;
    }
    
    public int getYear() {
        return year;
    }
    
    public void setMake(String make) {
        this.make = make;
    }
    
    public void setModel(String model) {
        this.model = model;
    }
    
    public void setYear(int year) {
        this.year = year;
    }
    
    // For copying the 'car1' object into 'car2' object while keeping their memory addresses separate, we need to create a copy() method inside the Car class.
    //car2.copy(car1);
    public void copy(Car x) {
        this.setMake(x.getMake());
        this.setModel(x.getModel());
        this.setYear(x.getYear());
    }
}

public class Main {
    
	public static void main(String[] args) {

		Car car1 = new Car("Chevrolet","Camaro",2021);
		//Car car2 = new Car("Ford","Mustang",2022);

        //car1 = car2;   // This code means, that both names 'car1' and 'car2' will refer to the  same object (i.e. car1) and will have exactly same memory address.
					     // This is not the code we wanna use if we need to create two separate/independent objects 'car1' & 'car2' with two different memory addresses.

		// For copying the car1 object into car2 object while keeping their memory addresses separate, we need to create a copy() method inside the Car class.
		//car2.copy(car1);

		// Created an new Car class contructor (which trakes another Car class object as parameter) and used the copy() method within it.
		Car car2 = new Car(car1);

		System.out.println(car1);
		System.out.println(car2);
		System.out.println();
		System.out.println(car1.getMake());
		System.out.println(car1.getModel());
		System.out.println(car1.getYear());
		System.out.println();
		System.out.println(car2.getMake());
		System.out.println(car2.getModel());
		System.out.println(car2.getYear());
	}
}
```