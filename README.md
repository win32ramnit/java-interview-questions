# Java Interview Questions and Answers
Core Java interview questions for both experience &amp; fresher 
<hr/>

### **Question 1:**
We cannot create an object for an **abstract** class, but an abstract class can contain a constructor. What is the need for it?

### **Answer:**
<span style="color:BALCK">
The constructor of an abstract class is responsible for initializing the member variables of a child object, specifically those instance variables that are inherited from the parent class.
For exmaple:

```java
class Employee {
    private String name;
    private double salary;
    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }
}

class Manager extends Employee {
    private double bonus;
    public Manager(String name, double salary, double bonus) {
        super(name, salary); // calling Employee's constructor
        this.bonus = bonus;
    }
}

class Test {
    public static void main(String[] args) {
        Manager tony = new Manager("Tony", 800000.0, 15000.0);
    }
}
```
Whenever we create a child class (manager class) object, the parent constructor (Employee's constructor, referred to as 'super' in the child class) is automatically executed to perform initialization for the instance variables that are inherited from the parent class.
</span>

### **Question 2:**
What is the need of executing parent's constructor?

### **Answer:**
[See answer in the Question 1](#question-1)

### **Question 3:**
Is it true that a parent class object is automatically created whenever we create a child class object?
### **Answer:**
<span>
No, it is not true that a parent class object is automatically created whenever we create a child class object. Each class, including the parent and child classes, has its own separate object. However, the child class object can inherit certain properties and behaviors from the parent class.
Let see with this example:

```java
class Parent {
    public Parent() {
        System.out.println(this.hashCode()); // 366712642
    }
}

class Child extends Parent {
    public Child() {
    	System.out.println(this.hashCode()); // 366712642
    }
}

public class Test {
    public static void main(String[] args) {
    	Child child = new Child();
        System.out.println(child.hashCode()); // 366712642
    }
}
OUTPUT: 
366712642
366712642
366712642
```
As we can see, both the child and parent produce the same hashcode. This means that whenever we create a child object, the parent object will not be created. Hence, it is proven.
</span>
