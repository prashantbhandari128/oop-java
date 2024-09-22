# Object Oriented Programming Concepts

## Fundamental of Classes
-------------------------
A class is a user defined blueprint or prototype from which objects are created.  It represents the set of properties or methods that are common to all objects of one type. In general, class declarations can include these components, in order:

* **Modifiers:** A class can be public or has default access
.
* **``class`` keyword:** class keyword is used to create a class.

* **Class name:** The name should begin with an initial letter (capitalized by convention).

* **Superclass(if any):** The name of the class’s parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.

* **Interfaces(if any):** A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.

* **Body:** The class body surrounded by braces, ``{ }``.

Syntax to declare a class:

```Java
class <class_name>{
    field;  
    method;  
}  
```
Example:

```Java
public class Bicycle {
  // state or field
  private int gear = 5;
  // behavior or method
  public void braking() {
    System.out.println("Working of Braking");
  }
}
```
## Object
---------

An object is called an instance of a class. For example, suppose ``Bicycle`` is a class then ``MountainBicycle``, ``SportsBicycle``, ``TouringBicycle``, etc can be considered as objects of the class.

An object has three characteristics:

* **State:** It is represented by attributes of an object. It also reflects the properties of an object.
* **Behavior:** It is represented by methods of an object. It also reflects the response of an object with other objects.
* **Identity:** It gives a unique name to an object and enables one object to interact with other objects.

Here is how we can create an object of a class.

Syntax:

```Java
className object = new className();
```

Example:

```Java
Bicycle sportsBicycle = new Bicycle();
Bicycle touringBicycle = new Bicycle();
```
We have used the ``new`` keyword along with the constructor of the class to create an object.

Here, ``sportsBicycle`` and ``touringBicycle`` are the names of objects. We can use them to access fields and methods of the class.

As you can see, we have created two objects of the class. We can create multiple objects of a single class in Java.

## Instance variable in Java
----------------------------

A variable which is created inside the class but outside the method is known as an instance variable. Instance variable doesn't get memory at compile time. It gets memory at runtime when an object or instance is created. That is why it is known as an instance variable.

## Access Members of a Class
-----------------------------
We can use the name of objects along with the . operator to access members of a class. For example,

```Java
public class Bicycle {
  // field of class
  int gear = 5;
  // method of class
  void braking() {
      System.out.println("Working of Braking");
  }
}

// create object
Bicycle sportsBicycle = new Bicycle();
// access field and method
sportsBicycle.gear;
sportsBicycle.braking();
```
In the above example, we have created a class named ``Bicycle``. It includes a field named ``gear`` and a method named ``braking()``. Notice the statement,

```Java
Bicycle sportsBicycle = new Bicycle();
```

Here, we have created an object of ``Bicycle`` named ``sportsBicycle``. We then use the object to access the field and method of the class.

* ``sportsBicycle.gear`` - access the field ``gear``
* ``sportsBicycle.braking()`` - access the method ``braking()``

## Abstraction
---------------
In **OOP**, abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it.

There are two ways to achieve abstraction in java:

* Abstract class (0 to 100%)
* Interface (100%)

### **Abstract class in Java**
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated.

**Syntax of declaring an abstract class:**

To declare an abstract class we use the keyword ``abstract``. The syntax is given below:

```Java
abstract class ClassName{
    //class body
}
```

**Example:**

```Java
abstract class A{}  
```

### **Abstract method in Java**
A method which is declared as abstract and does not have implementation is known as an abstract method. 

**Syntax of declaring abstract methods:**

```Java
access_specifier abstract return_type method_name();
```

**Example:**

```Java
abstract void printStatus(); //no method body and abstract  
```

## Encapsulation
-----------------
**Encapsulation** is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates. Another way to think about encapsulation is, it is a protective shield that prevents the data from being accessed by the code outside this shield. 

Advantages of Encapsulation:  

* **Data Hiding:** The user will have no idea about the inner implementation of the class. It will not be visible to the user how the class is storing values in the variables. The user will only know that we are passing the values to a setter method and variables are getting initialized with that value.

* **Increased Flexibility:** We can make the variables of the class read-only or write-only depending on our requirement. If we wish to make the variables read-only then we have to omit the setter methods like setName(), setAge(), etc.  or if we wish to make the variables as write-only then we have to omit the get methods like getName(), getAge(), etc.

