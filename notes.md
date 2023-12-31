## Java through .NET lens

* .NET SDK - **JDK**
* C#, F#, VB.NET - **Java, Groovy, Scala, Kotlin**
* CSC - **javac**
* IL - **Bytecodes**
* CLR - **JVM**
* Visual Studio - **Eclipse, IntelliJ, VS Code**

## JDK

* https://www.oracle.com/in/java/technologies/downloads/
* **java -version**
* Before version 8 (0r 1.8) and after 8(Or 1.8)

## Day 01

* Data types; Primitive and Reference types
* Primitive types are stored in the stack; Reference types are stored on the heap
* Wrapper classes used to box primitive types; Integer, Double, Byte, Long, Boolean
* Strings; Immutable; Stored in the string pool; There is an implicit object created to refer to the literal in the pool
* Everytime you change the value, a new literal thereby a new object is created
* If you want to manipulate strings, use StringBuilder 
* Two ways of creating strings; with/without using new keyword;
* Use **.equals** to compare the values of the string
* foreach, for, while, do-while
* if-else, ?:, switch-case

## Day 02

* OO concepts; 
* Java beans; POJO with no-arg constructor, private variables; public getter/setter methods
* extends, super, for inheritance;
* redefine the base class method with the same signature in the derived class is considered **overriding**
* private, static, final(sealed) methods; final(sealed) classes cannot be extended
* abstract;
* Inner classes; can access private members of outer class; you can create an instance of inner class only using outer class object;
* Compiler generates Outer$Inner.class files

## Day 03

* interfaces; **implements** keyword to inherit interfaces
* can have constants; abstract methods; default methods and also static methods
* record, enum;
* packages: physical grouping of folders and files
* by default the access specifier for an entity is package-friendly;
* java.util: List, Set, Map; java.io, java.nio,java.net, java.sql

## Day 04

* interfaces with just one abstract method are Functional interfaces
* You can syntactically mark them as **@FunctionalInterface**
* Lambda expression is an implementation of functional interface
* You use the lambda (->) operator and specify single line or multi-line implementations of interface
* During runtime, lambda expression is converted to a new (anonymous inner) class 
* Lambda expressions can be passed as arguments to other functions
* Conceptually lambda expression paves way for storing block of code as values to variables

``` java
@FunctionalInterface
interface Greetings {
	void hello(String name);
}

Greetings greetings = name -> System.out.println("Hi " + name);
greetings.hello("Sam");
```

## Day 05

* java.util.function.*
* Functional interfaces; Predicate, Function, Supplier, Consumer
* Method Reference operator **::** 
* Shortcut for lambda expressions
* System.out::println, String::toUpperCase (str -> str.toUpperCase())


## Day 06

* Stream API
* Stream is an abstraction/snapshot of a collection
* Create a stream on a collection by using .stream() method
* Streams are used for read-only operations on collections
* Stream cannot be reused once it's acted upon
* Streams are lazily evaluated till the terminal operation like get, collect, forEach is called.
* filter, map, reduce, max, min, collect
* Optional type; Optional type is a like a box that holds data; You need to check if it contains the data and **get()** the value

## Day 09

* **java.util.concurrent** is the package that contains classes dealing with concurrency
* Thread class and pass implementation of Runnable interface
* **ExecutorService** to create thread pools. Submit your task to the thread pool.
* Number of threads = number of cores/(1 - BlockingFactor)
* Blocking factor is between 0 to 1 depending on whether the task is CPU intensive or IO intensive
* Fixed thread pool, Cached thread pool, ForkJoinPool


### Quarkus

* Install JDK ( Java Standard Edition, Java SE)
* Core VM (Hotspot JVM), Coretto JVM, Eclipse Temurin, Graal VM 
* **Enterprise applications**; REST API, Web application, Messaging, Security, Scheduling, ORM
* Install JEE SDK (Java Enterprise Edition, JEE)
* Core JEE SDK is just one of the implementations out there; Not widely used
* Rest API -> Spring Boot, Struts, Jersey, Quarkus, RestEasy
* ORM(JPA) -> Hibernate, TopLink, Mybatis, Core JPA
* Messaging -> spring boot, spring cloud streams, quarkus
* All in one -> Framework
* **Spring boot; Quarkus; Micronaut**; -> Frameworks that contains all the libraries/tools to build enterprise applications in Java. They are the implementations of JEE spec

* Became popular when Microservices started getting more adopted
* Microservices unlike SOA is not a standard
* Microprofile (https://microprofile.io/) is an effort to standardize microservices architectures
* **Quarkus** is a framework that conforms to the Microprofile standard of building microservices
* Quarkus is k8s native(*marketing gimmick in my opinion*)
* Quarkus performs faster than its competitors like spring boot, because it can generate native executables: - **More about this later*
*
### Dependency Injection

* DI: Fundamental principle on which frameworks like Quarkus and Spring boot are designed upon
* DI is a mechanism by which you avoid writing unneccesary creation and lookup code

#### Quarkus Day 11

* https://code.quarkus.io 
* Select the version, build tool, extensions(or dependencies)
* quarkus-arc is the main dependency for DI
* **@QuarkusMain** : Commandline application
* Mark the bean in a scope: @Singleton or @ApplicationScoped
* @Inject the beans wherever you need
* @ConfigProperty or @ConfigMapping(prefix = "")
* @Named, @Default or @Alternative



















 