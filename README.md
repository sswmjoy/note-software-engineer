# note-software-engineer 
>This page is in order to record my knowledge about software engineering which contains interviewing, and reading notes.
I have many years as a java software engineer in China, but I realize that I also have some gaps to explain my knowledge in English. Otherwise, I have been preparing for my interview in English, so there are some tips about how to make a resume in English, etc.   
Finally, I will be glad if this information can bring you some useful help.
## Table of Contents 
---
- [Topic of Study](#-topic-of-study)
    - [1.Language](#1lauguage)
        - [Java](#java)
        - [JS](#js)
        - [Python](#python)

    - [2.Data Struct](#2data-struct)
    - [3.Coding Website](#3coding-website)
    - [4.Note of Book](#4note-of-book)
    - [5.DevOps](#5devops)
    - [6.More Knowledge](#6more-knowledge)

- [Getting the Job](#-getting-the-job)
    - [1.How to Make a Resume](#1how-to-make-a-resume)
    - [2.Find a Job](#2find-a-job)
### Topic of Study
---
#### 1.Lauguage
##### Java
- Core Jave Interview Questions and Answers(Freshers&Experienced Developers):
    **Q1:What are the types of Exceptions? Explain the hierarchy of Java Exception classes?**
    Ans:Exception is an error event that can happen during the execution of a program and disrupts its normal flow.

    There are THREE TPYES of Java Exception,Checked Exception,Unchecked Exception and Error.
    Types of Java Exceptions

    1. For Checked Exception: The classes which directly inherit Throwable class except RuntimeException and Error are known as checked exceptions e.g. IOException, SQLException etc. Checked exceptions are checked at compile-time.
    2. For Unchecked Exception: The classes which inherit RuntimeException are known as unchecked exceptions e.g. ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException etc. Unchecked exceptions are not checked at compile-time, but they are checked at runtime.
    3. For Error: Error is irrecoverable e.g. OutOfMemoryError, VirtualMachineError, AssertionError etc.

    Hierarchy of Java Exception classes
    The java.lang.Throwable class is the root class of Java Exception hierarchy which is inherited by two subclasses: Exception and Error.
    **Q2:What is the difference between aggregation and composition?**
    Ans:We call aggregation those relationships whose objects have an independent lifecycle, but there is ownership, and child objects cannot belong to another parent object.
    We use the term composition to refer to relationships whose objects don’t have an independent lifecycle, and if the parent object is deleted, all child objects will also be deleted.
    So, for aggregation is Has-A relationShip, but composition is Part-Of relationShip. For example:Car has a Driver is aggregation, and engine is a part of car, so they are composition.


    | Aggregation |	Composition |
    |--|--|
    |Aggregation is a weak Association|Composition is a strong Association.|
    |Class can exist independently without owner.|Class can not meaningfully exist without owner.|
    |Have their own Life Time.|Life Time depends on the Owner.|
    |A uses B.|A owns B.|
    |Child is not owned by 1 owner.|Child can have only 1 owner.|
    |Has-A relationship. A has B.|Part-Of relationship. B is part of A.|
    |Denoted by a empty diamond in UML.|Denoted by a filled diamond in UML.|
    |We do not use "final" keyword for Aggregation.|"final" keyword is used to represent Composition.|
    |Examples: <br>-Car has a Driver.-A Human uses Clothes.<br>-A Company is an aggregation of People.<br>-A Text Editor uses a File.<br>-Mobile has a SIM Card.|Examples:<br>- Engine is a part of Car.<br>- A Human owns the Heart.<br>- A Company is a composition of Accounts.<br>- A Text Editor owns a Buffer.<br>- IMEI Number is a part of a Mobile.|
    
    **Q3:What is difference between Heap and Stack Memory in java?**
    ```Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always created in the Heap space.```
    Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.
    ```Stack in java is a section of memory which contains methods, local variables and reference variables. Local variables are created in the stack.```
    Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.
    As soon as method ends, the block becomes unused and become available for next method. ```Stack memory size is very less compared to Heap memory.```

    |Parameter|Stack Memory|Heap Space|
    |--|--|--|
    |Application|Stack is used in parts, one at a time during execution of a thread|The entire application uses Heap space during runtime|
    |Size|Stack has size limits depending upon OS and is usually smaller then Heap|There is no size limit on Heap|
    |Storage|Stores only primitive variables and references to objects that are created in Heap Space|All the newly created objects are stored here|
    |Order|It is accessed using Last-in First-out (LIFO) memory allocation system|This memory is accessed via complex memory management techniques that include Young Generation, Old or Tenured Generation, and Permanent Generation.|
    |Life|Stack memory only exists as long as the current method is running|Heap space exists as long as the application runs|
    |Efficiency|Comparatively much faster to allocate when compared to heap|Slower to allocate when compared to stack|
    |Allocation/Deallocation|This Memory is automatically allocated and deallocated when a method is called and returned respectively|Heap space is allocated when new objects are created and deallocated by Gargabe Collector when they are no longer referenced|



    **Q4:What is JIT compiler in Java?**
    The Just-In-Time (JIT) compiler is a component of the runtime environment that improves the performance of Java applications by compiling bytecodes to native machine code at run time.

    **Q5:Java Interview Questions- Explain the difference between JDK, JRE, and JVM**
    ```JDK stands for Java Development Kit and is the tool used to compile, package and document Java programs.```
    ```JRE stands for Java Runtime Environment``` and is a runtime environment that is a prerequisite to run java byte-code.
    ```JVM stands for Java Virtual Machine and is a specification that facilitates a run-time environment``` in which Java’s bytecode can be implemented.
    **Q6:Would it be correct to say that Java is not 100% Object-oriented?**
    Yes, it would be correct to say that Java is not 100% Object-oriented because it utilizes eight kinds of primitive data types and they are - Boolean, byte, char, int, float, double, long, short. These data types are not objects.
    **Q7:What is a constructor in Java**
    A constructor is a block of code that is used in a Java environment to initialize an object. It carries the same name that you had given to the class. A Java constructor is automatically called when an object is created.

    **Q8:Differentiate between a constructor and a method? Can we mark constructors final?**
    A constructor constructs the value, by providing data for the object. It is a special type of method that is used to initialize the object.A method is an ordinary member function of a class. A method can be invoked using the dot operator and has its own name, and a return type
    no, we can't

    **Q9:What is the final class**
    A final class is a constant value of a final variable,Extending A final class is not possible

    **Q10:What is a wrapper class**
    The classes that “wrap” the primitive data type into an object of that class are called Java wrapper classes.

    **Q11:What is an abstract class**
    Abstract serves as a template. In order to use an abstract class, it must be extended or subclassed. An abstract class may not be instantiated. Any class with an abstract method is abstract itself, hence is declared as such.

    **Q12:Describe synchronization with respect to multithreading.**
    Synchronization is the method to control the access of multiple threads to shared resources, with respect to multithreading. One thread can modify a shared variable when not in synchronization even when another thread is in the process of using or updating the same shared variable. This can lead to significant errors.
    **Q13:What is the purpose of garbage collection in Java, and when is it used**
    The main purpose of garbage collection is to analyze a program, identify and discard the objects that are no longer needed. It is helpful as the resources can be reclaimed and reused. A Java object is subjected to garbage collection when the object is not reachable to the program in which it is used.
    **Q14:What are the different ways of implementing thread? Which one is more advantageous**
    The thread can be implemented by using runnable interface Inheriting from the Thread class. The use of the Runnable interface is more advantageous because when going for multiple inheritances, the only interface can help.

    **Q15:What if the main() method is declared as private? What happens when the static modifier is removed from the signature of the main() method?**
    When the main() method is declared as private, the program compiles but during runtime it shows “main() method not public.” Message. When the static modifier is removed from the signature of the main() method, the Program compiles but at runtime throws an error “NoSuchMethodError”.
    **Q16:What is a Java servlet**
    A Servlet in Java refers to the server-side technologies which are used to extend the competence of web servers by giving it support for a dynamic response as well as data persistence.
    **Q17:the Life-cycle of a Java Servlet**

##### JS
##### Python
#### 2.Data Struct
#### 3.Coding Website
#### 4.Note of Book
#### 5.DevOps
#### 6.More Knowledge
### Getting the Job
---
#### 1.How to Make a Resume
#### 2.Find a Job


