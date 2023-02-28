[👈 **_Back_**](../index.md)

# Process the Result

Suppose we have a table named "student" in a MySQL database with the following col:
| id |name| age|grade|
|----|----|----|-----|
|1|Alice|18|95|
|2|Bob|17|82|
|3|Charlie|16|74|
To retrieve all the rows from the "student" table using JDBC, we could use the following code :

```java
    String url = "jdbc:mysql://localhost:3306/mydatabase";
    String userName = "test";
    String password = "pass@123";

    Connection conn = DriverManager.getConnection(url, userName, password);

    Statement stmt = conn.createStatement();

    ResultSet rs = stmt.executeQuery("SELECT * FROM students");

    while(rs.next()){
        int id = rs.getInt("id");
        String name = rs.getString("name");
        int age = rs.getInt("age");
        int grade = rs.getInt("grade");
        System.out.println("id: "+id+", name: "+name+", age: "+age+", grade: "+grade);
    }

    rs.close();
    stmt.close();
    conn.close();
```

**Output**

```sql
    id = 1, name = Alice, age = 18, grade = 95
    id = 2, name = Bob, age = 17, grade = 82
    id = 3, name = Charlie, age = 16, grade = 74

```
