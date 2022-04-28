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
        - [Clean Code](#clean-code)
    - [5.DevOps](#5devops)
    - [6.More Knowledge](#6more-knowledge)

- [Getting the Job](#-getting-the-job)
    - [1.How to Make a Resume](#1how-to-make-a-resume)
    - [2.Find a Job](#2find-a-job)
    - [3.How to Write a Thank You Letter](#3how-to-write-a-thank-you-letter)
### Topic of Study
---
#### 1.Lauguage
##### Java
- Core Jave Interview Questions and Answers(Freshers&Experienced Developers):<br>**Q1:What are the types of Exceptions? Explain the hierarchy of Java Exception classes?**
    <br>Ans:Exception is an error event that can happen during the execution of a program and disrupts its normal flow.

    There are THREE TPYES of Java Exception,Checked Exception,Unchecked Exception and Error.
    Types of Java Exceptions

    1. For Checked Exception: The classes which directly inherit Throwable class except RuntimeException and Error are known as checked exceptions e.g. IOException, SQLException etc. Checked exceptions are checked at compile-time.
    2. For Unchecked Exception: The classes which inherit RuntimeException are known as unchecked exceptions e.g. ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException etc. Unchecked exceptions are not checked at compile-time, but they are checked at runtime.
    3. For Error: Error is irrecoverable e.g. OutOfMemoryError, VirtualMachineError, AssertionError etc.

    Hierarchy of Java Exception classes
    The java.lang.Throwable class is the root class of Java Exception hierarchy which is inherited by two subclasses: Exception and Error.

    <br>**Q2:What is the difference between aggregation and composition?**
    <br>Ans:We call aggregation those relationships whose objects have an independent lifecycle, but there is ownership, and child objects cannot belong to another parent object.
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
    <br>**Q3:What is difference between Heap and Stack Memory in java?**
    <br>```Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. Whenever we create any object, it’s always created in the Heap space.```
    Garbage Collection runs on the heap memory to free the memory used by objects that doesn’t have any reference. Any object created in the heap space has global access and can be referenced from anywhere of the application.
    <br>```Stack in java is a section of memory which contains methods, local variables and reference variables. Local variables are created in the stack.```
    <br>Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.
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



    <br>**Q4:What is JIT compiler in Java?**
    <br>The Just-In-Time (JIT) compiler is a component of the runtime environment that improves the performance of Java applications by compiling bytecodes to native machine code at run time.

    <br>**Q5:Java Interview Questions- Explain the difference between JDK, JRE, and JVM**
    <br>```JDK stands for Java Development Kit and is the tool used to compile, package and document Java programs.```
    ```JRE stands for Java Runtime Environment``` and is a runtime environment that is a prerequisite to run java byte-code.
    ```JVM stands for Java Virtual Machine and is a specification that facilitates a run-time environment``` in which Java’s bytecode can be implemented.
    <br>**Q6:Would it be correct to say that Java is not 100% Object-oriented?**
    <br>Yes, it would be correct to say that Java is not 100% Object-oriented because it utilizes eight kinds of primitive data types and they are - Boolean, byte, char, int, float, double, long, short. These data types are not objects.
    <br>**Q7:What is a constructor in Java**
    A constructor is a block of code that is used in a Java environment to initialize an object. It carries the same name that you had given to the class. A Java constructor is automatically called when an object is created.

    <br>**Q8:Differentiate between a constructor and a method? Can we mark constructors final?**
    <br>A constructor constructs the value, by providing data for the object. It is a special type of method that is used to initialize the object.A method is an ordinary member function of a class. A method can be invoked using the dot operator and has its own name, and a return type
    no, we can't

    <br>**Q9:What is the final class**
    <br>A final class is a constant value of a final variable,Extending A final class is not possible

    <br>**Q10:What is a wrapper class**
    <br>The classes that “wrap” the primitive data type into an object of that class are called Java wrapper classes.

    <br>**Q11:What is an abstract class**
    <br>Abstract serves as a template. In order to use an abstract class, it must be extended or subclassed. An abstract class may not be instantiated. Any class with an abstract method is abstract itself, hence is declared as such.

    <br>**Q12:Describe synchronization with respect to multithreading.**
    <br>Synchronization is the method to control the access of multiple threads to shared resources, with respect to multithreading. One thread can modify a shared variable when not in synchronization even when another thread is in the process of using or updating the same shared variable. This can lead to significant errors.

    <br>**Q13:What is the purpose of garbage collection in Java, and when is it used**
    <br>The main purpose of garbage collection is to analyze a program, identify and discard the objects that are no longer needed. It is helpful as the resources can be reclaimed and reused. A Java object is subjected to garbage collection when the object is not reachable to the program in which it is used.
    <br>**Q14:What are the different ways of implementing thread? Which one is more advantageous**
    <br>The thread can be implemented by using runnable interface Inheriting from the Thread class. The use of the Runnable interface is more advantageous because when going for multiple inheritances, the only interface can help.

    <br>**Q15:What if the main() method is declared as private? What happens when the static modifier is removed from the signature of the main() method?**
    <br>When the main() method is declared as private, the program compiles but during runtime it shows “main() method not public.” Message. When the static modifier is removed from the signature of the main() method, the Program compiles but at runtime throws an error “NoSuchMethodError”.
    <br>**Q16:What is a Java servlet**
    <br>A Servlet in Java refers to the server-side technologies which are used to extend the competence of web servers by giving it support for a dynamic response as well as data persistence.
    <br>**Q17:the Life-cycle of a Java Servlet**
    <br>Servlet is loaded
    Servlet is instantiated
    Servlet is destroyed
    Servlet is initialized
    Service the request
    <br>**Q18:What is a Java applet**
    <br>The applet is a Java program that is designed for transmitting the Java code over the internet. Ttion works automatically by Java-enabled Web Browser. The applet can respond to the user input immediately as it is dynamically programmed.
    <br>**Q19:What is numeric promotion**
    <br>Numeric promotions of a numeric operator are used for the conversion of the operands into a common type. In order to perform calculations easily, numeric promotion, conversion is performed. It is the conversion of a smaller numeric type to a larger numeric type so that integer and floating-point operations can be performed over it. Here byte, char, and short values are converted to int values. The int values are converted to long values, and the long and float values are converted to double values.
    <br>**Q20:What is false sharing in the context of multi-threading**
    <br>```On multi-core systems, false sharing is one of the well-known performance issues. Here each process has its local cache. When threads on a different processor, modify variables false sharing occurs, that resides on the same cache line``` as shown in the following images
    ```As the thread may access different global variables completely, false sharing can be hard to detect.```
    <br>**Q21:What are the methods used to implement the key Object in HashMap**
    <br>Equals and hashcode methods are to be implemented In order to use any object as Key in HashMap
    <br>**Q22:What is an immutable object**
    <br>Java classes whose objects cannot be modified once they are created are known as Immutable classes. Any modification of Immutable object results formation of the new object.
    <br>**Q23:Differentiate between StringBuffer and StringBuilder in Java**
    <br>The only difference between StringBuffer and StringBuilder is that StringBuffer methods are synchronized while StringBuilder is not synchronized.
    <br>**Q24:What is the difference between a factory and abstract factory patterns**
    <br>Abstract Factory provides one more level of abstraction. Consider different factories each extended from an Abstract Factory and responsible for the creation of different hierarchies of objects based on the type of factory. E.g. Abstract Factory extended by Automobile Factory, User Factory, Role Factory, etc. Each individual factory would be responsible for the creation of objects in that genre.
    <br>**Q25:Differentiate JAR and WAR files**
    <br>We are going to share the Difference between the JAR & WAR File:
    |JAR FILES|WAR FILES|
    |--|--|
    |Full form of JAR files is Java Archive Files.|Full form of WAR files is Web Archive Files.|
    |Aggregating many files into one is allowed in JAR files|XML, Java classes, and JavaServer Pages are stored in WAR|
    |The JAR is usually used to hold Java classes in a library.|Mainly used for Web Application purposes.|

    <br>**Q26:What is a package in Java?**
    <br>The collection of related classes and interfaces grouped together is Package in Java. It enables developers to easily modularize codes. Packages help in providing easier access control on the code.

    <br>**Q27:What is the final keyword in Java?**
    <br>Final is a special keyword in Java being used as a non-access modifier. It is used in various contexts like Final variables, Final Methods, and Final Class. Final class refers to a class being declared as final in Java. 

    <br>**Q28:What are the various types of inheritance in Java**
    <br>Java has four types of inheritance namely:
    - Single inheritance - Herein one class inherits the properties of another class.
    - Multilevel inheritance - A class having more than one parent class but at different levels is termed as Multilevel inheritance.
    - Hierarchical inheritance - When a class has more than one child class it is termed as hierarchical inheritance.
    - Hybrid inheritance - It’s a combination of two or more types of inheritance.

    <br>**Q29:What is the most important feature of Java8?**
    <br>The most important feature of Java 8 is its functional interface and static methods. When adding a functional interface to the object-oriented interface, programming becomes less complicated and more efficient.

    <br>**Q30:Can you explain serialization and deserialization?**
    <br>Both serialization and deserialization are crucial to stream handling in Java. Through serialization, you convert an object into a byte stream, and through deserialization, you simply undo the process.

    <br>Q31:What is a ternary operator
    <br>A ternary operator is a conditional operator in Java used to decide what values to be assigned to a variable.
##### JS
##### Python
#### 2.Data Struct
##### Arrays
[The Video Course of Arrays](https://www.coursera.org/lecture/data-structures/arrays-OsBSF)
##### Linked Lists
[singly-linked-lists-kHhgK](https://www.coursera.org/lecture/data-structures/singly-linked-lists-kHhgK)
##### Stack
##### Queue
##### 
#### 3.Coding Website
#### 4.Note of Book
##### Clean Code
There are two parts to learning craftsmanship: KNOWLEDGE and WORK.
The only way to make the deadline - the only way to go fast - is to keep the code as clean as possible at all time.
**Meaningful Name**
 - Use Intension-revealing Names
 - Avoid Disinformation
 - Make Meaningful Distinction
 - Use Pronounceable Names
 - Use Searchable Names
 - 

#### 5.DevOps
##### CI/CD
##### K8S
##### Docker
#### 6.More Knowledge
### Getting the Job
---
#### 1.How to Make a Resume
#### 2.Find a Job
#### 3.How to Write a Thank You Letter
**Example One:**
> Dear [interviewer name],
> Thank you again for taking the time to speak with me about the [job title] position and for giving me additional insight into the responsibilities and day-to-day duties involved. Our conversation today only increased my interest in the role. I would be thrilled to use my [insert a skill or two that you discussed in your interview, such as "editorial skills and background research and interviewing"] to benefit [company name] and your goals, including the work you're doing on [insert a specific example of a project or work your interview mentioned,such as "expanding into video and other multimedia content"].
> Please don't hesitate to reach out if you have additional questions for me! I look forward to having another conversation with you soon.
> Best regards,
> Your Name

**Example Two:**
> Hello [Interviewer Name],
> It was a pleasure to meet you today (dd/mm/yyyy). I wanted to take the opportunity to thank you once more for considering me for the _____ position. Our conversation made me fell even more confident that my current transferable skills and character are a great fit for what the team is looking for, I am eager to learn and can learn fast.
> I particularly enjoyed learning about the various projects/analysis that the team has been running to oversee the investment risk of the firm, and everyone in the team has the choice to rotate on project executions and analysis tasks. Furthermore, I want to join a team that I commit to long-term that will providing ongoing opportunity for growth and has great colleagues and leaders who I can continuously learn from. Based on our conversation, I know that the team aligns with these goals.
> Thank you again for your time and consideration, and look forward to hearing about next steps!

 

