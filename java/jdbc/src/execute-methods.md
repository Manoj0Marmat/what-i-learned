[👈 **_Back_**](../index.md)

# Execute Methods

1. `executeQuery()`
   This method is used to execute a `SELECT` statement and returns a [ResultSet](./result-set-methods.md) object that contains the data produced by the statement.
   ```java
       [ResultSet](./src/result-set-methods.md) rs = stmt.executeQuery("SELECT * FROM mytable");
   ```
2. `executeUpdate()`
   This method is used to execute `INSERT`, `UPDATE`, or `DELETE` statement and returns an int value indicating the number of rows affected by the statement.
   ```java
       int rowAffected = stmt.executeUpdate("UPDATE mytable SET name='manoj' WHERE id=1");
   ```
3. `execute()`
   This method is used to execute a SQL statement and returns a boolean value indicating whether the satement produced a [ResultSet](./result-set-methods.md) object or not.
   ```java
       boolean hasResultSet = stmt.execute("SELECT * FROM mytable");
       if(hasResultSet){
           // process the result set
       }else{
           int rowAffected = stmt.getUpdateCount();
           // process the row affected
       }
   ```
4. `executeBatch()`
   This method is used to execute batch of SQL statements a single unit and returns an array of int values indicating the number of rows affected by each statement.
   ```java
       stmt.addBatch("INSERT INTO mytable (id, name, age) VALUES (1, 'Manoj', 22)");
       stmt.addBatch("INSERT INTO mytable (id, name, age) VALUES (2, 'Rutik', 22)");
       int[] rowsAffected = stmt.executeBatch();
   ```
5. `executeQuery(String sql, String[] columnNames)`
   This method is used to execute an `INSERT` statement and returns a [ResultSet](./result-set-methods.md) object that contains the generated keys specified by the columnNames parameter.
   ```java
       PreparedStatement pstmt = conn.prepareStatement("INSERT INTO mytable (name, age) VALUES (?, ?)", new String[] {"id"});
       pstmt.setString(1, "Manoj");
       pstmt.setInt(2, 22);
       pstmt.executeQuery();
       ResultSet rs = pstmt.getGeneratedKeys();
       if(rs.next()){
           int id = rs.getInt(1);
           // use the generated id
       }
   ```
