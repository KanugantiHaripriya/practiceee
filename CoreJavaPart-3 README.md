# CoreJava Part-3 Notes
## Method Overloaded (or) Overloading
In a single class more than 1 method has same name but change in signature we called as method Overloading.

### Change in Signature
1. Number of Parameters.
2. Sequence of Parameters.
3. Datatype of Parameter.

### False polymorphism :-
It is illusion that a single method doing all type operation we call false polymorphism.

In above Example a single add method is doing all type of addition it is a illusion, but for different operation there is a separate add method.

**Advantages of method overloading**
- we can achieve compile time polymorphism.
---
## Method Overriding
- It is a process of providing subclass specific implementation to the inheritance methods; we called that as method overriding.
- @Override annotation which is used to indicate the overriding & to specify the method is overridden

**Rules to define on Method Overriding**
1. The return type of the method should be same.
2. Name of the method should be same.
3. Signature of the method should be same.
4. Implementation must be changed.

**NOTE:**
- Without Inheritance we can't provide Inheritance
- Final methods cant be inherited cant be overidden.
---
## Instance Initialization Block
- Instance initialization block which is used to initialize instance variables.
- Once object is created, the instance blocks are getting executed.
- It internally forms with constructor – instance initialization block executes before object creation.
- If we have n number of instance blocks, the order when we created the instance block – in the same order the block will get executed.

**Drawback**
- If we are creating for n number of object – if we are instance block to initialize instance variables all the object are come with same values.
---
## Constructor
- It is a special member of a class
- constructor name & class name should be same.
```
class Student(){
  Student(){
      // Constructor
  }
}
```
- It is used to initialize instance variables

### Types of Constructor
1. Default Constructor
2. Custom Constructor / Parameterized Constructor
     1. Zero-Parameter Constructor
     2. Parameterized Constructor

**1. Default Constructor**
   - If we not defined any constructor, the JVM also generates default constructor.
   - This is a zero parameter constructor.
   - The main purpose for default constructor to initialize instance variables with default values.

**2. Custom Constructor / Parameterized Constructor/ User-defined constructor**
  

