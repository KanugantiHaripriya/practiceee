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
- **Note:**In same scope unable to have same variable name.but outside the scope u can have same variable name.
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
---
  


