* **Reusability:** Encapsulation also improves the re-usability and is easy to change with new requirements.

* **Testing code is easy:** Encapsulated code is easy to test for unit testing.

### **Get and Set**

``private`` variables can only be accessed within the same class (an outside class has no access to it). However, it is possible to access them if we provide public ``get`` and ``set`` methods.

The ``get`` method returns the variable value, and the ``set`` method sets the value.

Syntax for both is that they start with either get or set, followed by the name of the variable, with the first letter in upper case:`

```Java
public class Person {
    private String name; // private = restricted access
    // Getter
    public String getName() {
        return name;
    }
    // Setter
    public void setName(String newName) {
        this.name = newName;
    }
}
```

Example explained

* The ``get`` method returns the value of the variable name.

* The ``set`` method takes a parameter ``(newName)`` and assigns it to the name variable. The ``this`` keyword is used to refer to the current object.

## Using ``this`` keyword
--------------------------
``this`` keyword in Java is a reference variable that refers to the current object of a method or a constructor. The main purpose of using this keyword in Java is to remove the confusion between class attributes and parameters that have same names.

Following are various uses of ``this`` keyword in Java:

* It can be used to refer instance variable of current class
* It can be used to invoke or initiate current class constructor
* It can be passed as an argument in the method call
* It can be passed as argument in the constructor call
* It can be used to return the current class instance

## Constructors 
----------------
In Java, a constructor is a block of codes similar to the method. It is called when an instance of the class is created. At the time of calling constructor, memory for the object is allocated in the memory.

It is a special type of method which is used to initialize the object.

Every time an object is created using the ``new()`` keyword, at least one constructor is called.

It calls a default constructor if there is no constructor available in the class. In such case, Java compiler provides a default constructor by default.

>It is called constructor because it constructs the values at the time of object creation. It is not necessary to write a constructor for a class. It is because java compiler creates a default constructor if your class doesn't have any.

Rules for creating constructor:

* Constructor name must be the same as its class name.
* A Constructor must have no explicit return type.
* A Java constructor cannot be abstract, static, final, and synchronized.

There are two types of constructors in Java:

* Default constructor (no-arg constructor)
* Parameterized constructor

### **Default constructor**

A constructor is called "Default Constructor" when it doesn't have any parameter.The default constructor is used to provide the default values to the object like 0, null, etc., depending on the type.

Syntax of default constructor:

```Java
<class_name>(){
  //body
}  
```

Example:

```Java
//Java Program to create and call a default constructor  
public class Bike {
    //creating a default constructor  
    Bike() {
        System.out.println("Bike is created");
    }
    //main method  
    public static void main(String args[]) {
        //calling a default constructor  
        Bike b = new Bike();
    }
}
```
### **Parameterized constructor**

A constructor which has a specific number of parameters is called a parameterized constructor. The parameterized constructor is used to provide different values to distinct objects. However, you can provide the same values also.

Example:

```Java
//Java Program to demonstrate the use of the parameterized constructor.  
public class Student {
    int id;
    String name;
    //creating a parameterized constructor  
    Student(int i, String n) {
        id = i;
        name = n;
    }
    //method to display the values  
    void display() {
        System.out.println(id + " " + name);
    }
    public static void main(String args[]) {
        //creating objects and passing values  
        Student s1 = new Student(111, "Karan");
        Student s2 = new Student(222, "Aryan");
        //calling method to display the values of object  
        s1.display();
        s2.display();
    }
}
```
## Java Methods
------------------------
A method is a collection of statements that perform some specific task and return the result to the caller. A method can perform some specific task without returning anything. Methods allow us to reuse the code without retyping the code.

### **Creating Method:**

Considering the following example to explain the syntax of a method

Syntax:

```Java
public static int methodName(int a, int b) {
   // body
}
```
Here,

* **public static** − modifier

* **int** − return type

* **methodName** − name of the method

* **a, b** − formal parameters

* **int a, int b** − list of parameters

### **Pass by Value and Pass by Reference in Java**

Pass by Value and Pass by reference is the two ways by which we can pass a value to the variable in a function.

* Pass by Value: It is a process in which the function parameter values are copied to another variable and instead this object copied is passed. This is known as call by Value.

* Pass by Reference: It is a process in which the actual copy of reference is passed to the function. This is called by Reference.

Talking about Java, we can say that Java is Pass by Value and not pass by reference.

### **Access Control**

Access specifier or modifier is the access type of the method. It specifies the visibility of the method. Java provides four types of access specifier:

* **Public**: The method is accessible by all classes when we use public specifier in our application.

* **Private**: When we use a private access specifier, the method is accessible only in the classes in which it is defined.

* **Protected**: When we use protected access specifier, the method is accessible within the same package or subclasses in a different package.

* **Default**: When we do not use any access specifier in the method declaration, Java uses default access specifier by default. It is visible only from the same package only.

### **Methods that Rerurns value**

A Java method may or may not return a value to the function call. We use the ``return`` statement to return any value. For example,

```Java
int addNumbers() {
  ...
  return (sum);
}
```

Here, we are returning the variable ``sum``. Since the return type of the function is ``int``. The sum variable should be of ``int`` type. Otherwise, it will generate an error.

>Note: If the method does not return any value, we use the ``void`` keyword as the return type of the method. For example:

```Java
public void square(int a) {
  int square = a * a;
  System.out.println("Square is: " + a);
}
```
## Polymorphism
--------------------------
The word polymorphism means having many forms.Polymorphism is considered one of the important features of Object-Oriented Programming. Polymorphism allows us to perform a single action in different ways. In other words, polymorphism allows you to define one interface and have multiple implementations. The word “poly” means many and “morphs” means forms, So it means many forms.

In Java polymorphism is mainly divided into two types:

* Compile time Polymorphism
* Runtime Polymorphism

### **(1) Compiled time Polymorphism:**
It is also known as static polymorphism. This type of polymorphism is achieved by function overloading or operator overloading. But **``Java doesn’t support the Operator Overloading``**.

**Method Overloading:** When there are multiple functions with same name but different parameters then these functions are said to be overloaded. Functions can be overloaded by ``change in number of arguments`` or/and ``change in type of arguments``.

Example:

```Java
// Java program for Method overloading
class MultiplyFun {
    // Method with 2 parameter
    static int Multiply(int a, int b) {
        return a * b;
    }
    // Method with the same name but 3 parameter
    static int Multiply(int a, int b, int c) {
        return a * b * c;
    }
    // Method with the same name but 2 double parameter
    static double Multiply(double a, double b) {
        return a * b;
    }
}
class Main {
    public static void main(String[] args) {
        System.out.println(MultiplyFun.Multiply(2, 4));
        System.out.println(MultiplyFun.Multiply(5.5, 6.3));
        System.out.println(MultiplyFun.Multiply(2, 7, 3));
    }
}
```

### **(2) Runtime Polymorphism:**
It is also known as **Dynamic Method Dispatch**. It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by **Method Overriding**.

Method overriding, on the other hand, occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.

Examnple:

```Java
// Java program for Method overriding
class Parent {
    void Print() {
        System.out.println("parent class");
    }
}
class subclass1 extends Parent {
    void Print() {
        System.out.println("subclass1");
    }
}
class subclass2 extends Parent {
    void Print() {
        System.out.println("subclass2");
    }
}
public class Program {
    public static void main(String[] args) {
        Parent a;
        a = new subclass1();
        a.Print();
        a = new subclass2();
        a.Print();
    }
}
```
Output:

```
subclass1
subclass2
```

## Nested and Inner Classes
----------------------------
Java inner class or nested class is a class that is declared inside the class or interface.

We use inner classes to logically group classes and interfaces in one place to be more readable and maintainable.

Additionally, it can access all the members of the outer class, including private data members and methods.

```Java
class OuterClass {
  // ...
  class NestedClass {
    // ...
  }
}
```

There are two types of nested classes you can create in Java.

* Static Nested Class
* Non-Static Nested Class

### **Static Nested Class**

* We Can define an inner class as static, so such type of classes is called a ``static nested class.``
* The ``nested class`` is defined with the ``static`` keyword, so this type of nested classes doesn’t share any relationship with the instance of an ``outer class``.
* A ``static nested class`` can able to access the ``static members`` of our class.

Example:

```Java
class Car {
    static class Wheel {
        public void rotate() {
            System.out.println("The wheel is rotating");
        }
    }
}
public class Test {
    public static void main(String args[]) {
        Car.Wheel wheel = new Car.Wheel();
        wheel.rotate();
    }
}
```
Output:
```
The wheel is rotating
```

### **Non-Static Nested Class**

* A ``non-static nested class`` is indirectly known as an ``inner class`` in Java.
* The ``inner class`` is associated with the ``object of the outer class``. So the inner class is treated like other variables and methods of the outer class.
* The ``inner class`` is associated with the outer class object or instance, so we ``can’t declare static variables`` inside the inner class.

Example:
```Java
public class OuterClassTest {
    private int a = 10;
    public void innerClassInstance() {
        InnerClassTest inner = new InnerClassTest();
        inner.outerObject();
    }
    class InnerClassTest {
        public void outerObject() {
            System.out.println("Outer Value of a is: " + a);
        }
    }
    public static void main(String args[]) {
        OuterClassTest outer = new OuterClassTest();
        outer.innerClassInstance();
    }
}
```

Output:
```
Outer Value of a is: 10
```

## Inheritance
------------------------

Inheritance is an important pillar of OOP ``(Object-Oriented Programming)`` . It is the mechanism in java by which one class is allowed to inherit the features ``(fields and methods)`` of another class. 

### **Types of Inheritance in Java**

Below are the different types of inheritance which are supported by Java. 

* Single Inheritance
* Multilevel Inheritance
* Hierarchical Inheritance
* Multiple Inheritance
* Hybrid Inheritance

#### **Single Inheritance:**

In single inheritance, subclasses inherit the features of one superclass. 

Example:

```Java
class A {
    public void print_A() {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B() {
        System.out.println("This is Class B.");
    }
}
public class Single {
    public static void main(String[] args) {
        B m = new B();
        m.print_A();
        m.print_B();
    }
}
```

Output:
```
This is Class A.
This is Class B.
```

#### **Multilevel Inheritance:**

In Multilevel Inheritance, a derived class will be inheriting a base class and as well as the derived class also act as the base class to other class. In the below image, class A serves as a base class for the derived class B, which in turn serves as a base class for the derived class C. In Java, a class cannot directly access the grandparent’s members.

Example:

```Java
class A {
    public void print_A() {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B() {
        System.out.println("This is Class B.");
    }
}
class C extends B {
    public void print_C() {
        System.out.println("This is Class C.");
    }
}
public class Multilevel {
    public static void main(String[] args) {
        C m = new C();
        m.print_A();
        m.print_B();
        m.print_C();
    }
}
```

Output:
```
This is Class A.
This is Class B.
This is Class C.
```

#### **Hierarchical Inheritance:**

In Hierarchical Inheritance, one class serves as a superclass (base class) for more than one subclass.

Example:

```Java
class A {
    public void print_A() {
        System.out.println("This is Class A.");
    }
}
class B extends A {
    public void print_B() {
        System.out.println("This is Class B.");
    }
}
class C extends A {
    public void print_C() {
        System.out.println("This is Class C.");
    }
}
class D extends A {
    public void print_D() {
        System.out.println("This is Class D.");
    }
}
public class Hierarchical {
    public static void main(String[] args) {
        B m1 = new B();
        m1.print_A();
        m1.print_B();
        C m2 = new C();
        m2.print_A();
        m2.print_C();
        D m3 = new D();
        m3.print_A();
        m3.print_D();
    }
}
```

Output:
```
This is Class A.
This is Class B.
This is Class A.
This is Class C.
This is Class A.
This is Class D.
```

#### **Multiple Inheritance (Through Interfaces):**

In Multiple inheritances, one class can have more than one superclass and inherit features from all parent classes. Please note that Java does not support multiple inheritances with classes. In java, we can achieve multiple inheritances only through Interfaces.

Example:

```Java
interface A {
    public void print_Apple();
}
interface B {
    public void print_Ball();
}
interface C extends A, B {
    public void print_Cat();
}
class D implements C {
    public void print_Apple() {
        System.out.println("Apple");
    }
    public void print_Ball() {
        System.out.println("Ball");
    }
    public void print_Cat() {
        System.out.println("Cat");
    }
}
public class Multiple {
    public static void main(String[] args) {
        D m = new D();
        m.print_Apple();
        m.print_Ball();
        m.print_Cat();
    }
}
```

Output:
```
Apple
Ball
Cat
```

#### **Hybrid Inheritance(Through Interfaces):**

It is a mix of two or more of the above types of inheritance. Since java doesn’t support multiple inheritances with classes, hybrid inheritance is also not possible with classes. In java, we can achieve hybrid inheritance only through Interfaces. 

Example:

```Java
interface A {
    public void print_Apple();
}
interface B extends A {
    public void print_Ball();
}
interface C extends A {
    public void print_Cat();
}
interface D extends A {
    public void print_Dog();
}
public class hybrid implements B, C, D {
    public void print_Apple() {
        System.out.println("Apple");
    }
    public void print_Ball() {
        System.out.println("Ball");
    }
    public void print_Cat() {
        System.out.println("Cat");
    }
    public void print_Dog() {
        System.out.println("Dog");
    }
    public static void main(String[] args) {
        hybrid m = new hybrid();
        m.print_Apple();
        m.print_Ball();
        m.print_Cat();
        m.print_Dog();
    }
}
```

Output:
```
Apple
Ball
Cat
Dogs
```

### **Using ``extends`` keyword**

``extends`` is the keyword used to inherit the properties of a class. Following is the syntax of extends keyword :

Syntax:

```Java
class <derived-class> extends <base-class>  {  
   //methods and fields  
}  
```

### **Subclass and Superclass**

In Java, it is possible to inherit attributes and methods from one class to another. We group the "inheritance concept" into two categories:

* ``Subclass (child)`` - the class that inherits from another class.
* ``Superclass (parent)`` - the class being inherited from.

To inherit from a class, use the ``extends`` keyword.

### **``super`` keyword usage**

The ``super`` keyword refers to superclass (parent) objects. It is used to call superclass methods, and to access the superclass constructor.The most common use of the ``super`` keyword is to eliminate the confusion between superclasses and subclasses that have methods with the same name.

* ``super`` can be used to refer immediate parent class instance variable.
* ``super`` can be used to invoke immediate parent class method.
* ``super()`` can be used to invoke immediate parent class constructor.

**Differentiating the Members:**

If a class is inheriting the properties of another class. And if the members of the superclass have the names same as the sub class, to differentiate these variables we use super keyword as shown below.

```Java
super.variable
super.method();
```

### **Overriding Method**
If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.

In other words, If a subclass provides the specific implementation of the method that has been declared by one of its parent class, it is known as method overriding.

**Usage of Java Method Overriding**

* Method overriding is used to provide the specific implementation of a method which is already provided by its superclass.
* Method overriding is used for runtime polymorphism

**Rules for Java Method Overriding**

* The method must have the same name as in the parent class
* The method must have the same parameter as in the parent class.
* There must be an IS-A relationship (inheritance).

Example:

```Java
class A {
    void Print() {
        System.out.println("This is Class A");
    }
}
class B extends A {
    @Override
    void Print() {
        System.out.println("This is Class B");
    }
}
class C extends B {
    @Override
    void Print() {
        System.out.println("This is Class C");
    }
}
public class Program {
    public static void main(String[] args) {
        A a = new A();
        a.Print();
        B b = new B();
        b.Print();
        C c = new C();
        c.Print();
    }
}
```

Output:
```
This is Class A
This is Class B
This is Class C
```

### **Dynamic Method Dispatch**
**Dynamic Method Dispatch** is a mechanism by which a call to an overridden method is resolved at runtime. This is how java implements runtime polymorphism. When an overridden method is called by a reference, java determines which version of that method to execute based on the type of object it refer to. In simple words the type of object which it referred determines which version of overridden method will be called.

```Java
class A {
    void action() {
        System.out.println("Inside A's action method");
    }
}
class B extends A {
    // overriding action()
    void action() {
        System.out.println("Inside B's action method");
    }
}
class C extends A {
    // overriding action()
    void action() {
        System.out.println("Inside C's action method");
    }
}
public class Program {
    public static void main(String args[]) {
        // object of type A
        A a = new A();
        // object of type B
        B b = new B();
        // object of type C
        C c = new C();
        // obtain a reference of type A
        A ref;
        // ref refers to an A object
        ref = a;
        // calling A's version of action()
        ref.action();
        // now ref refers to a B object
        ref = b;
        // calling B's version of action()
        ref.action();
        // now ref refers to a C object
        ref = c;
        // calling C's version of action()
        ref.action();
    }
}
```

Output:
```
Inside A's action method
Inside B's action method
Inside C's action method
```

## The Object Class
-------------------------
Object is the mother of all classes , in other words  every other class in java is the subclass of Object class. Object class is in the default package i.e ``java.lang`` package .

The Object class defines the basic state and behavior that all objects must have, such as the ability to compare oneself to another object, to convert to a string, to wait on a condition variable, to notify other objects that a condition variable has changed, and to return the object's class.There are 11 methods in Object class .

It has following methods in its class:

* ``equals(Object obj)``: Checks whether the obj object is equal to the object on which the equals method is called .

* ``hashCode()``: ``hashCode()`` is used for the HashTable.It returns the hash value of the object.

* ``getClass()``: It returns the runtime class object .

* ``clone()``: It creates and  returns the copy of the object .    

* ``notify()``: It will wake up the thread waiting for the objects monitor.

* ``notifyAll()``: It will wakes up all the thread that are waiting for the objects monitor .

* ``toString()``: It will return the string representation of the object .

* ``wait()``: This method causes the current thread to place itself in the wait set for this object and then to relinquish any and all synchronization claims on this object

## Abstract and Final Class in Java
------------------------------------

### Abstract Class
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its method implemented. It cannot be instantiated.

**Syntax of declaring an abstract class:**

To declare an abstract class we use the keyword ``abstract``. The syntax is given below:

```Java
abstract class ClassName{
    //class body
}
```

**Example:**

```Java
abstract class A {}  
```

### Final Class
A class which is declared with the ``Final`` keyword is known as the final class. The ``final`` keyword is used to finalize the implementations of the classes, the methods and the variables used in this class. The main purpose of using a final class is to prevent the class from being inherited (i.e.) if a class is marked as final, then no other class can inherit any properties or methods from the final class. If the final class is extended, Java gives a compile-time error.

The following is an example of how a final class is declared. However, a compile-time error is given because this final class is being inherited.

```Java
// Java program to demonstrate the
// Final class
final class Super {
    private int data = 100;
}
public class Sub extends Super {
    public static void main(String args[]) {}
}
```

The following table demonstrates the difference between an ``abstract`` class and a ``final`` class:

|                         Abstract Class                             |                                 Final Class                                    |
|--------------------------------------------------------------------|--------------------------------------------------------------------------------|
|Uses the ``abstrac`` key word.                                      |Uses the ``final`` key word.                                                    |
|This helps to achieve abstraction.                                  |This helps to restrict other classes from accessing its properties and methods. |
|For later use, all the abstract methods should be overridden        |Overriding concept does not arise as final class cannot be inherited            |
|A few methods can be implemented and a few cannot                   |All methods should have implementation                                          |
|Cannot create immutable objects (infact, no objects can be created) |Immutable objects can be created (eg. String class)                             |
|Abstract class methods functionality can be altered in subclass     |Final class methods should be used as it is by other classes                    |
|Can be inherited                                                    |Cannot be inherited                                                             |
|Cannot be instantiated                                              |Can be instantiated                                                             |

## Packages in Java
-----------------------
**Packages** are used in Java in order to prevent naming conflicts, to control access, to make searching/locating and usage of classes, interfaces, enumerations and annotations easier, etc.
A Package can be defined as a grouping of related types (classes, interfaces, enumerations and annotations ) providing access protection and namespace management.

### **Defining a packages:**
We use the ``package`` keyword to create or define a package in java programming language.

Syntax:
```Java
package packagename;
```

Let's consider the following code to create a user-defined package ``examplepackage``.

```Java
package examplepackage;
public class DefiningPackage {
	public static void main(String[] args) {
		System.out.println("This class belongs to examplepackage.");
	}
}
```

Now, save the above code in a file ``DefiningPackage.java``, and compile it using the following command.

```
javac -d . DefiningPackage.java
```

The above command creates a directory with the package name ``examplepackage``, and the ``DefiningPackage.class`` is saved into it.

Run the program use the following command.

```
java examplepackage.DefiningPackage
```

### **Importing a Package:**

In java, the ``import`` keyword used to import built-in and user-defined packages. When a package has imported, we can refer to all the classes of that package using their name directly.

The import statement must be after the package statement, and before any other statement.

Using an ``import`` statement, we may import a specific class or all the classes from a package.

**Importing specific class**

Using an importing statement, we can import a specific class. The following syntax is employed to import a specific class.

Syntax:

```Java
import packageName.ClassName;
```

**Importing all the classes**

Using an importing statement, we can import all the classes of a package. To import all the classes of the package, we use * symbol. The following syntax is employed to import all the classes of a package.

Syntax:

```Java
import packageName.*;
```

**Consider the following import statement**

```Java
import java.util.*;
```

The above import statement ``util`` is a sub-package of ``java`` package. It imports all the classes of ``util`` package only, but not classes of ``java`` package.

## Interface
---------------------
Like a class, an interface can have methods and variables, but the methods declared in an interface are by default abstract (only method signature, no body).  

* Interfaces specify what a class must do and not how. It is the blueprint of the class.
* An Interface is about capabilities like a Player may be an interface and any class implementing Player must be able to (or must implement) move(). So it specifies a set of methods that the class has to implement.
* If a class implements an interface and does not provide method bodies for all functions specified in the interface, then the class must be declared abstract.
* A Java library example is, Comparator Interface. If a class implements this interface, then it can be used to sort a collection.

### **Defining a Interface:**
An interface is declared by using the ``interface`` keyword. It provides total abstraction; means all the methods in an interface are declared with the empty body, and all the fields are public, static and final by default. A class that implements an interface must implement all the methods declared in the interface.

**Syntax:**

```Java
interface <interface_name>{            
    // declare constant fields  
    // declare methods that abstract   
    // by default.  
}  
```

**Example:**

```Java
interface Player{
    final int id = 10;
    int move();
}
```

### **Implementing and Applying Interfaces:**
To implement an interface we use keyword ``implements``.

**Syntax:**

```Java
class <class_name> implements <interface_name>
```

**Example:**

```Java
class main implements Player
```

**Example Program:**
Let’s consider the example of vehicles like bicycle, car, bike………, they have common functionalities. So we make an interface and put all these common functionalities. And lets Bicycle, Bike, car ….etc implement all these functionalities in their own class in their own way.

```Java
import java.io.*;
interface Vehicle {
    // all are the abstract methods.
    void changeGear(int a);
    void speedUp(int a);
    void applyBrakes(int a);
}
class Bicycle implements Vehicle {
    int speed;
    int gear;
    // to change gear
    @Override
    public void changeGear(int newGear) {
        gear = newGear;
    }
    // to increase speed
    @Override
    public void speedUp(int increment) {
        speed = speed + increment;
    }
    // to decrease speed
    @Override
    public void applyBrakes(int decrement) {
        speed = speed - decrement;
    }
    public void printStates() {
        System.out.println("speed: " + speed + " gear: " + gear);
    }
}
class Bike implements Vehicle {
    int speed;
    int gear;
    // to change gear
    @Override
    public void changeGear(int newGear) {
        gear = newGear;
    }
    // to increase speed
    @Override
    public void speedUp(int increment) {
        speed = speed + increment;
    }
    // to decrease speed
    @Override
    public void applyBrakes(int decrement) {
        speed = speed - decrement;
    }
    public void printStates() {
        System.out.println("speed: " + speed + " gear: " + gear);
    }
}
public class Program {
    public static void main(String[] args) {
        // creating an inatance of Bicycle
        // doing some operations
        Bicycle bicycle = new Bicycle();
        bicycle.changeGear(2);
        bicycle.speedUp(3);
        bicycle.applyBrakes(1);
        System.out.println("Bicycle present state :");
        bicycle.printStates();
        // creating instance of the bike.
        Bike bike = new Bike();
        bike.changeGear(1);
        bike.speedUp(4);
        bike.applyBrakes(3);
        System.out.println("Bike present state :");
        bike.printStates();
    }
}
```
**Output:**
```
Bicycle present state :
speed: 2 gear: 2
Bike present state :
speed: 1 gear: 1
```