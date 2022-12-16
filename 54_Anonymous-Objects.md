1. **Anonymous** means ***Nameless***. 
1. Generally, when creating an object in Java, you need to assign a name to the object. But the anonymous object in Java allows you to create an object without any name assigned to that object.
1. So, if you want to create only one object in a class, then the anonymous object would be a good approach.
1. Since they have no name, there’s no other way to refer to them beyond the point when they are created. Consequently, they have “expression scope,” meaning they are created, evaluated, and destroyed everything within a single expression.

```java
public class Square {
	
	int side;
	
	public Square(int side) {
		this.side = side; 
	}
	
	public void perimeter() {
		int perimeter = side * 4;
		System.out.println("Perimeter is = "+perimeter);
	}
	
	public void area() {
		int area = side * side;
		System.out.println("Area is = "+area);
	}

	public static void main(String[] args) {
		// Creating Anonymous Objects
		new Square(5).perimeter();	//Perimeter is = 20
		new Square(10).area();	//Area is = 100
		new Square(15).perimeter();	//Perimeter is = 60
		new Square(20).area();	//Area is = 400
	}

}
```