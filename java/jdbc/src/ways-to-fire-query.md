[👈 **_Back_**](../index.md)

# Three Ways to Fire A Query Using JDBC

1. **Using Statement Object :**
   The simplest way to fire a query in JDBC is to use a Statement object. We can Create a Statement object using `createStatement()` method of the Connection object, and the execute a query using `executeQuery()` method of the Statement object.
   ```java
       Connection conn = DriverManger.getConnection(url, userName, password);
       Statement stmt = conn.createStatement();
       ResultSet rs = stmt.executeQuery("SELECT * FROM mytable");
   ```
2. **Using a PreparedStatement object :**
   A PreparedStatement object allows you to execute a query multiple times with different parameter values. We can create PreparedStatement object using the `prepareStatement()` method of the Connection object, and then execute the query using the `executeQuery()` method of the PreparedStatement object.
   ```java
       Connection conn = DriverManager.getConnection(url, userName, password);
       PreparedStatement pstmt = conn.prepareStatement("SELECT * FROM mytable WHERE id = ?");
       pstmt.setInt(1, 123);
       ResultSet rs = pstmt.executeQuery();
   ```
3. **Using CallableStatement object :**
   A CallableStatement object allows us to execute a stored procedure in the database. we can create CallableStatement object using the `prepareCall()` method of the Connection object, and then execute the [stored procedure](./stored-procedure.md) using the `execute()` method of the CallableStatement object.
   ```java
       Connection conn = DriverManager.getConnection(url, userName, password);
       CallableStatement cstmt = conn.prepareCall("{call myproc(?, ?)}");
       cstmt.setInt(1, 123);
       cstmt.setString(2, "test");
       ResultSet rs = cstmt.executeQuery();
   ```
