# Java Database Connectivity

- Java Database Connectivity or JDBC is a **Java Core API** for performing **Database Interactions**.
- Using JDBC API, a java application can access and interact with a variety of databases such as **MS Access**, **MySQL**, **MongoDB** etc.

![](imgfiles\chap70\2023-02-28-10-24-02.png)

# JDBC Driver

- Driver is software component which connects two dissimilar environments i.e. software-hardware or software-software.

- It allows the Client Application to connect and interact with the database server.

- JDBC Drivers are database vendor specific.

- ## Steps To Add JDBC Driver - MySQL Connector for Java - To Our Java Project:
    1. Google search **"mysql java connector"**.

    1. Click on the first link **"Download Connector/J - MySQL :: Developer Zone"**.

    1. Select operating system **"Platform Independent"**.

    1. Download the **ZIP** Archive -> **No thanks, just start my download**.

    1. Extract the **mysql-connector.jar** file from the **ZIP** folder -- **cut** and **paste** the extracted file inside the **C:\Program Files\MySQL** folder. <br>
    ![](imgfiles\chap70\2023-02-28-20-17-33.png)

    1. Open the **Java Project** *(Youtube)* in **VS Code** - where you wish to add the **MySQL Java Connector**.

    1. ***Recommended**: Run a basic print staement from Main.java/App.java file first - before proceeding further.*

    1. At the bottom of the  **Explorer Tab** expand **Java Projects Tab** <br>
    ![](imgfiles\chap70\2023-02-28-11-54-12.png)

    1. Click on the **"+"** icon beside **Referenced Libraries**.<br>
    ![](imgfiles\chap70\2023-02-28-11-55-34.png)

    1. Select the **mysql-connector-j-8.0.32.jar** file which is stored in the location - **C:\Program Files\MySQL**

    1. And now, the *JDBC Driver - MySQL Connector for Java* has been successfully integrated with our Java Project and we can use this driver software for connecting and interacting with our with our MySQL Database from the our Java Application (Source Code).


# JDBC API Syntax:

