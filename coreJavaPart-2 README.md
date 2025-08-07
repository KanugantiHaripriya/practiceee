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
- We can access  non static variables inside non static metod directly.
  


















