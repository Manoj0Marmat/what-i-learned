# Encapsulation

It is the process wrapping the properties & behaviours of an object whithin a single unit of a class.

##### Ways to Perform

1. make properties **private** who's have some valid ranges/need to perform some validation on them
2. add _getters & setters_ to perform read & write on only **\*private** properties\*

##### Advantages

1. Code Reusebility
2. Security
3. Controlled Access
4. Data Hiding

##### Example

###### Blueprint Class

```java
class Vote{
    String name;
    private int age;
    private long adhar;

    // default constructor
    public Vote(){
        this.name = "manoj marmat";
        this.age = 22;
        this.adhar = 123456789101l;
    }

    // parameterized constructor
    public Vote(String name, int age, long adhar){
        if(age>=18 && (int)(Math.log10(adhar)+1)==12){
            this.name = name;
            this.age = age;
            this.adhar = adhar;
        }
    }

    // getters && setters only for private properties
    public int getAge(){
        return this.age;
    }

    // setter with validation
    public void setAge(int age){
        if(age>=18){
            this.age = age;
        }
    }

    public long getAdhar(){
        return this.adhar;
    }

    // setter with validation
    public void setAdhar(long adhar){
        if((int)(Math.log10(adhar) == 12)){
            this.adhar = adhar;
        }
    }

}
```
