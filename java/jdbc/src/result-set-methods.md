[👈 **_Back_**](../index.md)

# Methods in ResultSet

1. `next()`
   This method is used to move the cursor to the next row in the result set. It returns a boolean value indicating whether there is a next row or not.
   ```java
       while(rs.next()){
           // process the current row
       }
   ```
2. `getXxx()`
   These methods are used to retrieve the values of the columns in the current row. The Xxx represents the data type of the column. For ex. getInt(), getString(), getDate().
   ```java
       int id = rs.getInt("id");
       String name = rs.getString("name");
       Date date = rs.getDate("date");
   ```
3. `getObject()`
   This method is used to retrieve the value of a column in the current row as an Object.
   ```java
       Object obj = rs.getObject("column_name");
   ```
4. `wasNull()`
   This method is used to check whether the value of the last column retrieved using `getXxx()` was null or not.
   ```java
       int age = rs.getInt("age");
       if(rs.wasNull()){
           // age is null
       }
   ```
5. `getMetaData()`
   This method is used to retrieve the ResultSetMetaData object that contains metadata about the columns in the result set.
   ```java
       ResultSetMetaData meta = rs.getMetaData();
       int columnCount = meta.getColumnCount();
       String columnName = meta.getColumnName(1);
   ```
6. `beforeFirst()`
   This method is used to move the cursor to before the first row in result set.
   ```java
       rs.beforeFirst();
   ```
7. `absolute()`
   This method is used to move the cursor to a specific row in the result set.
   ```java
       rs.absolute(3);
   ```
8. `updateXxx()`
   These method are used to update the values of the columns in the current row. The Xxx represents the data type of the column For ex. getInt(), getString(), getDate().
   ```java
       rs.updateInt("age", 23);
       rs.updateRow();
   ```
