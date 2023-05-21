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
    public Employee(String name, salary) {
        this.name = name;
        this.salary = salary;
    }
}

class Manager extends Employee {
    private double bonus;
    public Manager(String name, salary, double bonus) {
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

