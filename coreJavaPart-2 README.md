# Core Java Notes Part-2
## Memory Areas in Java
- **Heap:**
  - Area of memory where Java objects (instances) and instance variables are stored.
- **Stack:**
  - Memory area that stores local variables and method call information. Local variables exist only as long as the method/block is executing.
- **Method Area (Static/Class Area):**
  - Stores class-level data such as static variables, static methods, and bytecodes of methods.
- **PC Register:**
  - A per-thread register that contains the address of the current instruction being executed.
- **Native Method Stack:**
  - Contains native (platform-dependent) method calls.
- **Execution Stack / Call Stack:**
  - Stores frames for method calls and local variables.


## Program Execution Flow
- JVM wont directly coomunicate with byte code but after the class loading it starts communicate with the byte code
- **Class Loading** : It is bringing dot class file into jvm memory
  ```
               +-----------------+
             |    add .java    |
             +-----------------+
                      |
                      v
                +-----------+
                |   Java    |
                +-----------+
                      |
                      v
                +-----------+
                | Bytecode  |
                +-----------+
                      |
                      v
                 class loading
                      |
   +------------------+------------------+
   |       JVM architecture flow         |
   +-------------------------------------+

         +---------+  +---------+  +-----------------+
         | loading |  | linking |  | initialization  |
         +---------+  +---------+  +-----------------+
                      |               |
                      v               v
     ---------------------------------------------------------
     | Method area | Heap memory | Stack memory | PC register |
     | Native stack memory                                     |
     ---------------------------------------------------------
                      |
                  Execution Engine
    -------------------------------------------------
    |  Interpreter | JIT compiler | Garbage collector |
    -------------------------------------------------
                      |
                     JNI
                      |
          Native stack library
  ```
## Variables
- We have two different types of variables
1. Non-static variables
   - Instance Variables
   - Local Variables
2. Static Varaibles

###  Instance Variables
- Declared inside the class but outside any method, constructor, or block.
- Instance variables also called as ` Object variable`
- Instance memory get memory as part of object inside Heap
- Instance variable gets created once object is created
- This variables gets destroyed once object is destroyed
- Instance variables have default values according to the datatype
- You can access this variables throughout the class
- The scope is throughout the class, access outside the class
- To access instance variables inside class method make use of object reference
- We can access  non static variables inside non static method directly.
``` bash
class Student{
	int a; // Instance Variables
	String name;  //Instance Variables
	Student(){
		//constructor
	}
	void a() {
		 //method
	}
	{
		//Block
	}
}
```

### Local variables
- The variables which declare inside the method, constructor and block is called as local variable.
- Local variables get the memory inside stack call as a temporary memory.
- Once method starts it execution then local variables getting memory space.
- Once method complete its execution, then local variables get destroyed.
- Local variables don’t have default values.
- Scope of the local variable is with a scope of local scope i.e. within a method or within a constructor or in a block.
- **Note:** In same scope unable to have same variable name.but outside the scope u can have same variable name.
```
class Student{
	Student(){
		int a=10; // Local Variables
	}
	void a() {
		 double b=30; // Local Variables
	}
	{
		float f=3.111; // Local Variables
	}
}
```
---
 ## this keyword 
 - It’s used to call data and behaviour of current object.
 - 'this' keyword we can;t used in static methods even inside the main method

### Varaible Clasing/ Variable Shadowing
- Whenever the local variable and instance variable having same name, JVM always giving the preference to local variable over instance variable.
- To overcome this problem we can use this keyword.

---
## Static variables
- The variable which declared with static keyword is called static variable.
- The static variables belonging to the class not for the object.
  ```
   class name {
  		static int a = 10;
	}
  ```
- The static variables loaded into the class area of memory and only once at the time of class loading.
- **Class loading:** When class file is loaded into JVM memory call it as class loading.
- **Note:** Static variables can access throughout the class without any reference variable.
- Static variables can directly access inside the main method without any object reference.
- Once the static variables are updated, it is impossible to get the previous value.
- The static variables can access inside non-static method without any reference variable (object).
- The static variables can be accessed outside the class with the help of class name with dot operator.
- **Note:** The local variable cannot be static
---
## Inheritance
- Accessing the properties from one class to another class i.e. Super class to subclass using `extends` keyword.
- Inheritance is also called as `IS-A relation.`

### Super/parent/Base class 
- The class which having common properties and behaviours we call it as Super/parent/Base class.

### Sub/child/Derived class 
- The class which inherits the properties from parent class.