## Demo 1 : `executeUpdate()`

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class Main {

	// Important :: To run this code, use the 'Run Java' option instead of 'Run
	// Code'.
	// Otherwise the code will throw "java.sql.SQLException: No suitable driver
	// found for jdbc:mysql://localhost:3306/" error message -- on using the 'Run
	// Code' option.
	// You can also use the 'Run' option from the "Run|Debug" just below this
	// comment.
	public static void main(String[] args) {
		String DBConnectionURL = "jdbc:mysql://localhost:3306/pritamdb";
		// mysql = Database Service Provider
		// localhost = IP/Server Address
		// 3306 = PortNo.
		// pritamdb = database_name
		String DBUsername = "sqluser"; // connection_username
		String DBPassword = "password"; // connection_password

		try {
			// Creating the connection
			Connection connection = DriverManager.getConnection(DBConnectionURL, DBUsername, DBPassword);
			System.out.println("Connected to Database Successfully!");

			// PreparedStatement - Holds the SQL Query - INSERT Statement
			String psql = "INSERT INTO employees values (?,?,?,?)"; // Inserting values in the employees table.
			PreparedStatement pStatement = connection.prepareStatement(psql);

			// Inserting values // (parameterIndex, value)
			pStatement.setInt(1, 1004);
			pStatement.setInt(2, 26);
			pStatement.setString(3, "Bikash");
			pStatement.setString(4, "Kalita");

			// Executing the PreparedStatement
			int noOfRowsUpdated = pStatement.executeUpdate();  
			// For executing INSERT, UPDATE, and DELETE statements - DML Statements - we use the executeUpdate() method of PreparedStatement class. 
			// The executeUpdate() method returns the number of rows updated in the table. 

			System.out.println("Number of rows updated in Database : " + noOfRowsUpdated);

		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
```

![](imgfiles\chap70\2023-02-28-20-32-58.png)
![](imgfiles\chap70\2023-02-28-20-34-34.png)
![](imgfiles\chap70\2023-02-28-20-36-38.png)
![](imgfiles\chap70\2023-02-28-20-39-10.png)


## Demo 2: `executeQuery()`

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class Main {

	// Important :: To run this code, use the 'Run Java' option instead of 'Run
	// Code'.
	// Otherwise the code will throw "java.sql.SQLException: No suitable driver
	// found for jdbc:mysql://localhost:3306/" error message -- on using the 'Run
	// Code' option.
	// You can also use the 'Run' option from the "Run|Debug" just below this
	// comment.
	public static void main(String[] args) {
		String DBConnectionURL = "jdbc:mysql://localhost:3306/pritamdb";
		// mysql = Database Service Provider
		// localhost = IP/Server Address
		// 3306 = PortNo.
		// pritamdb = database_name
		String DBUsername = "sqluser"; // connection_username
		String DBPassword = "password"; // connection_password

		try {
			// Creating the connection
			Connection connection = DriverManager.getConnection(DBConnectionURL, DBUsername, DBPassword);
			System.out.println("Connected to Database Successfully!");

			// PreparedStatement - Holds the SQL Query - SELECT Statement
			String rsql = "SELECT * FROM employees";
			PreparedStatement pStatement = connection.prepareStatement(rsql);
			ResultSet resultSet = pStatement.executeQuery();
			// 'result' object of 'ResultSet' class holds the data that we recieve after
			// executing the SELECT query over our database 'pritamdb'.
			// For executing the SELECT Statements (DDL Statements), we use the executeQuery() method of
			// PreparedStatement class.
			// The executeQuery() method returns - the data retrieved from the database - in form of a ResultSet class object.
			// The ResultSet object maintains a pointer - that is initially pointing at 'the position' just before the first row of the data.
			// A default ResultSet object is not updatable and has a cursor that moves forward only.

			// Printing out the result
			while (resultSet.next()) { // Traverse through all the rows till there is no row left.
										// On each invocation of the next() method, the pointer present inside the 'resultSet' object, moves to the next row and returns 'true'.
										// If there are no more rows left - next() method returns 'false'.
				System.out.println("Employee Id: " + resultSet.getInt("id"));
				System.out.println("Age : " + resultSet.getInt("age"));
				System.out.println("First Name: " + resultSet.getString("first"));
				System.out.println("Last Name: " + resultSet.getString("last"));
				System.out.println("**********************************");

				// "id", "age", "first", "last" are respective column names of the employee
				// table - passesd as arguments.
			}

		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
```

## Demo 3 : Scrollable ResultSet 

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class Main {

	// Important :: To run this code, use the 'Run Java' option instead of 'Run
	// Code'.
	// Otherwise the code will throw "java.sql.SQLException: No suitable driver
	// found for jdbc:mysql://localhost:3306/" error message -- on using the 'Run
	// Code' option.
	// You can also use the 'Run' option from the "Run|Debug" just below this
	// comment.
	public static void main(String[] args) {
		String DBConnectionURL = "jdbc:mysql://localhost:3306/pritamdb";
		// mysql = Database Service Provider
		// localhost = IP/Server Address
		// 3306 = PortNo.
		// pritamdb = database_name
		String DBUsername = "sqluser"; // connection_username
		String DBPassword = "password"; // connection_password

		try {
			// Optional Step - Implicitly performed by DriverManager.getConnection() method.
			// Creating an object of the "com.mysql.cj.jdbc.Driver" class and registering
			// the Driver with Driver Manager.
			Class.forName("com.mysql.cj.jdbc.Driver");

			// Creating the connection
			Connection connection = DriverManager.getConnection(DBConnectionURL, DBUsername, DBPassword);
			System.out.println("Connected to Database Successfully!");

			// PreparedStatement - Holds the SQL Query - SELECT Statement
			String rsql = "SELECT * FROM employees";
			PreparedStatement pStatement = connection.prepareStatement(rsql, ResultSet.TYPE_SCROLL_INSENSITIVE,
					ResultSet.CONCUR_READ_ONLY);
			// A default ResultSet object has a cursor that moves in forward direction only.
			// ResultSet.TYPE_SCROLL_INSENSITIVE = In the TYPE_SCROLL_INSENSITIVE ResultSet,
			// the cursor moves in forward or backward directions. This type of ResultSet is
			// insensitive to the changes that are made in the database. Example - Let’ say
			// you have multiple users in the database. You issued select query at 1:00.
			// Than some other user updated the underlying database at 1:01. With
			// TYPE_SCROLL_INSENSITIVE ResultSet, at 1:02 you will still be scrolling (using
			// next(), previous(), first(), last(), absolute() and relative() methods) at
			// old data fetched the at 1:00 and not the updated one.
			// ResultSet.CONCUR_READ_ONLY means that the ResultSet can only be read.
			// ResultSet.CONCUR_UPDATABLE means that the ResultSet can be both read and
			// updated.

			ResultSet scrollableResultSet = pStatement.executeQuery();
			// 'result' object of 'ResultSet' class holds the data that we recieve after
			// executing the SELECT query over our database 'pritamdb'
			// For executing the SELECT Statements, we use the executeQuery() method of
			// PreparedStatement class.

			System.out.println("Initial scrollableResultSet Pointer Position: " + scrollableResultSet.getRow());
			// 0
			// Initially the ResultSet pointer is pointing to an empty row just before the
			// 1st row of the table.

			scrollableResultSet.next();
			// Now the pointer moves to the 1st row of the table.
			System.out.println("Current pointer position after moving the pointer one step forward: "
					+ scrollableResultSet.getRow()); // 1
			System.out.println("Employee Id: " + scrollableResultSet.getInt("id")); // 1001
			System.out.println("Age: " + scrollableResultSet.getInt("age")); // 25
			System.out.println("First Name: " + scrollableResultSet.getString("first")); // Pritam
			System.out.println("Last Name: " + scrollableResultSet.getString("last")); // Kalita
			System.out.println("\n");

			scrollableResultSet.last(); // Moving the 'scrollableResultSet' pointer to the last row of the table.
			System.out.println("Current pointer position after moving the pointer to last row: "
					+ scrollableResultSet.getRow()); // 4
			System.out.println("Employee Id: " + scrollableResultSet.getInt("id")); // 1004
			System.out.println("Age: " + scrollableResultSet.getInt("age")); // 26
			System.out.println("First Name: " + scrollableResultSet.getString("first")); // Bikash
			System.out.println("Last Name: " + scrollableResultSet.getString("last")); // Kalita
			System.out.println("\n");

			scrollableResultSet.previous(); // Moving the 'scrollableResultSet' pointer to the 'previous' row before
											// last row of the table.
			System.out.println("Current pointer position after moving the pointer to the previous row before last row: "
					+ scrollableResultSet.getRow()); // 3
			System.out.println("Employee Id: " + scrollableResultSet.getInt("id")); // 1003
			System.out.println("Age: " + scrollableResultSet.getInt("age")); // 26
			System.out.println("First Name: " + scrollableResultSet.getString("first")); // Rohit
			System.out.println("Last Name: " + scrollableResultSet.getString("last")); // Ghosh
			System.out.println("\n");

			scrollableResultSet.absolute(2); // Moving the 'scrollableResultSet' pointer to row number 2 of the table.
			System.out.println("Current pointer position after moving the pointer to row no. 2 : "
					+ scrollableResultSet.getRow()); // 2
			System.out.println("Employee Id: " + scrollableResultSet.getInt("id")); // 1002
			System.out.println("Age: " + scrollableResultSet.getInt("age")); // 25
			System.out.println("First Name: " + scrollableResultSet.getString("first")); // Pradhugyna
			System.out.println("Last Name: " + scrollableResultSet.getString("last")); // Pal
			System.out.println("\n");
		}

		catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
```

![](imgfiles\chap70\2023-03-01-13-23-55.png)


## Demo 4: ResultSetMetaData Class

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.SQLException;

public class Main {

	public static void main(String[] args) {
		String DBConnectionURL = "jdbc:mysql://localhost:3306/pritamdb";

		String DBUsername = "sqluser";
		String DBPassword = "password";

		try {

			Class.forName("com.mysql.cj.jdbc.Driver");
			Connection connection = DriverManager.getConnection(DBConnectionURL, DBUsername, DBPassword);
			System.out.println("Connected to Database Successfully!");
			String rsql = "SELECT * FROM employees";
			PreparedStatement pStatement = connection.prepareStatement(rsql);
			ResultSet resultSet = pStatement.executeQuery();

			ResultSetMetaData metaData = resultSet.getMetaData();  //  Retrieving the metadata from the resultSet.

			System.out.println("Number of Columns: " + metaData.getColumnCount()); // 4
			System.out.println("Column 1 Name: " + metaData.getColumnName(1)); // id
			System.out.println("Column 1 Type: " + metaData.getColumnType(1)); // 4 - code for INTEGER type
			System.out.println("Column 1 Precision: " + metaData.getPrecision(1)); // 10

		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}
```