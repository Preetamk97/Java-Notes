# FileReader Class

```java
import java.io.FileReader;
import java.io.FileNotFoundException;
import java.io.IOException;

public class Main {

	public static void main(String[] args) {
		
		// FileReader = reads the contents of a file as a stream of characters -- One by one -- One at a time.
		//				.read() returns an int value which contains the byte value of the current character.
		//				When read() returns -1, there is no more data to be read.
		
		try {
			FileReader reader = new FileReader("art.txt"); 
			// Within the constructor FileReader() ; place filename or file path.
			
			int data = reader.read();
			//.read() : reads the immediate first character of the file 'art.txt'.
			//        : returns an 'int' value which contains the byte value of that character.
			
			while(data != -1) {     // Repeat the process until data=-1 (no data to read).
				// When read() returns -1, there is no more data to be read.
				System.out.print((char)data); 
				// convert/cast the 'int' type byte value (that is stored inside the variable 'data') into the OG character and print it.
				// Also, make sure to use print() instead of println().
				data = reader.read(); // again read the next immediate first character from the file 'art.txt' and store it inside 'int data' variable.
			}
			reader.close();
			
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {			
			e.printStackTrace();
		}
	}
}
```

# BufferedReader Class

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {

	public static void main(String[] args) {

		try {
			FileReader reader = new FileReader("poem.txt"); // Creating the FileReader Object

			BufferedReader bReader = new BufferedReader(reader); // Stream Chaining

			// reading the content
			int i = bReader.read();

			while (i != -1) {
				System.out.print((char) i);
				i = bReader.read();
			}

			// closing the reader object.
			bReader.close();

			System.out.println("\nData read successfully !");

		} catch (IOException e) {

			e.printStackTrace();
			// printing stack trace of the error object.
		}
	}
}
```