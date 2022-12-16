1. Lets us create a file "secret_message.txt" on our Desktop.

1. We also place a copy of this file "secret_message.txt" inside out Java Project Folder. Make sure to paste the copy file inside the Java Project Folder but NOT inside the package folder itself where our Main.java file is located.

1. Now, we can determine if the file "secret_message.txt" is actually present at a certain location/folder in our computer or not through the Java File class.

1. See the code below.

```java
import java.io.File;  // Necessary import for using file class.

public class Main {

 public static void main(String[] args) {

  // file = An abstract representation of file and directory pathnames

  File file = new File("secret_message.txt");
  // Creating a file class object and giving it the name of our file that we want to search for, as a string argument.
  // In this case, we are searching for the file "secret_message.txt" that is located inside the Java Project Folder.

  // If we want to search for the file "secret_message.txt" that is located somewhere else (i.e. not inside the Java Project Folder) such as desktop, we need to give the full file path as argument instead of just the file name. See the code line below.
  File file2 = new File("C:\\Users\\preet\\Desktop\\secret_message.txt");
  // For backslashes in the file path/address, we can either use '\\' (double backslash) or '/' (forward backslash).

  if(file.exists()) {
   System.out.println("That file exists! :O!");
   //That file exists! :O!
   System.out.println(file.getPath());
   //secret_message.txt
   //It returns whatever we passed as argument while creating our file object.
   System.out.println(file.getAbsolutePath());
   //C:\Users\preet\eclipse-workspace\FirstJavaProject\secret_message.txt
   // It returns the exact location of the file.
   System.out.println(file.isFile());
   //true
   // It returns true if your file is infact a file.

   //file.delete();
   // This deletes the file at the file loaction.
   // Refresh the project folder to see the file deleted.
  }

  if(file2.exists()) {
	   System.out.println("That file exists! :O!");
	   //That file exists! :O!
	   System.out.println(file2.getPath());
	   //C:\Users\preet\Desktop\secret_message.txt
	   // It returns whatever we passed as argument while creating our file object.
	   System.out.println(file2.getAbsolutePath());
	   ///C:\Users\preet\Desktop\secret_message.txt
	   // It returns the exact location of the file.
	   System.out.println(file2.isFile());
	   //true
	   // It returns true if your file is infact a file.

       //file2.delete();
	   // This deletes the file at the file loaction.
	   // Refresh the project folder to see the file deleted.
	  }
      
  else {
   System.out.println("That file doesn't exist :(");
  }
 }
}
```
