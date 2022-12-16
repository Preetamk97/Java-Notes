```java
import java.io.FileWriter;
import java.io.IOException;

public class Main {

	public static void main(String[] args) {
		
		try {
			FileWriter writer = new FileWriter("poem.txt"); 
			// Creating a FileWriter class object 'writer'.
			// "poem.txt" is the name of the file that we are going to create. This will create the file "poem.txt" inside the project folder.
			// Refresh to see the result.
			
			// If we want to create the file anywhere other than the project folder, we would have to give the full file path/address (with file name) as argument string.
			FileWriter writer2 = new FileWriter("C:\\Users\\preet\\Desktop\\secret_message.txt");
			// Creating a FileWriter class object 'writer2'.
			// Creating a file "secret_message.txt" in Desktop.
			// Refresh to see the result.
			
			writer.write("Roses are red \nViolets are blue \nBooty booty booty booty \nRockin' everywhere!"); 
			// Writing to the file "poem.txt" using FileWriter class object 'writer'
			// '\n' is an escape sequence which means "start from a new line".
			
			writer.append("\n(A poem by Bro)");	
			// Appending to the file "poem.txt"
			
			writer.close();	
			// closing the writer object.
			
			writer2.write("Roses are red \nViolets are blue \nBooty booty booty booty \nRockin' everywhere!"); 
			// Writing to the file "secret_message.txt" using FileWriter class object writer2
			
			writer2.append("\n(A poem by Bro)");	
			// Appending to the file "secret_message.txt" using FileWriter class object writer2
			
			writer2.close();	
			// closing the writer2 object.
		} 
		catch (IOException e) {
			
			e.printStackTrace(); 
			// printing stack trace of the error object.
		}
	}
}
```