[👈 **_Back_**](../index.md)

# Stored Procedure

A stored procedure is a set of SQL statements that are stored in a database and can be called by name to perform a specific task.
Stored procedure are typically created using SQL commands or a visual database objects

Here's a simple ex of a stored procedure in MySQL that takes input parameter and returns a result set

```sql
    CREATE PROCEDURE get_customer_by_name (IN customer_name VARCHAR(255))
    BEGIN
        SELECT * FROM customers WHERE name=customer_name;
    END
```

This stored procedure takes a single input parameter called `customer_name`, which is a String value.
When the stored procedure is called, it executes a `SELECT` statement that retrieves all the rows from the `customers` table where the `name` column matches input parameter.
To call this stored procedure from a JDBC application, we would create a CallableStatement object and set the input parameter using the `setString` method

```java
    CallableStatement cstmt = conn.prepareCall("{call get_customer_by_name(?)}");
    cstmt.setString(1, "manoj");
    ResultSet rs = cstmt.executeQuery();
```
