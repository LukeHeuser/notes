# SpringBoot

# What is Spring?

Spring is a *Java Framework* that makes it easy to create Java Enterprise Applications.

The Spring Framework is divided into modules. At the center are the modules of the core container, including a `configuration model` and a `dependency injection mechanism`.

The `Spring Framework` provides foundational support for different application architectures, including `messaging`, `transactional data and persistence`, and `web`. It also includes the Servlet-based Spring MVC web framework and, in parallel, the Spring WebFlux reactive web framework.

A note about modules: Spring Framework’s jars allow for deployment to the module path (Java Module System). For use in module-enabled applications, the Spring Framework jars come with `Automatic-Module-Name` manifest entries which define stable language-level module names (`spring.core`, `spring.context`, etc.) independent from jar artifact names. The jars follow the same naming pattern with `-` instead of `.` – for example, `spring-core` and `spring-context`. Of course, Spring Framework’s jars also work fine on the classpath.

* `Spring Framework 6.0` is fully compatible with `Tomcat 10.1`, `Jetty 11` and `Undertow 2.3` as `web servers`, and also with `Hibernate ORM 6.1`

Today, with the help of Spring Boot, applications are created in a devops- and cloud-friendly way, with the Servlet container embedded and trivial to change. 


## Why Spring?

Spring provides the most important features needed to build easily maintanable applications: `Dependency Injection` & `Autowiring`.

Spring Boot Makes using the Spring Frame work *MUCH* easier.

## Spring Framework Terminology

* Tight Coupling
* Loose Coupling
* Dependency Injection
* IOC Container
* ApplicationContext
* Spring Beans
* Autowiring
* Component Scan

# Group ID & Artifact ID

Group ID & Aritifact ID are very similar to `Package Name` & `Class Name`

Maven is a dependency managment tool. Maven downloads the Spring framework and makes it available to us

# What is Tight Coupling?

Coupling is a measure of how much work is involved in changing something.

Tightly Coupled Eample: *An engine is tighlty coupled to a car*

Losely Coupled: *A wheel is losely coupled to a car*

We want to have loose coupling as much as possible. This allows us to make changes to our program without affecting other methods and accidentally breaking it. This also allows us to make changes more easily.


# @Configuration

The `@Configuration` annotation indicates that a class declares one or more `Bean Methods`. They may be *processed* by the `Spring Container` to generate `Bean Definitions` and service requests for those `@Beans` at runtime.

In a @Configuration class, we can define Spring Beans. The objects which are managed by Spring are what are called, `Spring Beans` and we can define the methods to create these Spring Beans in our `configuration class`.

The underlying purpose of the Configuration annotation in a Spring application is to mark a class as a source of `Bean Definitions`, allowing the Spring container to manage the beans defined within it!

# @Bean
`@Bean`: Indicates that a method produces a bean to be managed by the `Spring Container`.

# Creating a Spring Context

The below is creating a `Spring Context` with a `Configuration Class`. Our Configuration Class needs to be launched and that's where the Spring Context comes in!

```
var context = new AnnotationConfigApplicationContext(*ConfigurationClassName*.class);
```

# What is the Spring Container?

* `Spring Container`: Manages Spring beans & their life cycle

* `IOC Container` = Inversion of Control Container 

```
|POJO|   |CONFIG|
    \     /
|IOC CONTAINER|
      ||
|READY SYSTEM|
```

* Our Java classes & Config file are passed as inputs to the `Spring Container`

* The IOC Container creates the runtime system. This is whats creating the Spring contest and managing the beans for us

## Two Types of IOC Containers

1. Bean Factory: Basic Spring Container
2. ApplicationContext: Advanced Spring Container with enterprise specific features such AS:
* Building a web application
* Internationalization features
* Integration with Spring AOP (Aspect Orineted Programming)

NOTE: ApplicationContext is the most frequently used.

Most enterprise applications use ApplicationContext which is recommended for: web apps, web servises - REST API and micro services.

# How is the ApplicationContext an IOC Container?

1. Bean Management: 

The ApplicationContext maintains and manages the lifecycle of beans, ensuring the dependencies are injected where needed.

2. Dependency Injection:

 Automatically injects required dependencies, following the IoC principle.

3. Enhancements Over BeanFactory: 

The BeanFactory is the basic IoC container, ApplicationContext provides additional Feaetures like:

* ClassPathXmlApplicationContext

* FileSystemXmlApplicationContext

* AnnotationConfigApplicationContext

* GenericWebApplicationContext


# POJO vs JavaBean vs SpringBean

EJB = Enterprise Java Beans (These are rarely used or seen)

There are 3 constraints to EJB's:
1. It has a public no-arg constructor
2. uses getters and setters
3. must impliment the interface serializable

### SpringBean

Any java object that is managed by the spring framework is called a spring bean. 

Spring uses the IOC Container (`BeanFactory` or more likely, `ApplicationContext`) to manage these Objects

### POJO

POJO = Plain Old Java Object 

Any Java Object is a POJO

# What To Do With Multiple Matching Beans
When there are multiple matching beans, these are called candidatess. Spring will throw an exception if one of the beans (candidates) is not `@Primary`.

Below is an example of setting a bean as a primary over another candidate. Remember, that when calling `context.getBean(Person.class)`, there would be an exception if one of the spring beans isn't set as the primary.

```
@Bean
@Primary
public Person person4Parameters(String name, int age, Address address){
    return new Person(name, age, address);
}

@Bean
public Person person3Parameters(String name, int age, Address address3){
    return new Person(name, age, address3);
}
```

Another option to handling this exception if you do not want a primary, is to use `@Qualifier`.

```
@Bean
public Person person5Qualifier(String name, int age, @Qualifier("address3Qualifier") Address adress){
    return new Person(name, age, adress);
}

@Bean(name = "address3")
@Qualifier("address3Qualifier")
public Address address3() {
    return new Address("William St.", "Delaware");
}
```

The `@Qualifier` works by auto injecting a designated bean into the Spring beans parameter.

# How to Wire Spring to Create and Manage Spring Beans

Firstly, we will use the annotation `@Configuration`, on our class that contains the `Spring Context`. Typically, the Spring `Application Context` which is an `IOC (Inversion of Control) Container`. 
