### Advantages of Inheritance 
1. Reduce Redundancy
2. Code Reusability

```
class Vegetable{
	// Base Class
}
class Carrot extends Vegetable{
	// Derived Class
}
```
- By using Inheritance we can inherit only variables and methods but not constructors and blocks.
- By using super class reference we can access only inherited variables and methods but not subclasses specific behaviours, properties.
- **Note**
  - Static members cannot be inherited
  - private members cannot be inherited
### Types of Inheritance
1. Single level Inheritance.
2. Multi-level Inheritance.
3. Hierarchical Inheritance.
4. Multiple Inheritance.
5. Hybrid Inheritance.

**1.  Single Level Inheritance**
   - A subclass inherits directly from a single superclass.
```
class Person {
   // Parent class code here
}

class Student extends Person {
   // Child class inherits properties from Person
}
```
```
Person
  ↓
Student
```
**2. Multi-level Inheritance**
   - Inheritance happens in multiple levels; a class inherits from a subclass which itself inherits from another class.
```
Food
 ↓
Dosa
 ↓
Masala Dosa
```
```
Food
 ↓
Dosa
 ↓
Masala Dosa
```
**3.  Hierarchical Inheritance**
   -  A single parent class has multiple child classes, inheriting its properties.
```
Vehicle
 ↙   ↓   ↘
Bike  Car  4 wheeler vehicle
 |     |       |
E-car  E-car   Few
```
### Object Class
- The Object class is the root (super class) for all classes in Java.
- It is defined in the java.lang package.
- Every class either directly or indirectly extends the Object class.
- Common built-in Java classes like Scanner, String, Emp, System, and Array all derive from Object.
```
          Object  (Parent of all object classes)
              |
   |-----------|-----------|-----------|-----------|-----------|
 Scanner     String       Emp        System       Array
```
-  Which is the super most class to Java? Object class
-  How many methods present to Object class? 11 methods
-  **Note:**
   - Where each and every class extends to object class when the class is not extended to another class.
   - If the class is extends to any other class indirectly, the class extends to object class.

**4.  Multiple Inheritance**
- A single sub class having multiple super classes
```
   Parent1      Parent2
       \          /
        \        /
          Child
```
```
class Parent1 {
    // Parent1 class methods and fields
}

class Parent2 {
    // Parent2 class methods and fields
}

// This syntax is not allowed in Java
class Child extends Parent1, Parent2 {
    // Child class inherits from both Parent1 and Parent2
}
```
- We can't achieve multiple inheritance by using class because of two reasons i.e;
1. Ambiguity while method calling
2. Ambiguity while construction chaining

**1. Ambiguity while method calling**
   - If two parent classes have the same method name and a child inherits both, the compiler wouldn’t know which method to call.
   ```
   class A {
    void show() {
        System.out.println("From Class A");
    }
	}
	
	class B {
	    void show() {
	        System.out.println("From Class B");
	    }
	}
	
	// ❌ Not allowed in Java
	class C extends A, B { 
	    public static void main(String[] args) {
	        C obj = new C();
	        obj.show(); // Ambiguity — which show()?
	    }
	}
 ```
**Reason:** The compiler can’t decide whether to call `A.show()` or `B.show()`.

**2. Ambiguity while constructor chaining**
- When a child class inherits multiple classes, it must call the parent constructors.
If both parents have constructors, the compiler won’t know which one to call first.
 ```
class A {
    A() {
        System.out.println("A's Constructor");
    }
}

class B {
    B() {
        System.out.println("B's Constructor");
    }
}

// ❌ Not allowed
class C extends A, B {
    C() {
        System.out.println("C's Constructor");
    }
}
```
**Reason:** The compiler can’t decide whether to call A’s constructor first or B’s constructor first.

### Diamond Problem
- If two superclasses have the same method name and a child class tries to inherit from both, the compiler gets confused about which method to call.
- This confusion is the main reason multiple inheritance using classes is not possible in Java.
- Even if the method names are different, both superclasses still inherit methods from the Object class.
- Some of these inherited methods (like toString(), equals(), etc.) may be present or overridden in the child class.
- Java has default routing rules for method calls, which can again create ambiguity about which superclass method to use.
- This ambiguity is called the Diamond Problem

**5. Hybrid Inheritance**
- It is a combination of multiple and hierarchical inheritance.
- Multiple and hybrid inheritance can’t achieve by using the class but we can achieve by interfaces.
---   
