Java anonymous inner class is an inner class without a name and for which only a single object is created.

It should be used if you have to override a method of the class -- only for one specific particular object -- in that case, it saves us the hustle of creating an entire sub-class of the class and overriding the method in it -- just for creating 1 object from that sub-class which needs the modifies method. 

Java Anonymous inner class can be created in two ways:

1. Class (may be abstract or concrete).
1. Interface

# Java Anonymous Inner Class Example Using Class

```java
abstract class Person{  
  abstract void eat();  
}  

public class Main{  
 public static void main(String args[]){  

    Person p=new Person(){  
    void eat(){System.out.println("nice fruits");}  
    }; 
//********************************************************************************************
//   Internal working of given code

//   Person p=new Person(){  
//   void eat(){System.out.println("nice fruits");}  
//   }; 

//  1. A class is created, but its name is decided by the compiler, which extends the Person class and provides the implementation of the eat() method.
//  2. An object of the Anonymous class is created that is referred to by 'p,' a reference variable of Person type.
//*********************************************************************************************
  p.eat();  
 }  
}  
```

### Output

![](imgfiles/chap57/output.png)



# Java Anonymous Inner Class Example Using Interface

```java
public interface Eatable{  
 public void eat();  
} 

class Main{  
 public static void main(String args[]){  
 Eatable e=new Eatable(){  
  public void eat(){System.out.println("nice fruits");}  
 };  
 //********************************************************************************************
 //   Internal working of given code
 
//  Eatable e=new Eatable(){  
//   public void eat(){System.out.println("nice fruits");}  
//  };
 
 //  1. A class is created, but its name is decided by the compiler, which implements the Eatable interface and provides the implementation of the eat() method.
 //  An object of the Anonymous class is created that is referred to by 'p', a reference variable of the Eatable type.
 //*********************************************************************************************
 e.eat();  
 }  
}  
```

### Output

![](imgfiles/chap57/output.png)