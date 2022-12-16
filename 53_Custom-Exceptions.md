```java
// Creating a Custom Exception class.
public class AgeException extends Exception{
	
	// exception = an event that disrupts the normal flow of the program.
	// Some exception classes are provide by java itself.
	// example : ArithmeticException, ArrayIndexOutOfBoundsException, FileNotFoundException etc.
	
	// Custom exceptions = User defined exceptions
	// examples: AgeException, InvalidInformationException, DataNotFoundException etc.

	AgeException(String message){  
		super(message);  
	}  
}

public class Main { 
	
	public static void main(String args[]){
		
		 Scanner scanner = new Scanner(System.in);
		 
		 System.out.print("Enter your age: ");
		 int age = scanner.nextInt();
 	 
	      try{  
	    	  checkAge(age);  
	      }
	      
	      // If checkAge(age) throws an AgeException object or any Exception type object for that matter, then that exception object will be catched and dealt with by catch block.
	      // Every exception object is an object of the Exception class.
	      catch(Exception e)
	      {
	    	  System.out.println("A problem occured: "+e);
	      }   
	} 
	
	public static void checkAge(int age) throws AgeException{ 
	// Since we are using this function inside main() function which is static itself, therefore we also have to declare this function as static.
	// This function 'checkAge(int age)' throws an object of the 'AgeException' class. 
	// 'throws' keyword exclusively points towards an exception class.
	// 'AgeException' is a custom-user-defined 'Exception' class - that we created - extending from the 'Exception' class of java itself.
		 
	     if(age<18) {
	    	 throw new AgeException("\n"+"You must be 18+ to sign up"); 
	    	 // if age<18, this function 'checkAge(int age)' will throw an object of AgeException class with the message given as String argument.
	     }
	     else {
	    	// if age>18
	    	 System.out.println("You are now signed up!");
	     }       
	}
}
```