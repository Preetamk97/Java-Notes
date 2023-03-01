# Introduction:

Java is a programming language from Sun Microsystems (Sun) developed by James Gosling in 1991. The main objective of Java is to make it platform-independent, which helps to write a program once and then run this program on multiple operating systems. Java also helps in developing distributed applications. It was inspired by C++ and has many of its syntaxes. The 1st Java version (Java 1.0) was made publicly available in 1995. Later, new enhanced versions of Java have been released.

# Environment Setup

## Necessary Installations:

1. **IDE - VS Code or Eclipse** : Download & install from official websites.
1. **Java Developmen Kit (If using Eclipse)**: Download JDK separately and install it (steps shown in Bro Code PDF) >> After successfull installion give a system restart >> After ther restart, to check if the JDK is installed successfully -- run `java --version` -- on a command prompt.
1. **Java Developmen Kit (If using VS Code)**: Google search "Java for VS Code" >> Go to the first link (code.visualstudio.com/docs/languages/java) >> Download & install the "Coding Pack for Java - Windows/Mac" in your system. This will install all the necessary VS Code Extensions + JDK necessary for Java development >> After successfull installion give a system restart >> After ther restart, to check if the JDK is installed successfully -- run `java --version` -- on a command prompt.


# Printing 'Hello World' in Java.

```java
// In Java, the class name (class Main) and the name of the .java file (Main.java) have to be same.
public class Main {
	
	// The execution of our code inside Main class starts with public static void main(String[] args) method.
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		// Inside main method, any code that you write at the top will get executed first.
		
		// Printing a string in the console using System.out.print()
// 		System.out.print("Hello World!");
// 		System.out.print("Nice to meet you.");
		// Hello World!Nice to meet you.
		
		// Printing a string in the console using System.out.println()
//		System.out.println("Hello World!");
//		System.out.println("Nice to meet you.");
		// Hello World!
		// Nice to meet you.
		
		// Alternative to using System.out.println -- "\n" --- Escape Sequence Character.
//		System.out.print("Hello World!\n");
//		System.out.print("Nice to meet you.");
		// Hello World!
		// Nice to meet you.
		
		// Guess the output of this code.
		System.out.println("Hello World!\n");
		System.out.println("Nice to meet you.");
//		Hello World!
//
//		Nice to meet you.

	}
}
```

# Compiling and Running Java File from Command Prompt:

1. javac Main.java (to compile and create the .class file)
1. java Main (to run a .class file, it's portable)


# Use of Escape Sequence '\t' (= tab while printing in console)

```java
public class Main {
	
	public static void main(String[] args) {
		
 		System.out.print("Hello World!\t");
 		System.out.print("Nice to meet you.");
 		// Hello World!     Nice to meet you.
	}
}
```

# Printing '"Hello World!"' with quotation marks in console.

```java
public class Main {
	
	public static void main(String[] args) {
		
 		System.out.println("\"Printing Hello World! with quotation marks\"");
        // "Printing Hello World! with quotation marks"
        // Placing a escape sequence (\) before " " marks instructs the Java compiler to consider the following " " marks as string values.

        System.out.println("\\Printing a backslash in console.");
        // \Printing a backslash in console.
 		
	}
}
```

# Comments in Java

```java
public class Main {
	
	public static void main(String[] args) {
		
		// Single-line Comment
		
		/* 
		 * This 
		 * is
		 * a
		 * multi-line
		 * comment
		 */
 		
	}
}
```

# Eclipse/VS Code Tricks: 

1. **Keyboard Shortcut for writting `System.out.println`** -- Write `sysout` on the editor and hold (Ctrl + Space).

2. **Keyboard Shortcut for Zooming In & Zooming Out:**
		Zooming In ----- Ctrl + [+ key] 
		Zooming Out ------ Ctrl + [- key]

