```java
// Interface = a template that can be applied to a class.
//			 = similar to inheritance, specifies what a class has/must do.
// Classes can apply more than 1 interface, but inheritance is limited to only 1 super class.

public class Main {

	public static void main(String[] args) {
		
		Rabit rabit = new Rabit();
		rabit.flee();	//*The rabbit is fleeing*
		
		Hawk hawk = new Hawk();
		hawk.hunt();	//*The hawk is hunting*
		
		Fish fish = new Fish();
		fish.hunt(); 	//*The fish is hunting* 
		fish.flee();	//*The fish is fleeing*
	}
}

public interface Prey {
	void flee();
}

public interface Predator {
	void hunt();
}

public class Rabit implements Prey {

	@Override
	public void flee() {
		// TODO Auto-generated method stub
		System.out.println("*The rabbit is fleeing*");
	}

}

public class Hawk implements Predator {

	@Override
	public void hunt() {
		// TODO Auto-generated method stub
		System.out.println("*The hawk is hunting*");
	}

}

public class Fish implements Predator, Prey {

	@Override
	public void flee() {
		// TODO Auto-generated method stub
		System.out.println("*The fish is fleeing*");
	}

	@Override
	public void hunt() {
		// TODO Auto-generated method stub
		System.out.println("*The fish is hunting*");
	}

}
```