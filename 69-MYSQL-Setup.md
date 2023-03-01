# Downloading MYSQL

1. Search '**mysql**' on Google
1. Go to the Official Website Link (**https://www.mysql.com**) of MySQL.
1. Go to **Downloads** -> Scroll to the bottom -> Click on "**MySQL Community (GPL) Downloads**".
1. Click on **MySQL Installer for Windows**.
1. **Download** the **437.3 MB- Windows (x86, 32-bit), MSI Installer** -> Click on **No thanks, just start my download.**.


# Installing MYSQL

1. Open the Installer File.
1. Select **Custom Installation**.
1. Select the following MySQL Products to **install** - **MySQL Server**.
1. Keep rest of the settings and options on **default** and keep hitting **Next** -> **Execute**-> **Next** -> until you reach the **Accounts and Roles** Page. 
1. On the  **Accounts and Roles** Page fill up the a **MYSQL Root Password** and **Repeat Password** fields. (*You can choose any password of your choice*) -> **Next** -> You can uncheck the **"Start the MySQL Server System Startup"** box -> **Next** -> **Execute**
1. **Finish** -> **Next** -> **Finish** -> The Installation is **completed**.


# Adding Path To Environment Variables

1. Copy the path - **C:\Program Files\MySQL\MySQL Server 8.0\bin**.
1. Go to **Start Menu** -> search for "Environment Variables" -> Select **Edit the System Environment Variables** -> **Environment Variables**.
1. Under **System variables** sections, select **Path** -> **Edit** -> **New** -> Paste the address **C:\Program Files\MySQL\MySQL Server 8.0\bin**.


# Basic Commands (*Use Command Prompt to run the below commands - VS Code Terminal wont work here*)

1. To check the version of **MySQL** installed on your system, open **Command Prompt** and run the following command : `mysql --version`
1. **Starting the MYSQL Server from the Command Prompt** : 
    - Run the following command : `mysql -u root -p`
    - Enter the **root password** **(dynamic@3)** -> **Enter**.
1. **To check the default databases** -> **after doing the above step** -> run the following command from the **same** **Command Prompt Terminal** : `show databases;`
1. **To create a new database**, run the following command from the **same Command Prompt Terminal where we have started the MySQL Server**: `create database database_name;` -> **Enter**.
1. Now if you run `show databases;` command, you can see the name of the newly created database in the list.


# Setting Up MySQL in VS Code:

1. Open **Command Prompt** -> Run the commands:
    ```bash
    mysql --version

    # Starting the MySQL Server
    mysql -u root -p
    # Provide password = dynamic@3

    # Creating a MySQL User called 'sqluser' which will use a password i.e. 'password'
    CREATE USER 'sqluser'@'%' IDENTIFIED WITH mysql_native_password BY 'password';

    # Granting all privileges to the 'sqluser' user.
    GRANT ALL PRIVILEGES ON *.* TO 'sqluser'@'%';

    FLUSH PRIVILEGES;
    ```
1. Close the connection - `exit`.
1. Close the Commmand Prompt - `exit`.
1. Open the **VS Code** -> **Extensions**.
1. Search for **SQLTools** Extension -> **Install** it.
1. Search for **SQLTools MySQL/MariaDB** Extension -> **Install** it.
1. **To Create A New Connection In The Current Folder Opened In VS Code** 
    - Open the **SQLTools** Extension from the left-side bar of **VS Code** window 
    - Click on **Add new connection**.
    - Under the **Connection Assistant** -> Select **MySQL** database driver.
    - Fillup the fields **Connection Name = mysql** *(connection name is your choice)*, **Database = pritamdb** *(we have to give name of an existing database that has **already been created** from the **Command Promt** previously)*, **Username = sqluser** *(previously set from Command Prompt)*, **Use Password = Save as plaintext in settings**, **Password = password** *(previously set from Command Prompt)*.
    - Click on **Save Connection**.
1. Now you can see the new connection **mysql** under the **SQLTools Extension** -> **CONNECTIONS** Tab.<br>
![](imgfiles\chap69\2023-02-27-22-18-06.png)
1. **Hover** the mouse pointer over **mysql** connection and select the *green-colored* **Connect** icon. Now the **mysql** connection is up and running. This also opens the **mysql.session.sql** file, where we can pass our Queries and work with all the **mysql** connection's **databases**. If we save the **mysql.session.sql** file, it gets saved in the **currently open folder** in **VS Code** *(Youtube)* <br> 
![](imgfiles\chap69\2023-02-27-22-19-45.png)
![](imgfiles\chap69\2023-02-27-23-00-20.png)
1. If we accidentally close the **mysql.session.sql** file in **VS Code** -- without saving it, we can open a new SQL file using this button:<br>
![](imgfiles\chap69\2023-02-27-23-04-55.png)
1. If we expand the **mysql** connection, we can see the **pritamdb** database that we have added to this connection while creating it.
1. Now, if we create a **new database** using the `create database cardb;` command from **Command Prompt**, it will show up under the **mysql** connection in **VS Code**.<br>
![](imgfiles\chap69\2023-02-27-22-45-03.png)
1. We can also create a new database from the **mysql.session.sql** file in **VS Code** using this query:
```sql
CREATE DATABASE studentdb
```
13. After writting the query, click on **Run on active connection**.
1. **Refresh** the connection once if you do not to see the database name appear oon the list.<br>
![](imgfiles\chap69\2023-02-27-23-25-36.png)
1. Query for Deleting Databases:
```sql
DROP DATABASE studentdb;
DROP DATABASE cardb;
```


# Query for creating a Table in the `pritamdb` database

```sql
CREATE TABLE pritamdb.employees
(
   id INT NOT NULL PRIMARY KEY,
   age INT NOT NULL,
   first VARCHAR(255),
   last VARCHAR(255)
);
```

- database_name = pritamdb , table_name = employees
- Click **Run on active connection**.
- **Refresh** the connection once if you do not to see the newly created table inside **pritamdb->Tables**. <BR>
![](imgfiles\chap69\2023-02-28-11-09-01.png)

- You can see two icons beside the **employees** Table at 
**pritamdb->Tables->employees** - **Generate Insert Query** & **Show Table Records**.


# Query for inserting values in the Table in the `pritamdb` database

```sql
INSERT INTO pritamdb.employees (id, age, first, last)
VALUES (
    1001,
    25,
    'Pritam',
    'Kalita'
  );
```

- database_name = pritamdb , table_name = employees
- Click **Run on active connection**.
- To see the contents of this table just click on the **magnifyingGlass** button at **pritamdb->Tables->employees**.<br>
![](imgfiles\chap69\2023-02-28-11-17-40.png)