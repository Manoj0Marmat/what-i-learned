[👈 **_Back_**](./index.md)

# Composition

Has-a relationship is similar to **Whole&Part** relationship, where one object is used by another objects as it's property.

##### Example

1.  Car has an Engine

    ```lua
        +----------+           +-------------+
        |    Car   |           |  Engine     |
        +----------+           +-------------+
        |  make    |           |  model      |
        |  engine  |<--------+ |  horsepower |
        |  year    |           +-------------+
        |  model   |
        +----------+
    ```

    ###### Engine Blueprint Class

    ```java
    class Engine{
        String model;
        double horsePower;

        public Engine(String model, double horsePower){
            this.model = model;
            this.horsePower = horsePower;
        }
    }
    ```

    ###### Car Blueprint Class

    ```java
    class Car{
        String make;
        Engine engine;
        int year;
        String model;

        public Car(String make, Engine engine, int year, String model){
            this.make = make;
            this.engine = engine;
            this.year = year;
            this.model = model;
        }
    }
    ```

    ###### Car User Logic Class

    ```java
    Car jaguar = new Car("make", new Engine("x012", 289.9), 2022, "jx02");
    ```

    > [!NOTE] > `Engine engine` property of Car Class forming Composition here

2.  House has Room

    ```lua
        +----------+           +----------+
        |   House  |           |   Room   |
        +----------+           +----------+
        |  address |           |  number  |
        |  rooms   |<--------+ |  type    |
        |  owner   |           |  size    |
        +----------+           +----------+
    ```

    ###### Room Blueprint class

    ```java
    class Room{
        int number;
        String type;
        int size;
        public Room(int number, String type, int size){
            this.number = number;
            this.type = type;
            this.size = size;
        }
    }
    ```

    ###### House Blueprint class

    ```java
    class House{
        String address;
        Room rooms;
        String owner;

        public House(String address, Room rooms, String owner){
            this.address = address;
            this.rooms = rooms;
            this.owner = owner;
        }
    }
    ```

    ###### House User Login Class

    ```java
    House house = new House("Ameerpet,Hy", new Room(2, "living", 100), "Subbarao Anna");
    ```

    > [!NOTE] > `Room rooms` property of House Class forming Composition here

3.  Person has Address

    ```lua
        +----------+           +----------+
        |  Person  |           |  Address |
        +----------+           +----------+
        |  name    |           |  street  |
        |  address |<--------+ |  city    |
        |  gender  |           |  state   |
        |  age     |           +----------+
        +----------+
    ```

    ###### Address Blueprint Class

    ```java
    class Address{
        String street;
        String city;
        String state;

        public Address(String street, String city, String state){
            this.street = street;
            this.city = city;
            this.state = state;
        }
    }
    ```

    ###### Person Blueprint Class

    ```java
    class Person{
        String name;
        Address address;
        String gender;
        int age;

        public Person(String name, Address address, String gender, int age){
            this.name = name;
            this.address = address;
            this.gender = gender;
            this.age = age;
        }
    }
    ```

    ###### Person User Logic Class

    ```java
    Person person = new Person("manoj marmat", new Address("ammerpet road", "Hy", "Telangana"), "male", 22);
    ```

    > [!NOTE] > `Address address` property of Person Class forming Composition here
