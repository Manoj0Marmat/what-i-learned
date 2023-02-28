# Java DataBase Connectivity

it is Java Api for accessing relational datatbase.

##### Steps to Use JDBC in Java Program

1. **Load the [JDBC Driver](./src/driver.md) :**
   First, we need to load the [JDBC driver](./src/driver.md) for database we want to connect to.

   ```java
       Class.forName("com.mysql.cj.jdbc.Driver");
   ```

2. **Establish a connection :**
   Once driver is loaded, you can establish a connection to the database using the `DriverManager.getConnection()` method. This method takes a URL that specifies database to connect to, as well as a username and password.

   ```java
       String url = "jdbc:mysql://localhost:3306/<db_name>";
       String userName = "root";
       String password = "1234567";

       Connection conn = DriverManager.getConnection(url, userName, password);
   ```

3. [**Create a Statement :**](./src/ways-to-fire-query.md)
   After establishing a connection, we need to create a statement object that will be used to execute sql statements. the statement can be created using the `Connection.createStatement()` method.
   ```java
       Statement stmt = conn.createStatement();
   ```
4. [**Execute a query:**](./src/execute-methods.md)
   Once you have a statement object, we can execute SQL queries using its `executeQuery()` method. This method returns a [ResultSet](./src/result-set-methods.md) object that contains the results of the query.
   ```java
       ResultSet rs = stmt.executeQuery("SELECT * FROM table");
   ```
5. **[Process the Results :](./src/process-the-results.md)**
   You can process the results of the query by iterating over the [ResultSet](./src/result-set-methods.md) object using its `next()` method. This method returns true if there is another row in the result set, and false if there are no more rows.
   ```java
       while(rs.next()){
           int id = rs.getInt("Id");
           String name = rs.getString("name");
           int age = rs.getInt("age");
           // process the row...
       }
   ```
6. **Close the Resources :**
   Once we have finished using [ResultSet](./src/result-set-methods.md), Statement, and Connection objects, we should close them to free up any resources they are holding.
   ```java
       rs.close();
       stmt.close();
       conn.close();
   ```
