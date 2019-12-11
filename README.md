# Spring Boot 2.2 Liquibase problem

Starting from Liquibase 3.8.1 Liquibase packages some pro obfuscated code 
in their Maven Central liquibase-core.jar. 
This is not Java 11 compatible, since it uses `XmlElement` and throws an exception when run on Java 11.

Steps to reproduce the problem:

1. Make sure you have Java 11
1. run `mvn spring-boot:run`
1. The application does not boot

Changing the liquibase version to `3.8.0` works.
