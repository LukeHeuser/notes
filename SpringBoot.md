# SpringBoot

# What is Spring?
Spring is a Java framework that makes it easy to create Java Enterprise Applications.

The Spring Framework is divided into modules. At the center are the modules of the core container, including a configuration model and a dependency injection mechanism.

The `Spring Framework` provides foundational support for different application architectures, including `messaging`, `transactional data and persistence`, and `web`. It also includes the Servlet-based Spring MVC web framework and, in parallel, the Spring WebFlux reactive web framework.


A note about modules: Spring Framework’s jars allow for deployment to the module path (Java Module System). For use in module-enabled applications, the Spring Framework jars come with `Automatic-Module-Name` manifest entries which define stable language-level module names (`spring.core`, `spring.context`, etc.) independent from jar artifact names. The jars follow the same naming pattern with `-` instead of `.` – for example, `spring-core` and `spring-context`. Of course, Spring Framework’s jars also work fine on the classpath.

Spring Framework 6.0 is fully compatible with Tomcat 10.1, Jetty 11 and Undertow 2.3 as web servers, and also with Hibernate ORM 6.1.


