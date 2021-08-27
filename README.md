<h1 align="center">
  <br>
  <a href="https://spring.io"><img src="images/spring.png" alt="Markdownify" width="200"></a>
  <br>
 AOP-Spring-Notes
  <br>
</h1>

For factual reference please look at official spring.io guide here: `https://docs.spring.io/spring-framework/docs/2.5.x/reference/aop.html`

## Aspect Oriented Programming Overview

- DAO (Data Access Object)

  - structural pattern that allows us to isolate the application/business layer from the persistence layer (usually a relational database, but it could be any other persistence mechanism) using an abstract API.

  Read more about DAO here : `https://www.baeldung.com/java-dao-pattern`

- add logging code for the current session in hibernate. trying to understand what the session is doing

- new requirement security to the DAO

- add account method adding code for security check

- AOP potentially resolves code tangling and scattering

- Java does not support multiple inheritance (remember that).

## The purpose

- Cross cutting concern logic is looking is looking at overall functionality
- (taking classes and injecting between other classes (diagram)):

- aspect can be reused at multiple locations and can be applied based on configuration

## Solution

- Apply proxy design pattern approach

## Benefits

- code aspect defined in single class

- very configurable

## Use cases

- logging, audit logging(who, what, when where), api management(average load, who is top user??), expection logging and handling(sms to devops team example), cache management

## Advantages and Disadvantages of AOP

Pros:

- resusable

- resolve code tangling

- resolve code scatter

- applied selectively based on configuration

Cons:

- too many aspects and app flow is hard to follow

- performance cost is minor for run-time

## AspectJ (java-extension) The OG AOP Framework.

- Terminology:

  Aspect: A modularization of a concern that cuts across multiple objects. Each aspect focuses on a specific crosscutting functionality

- Join point: A point during the execution of a script, such as the execution of a method or property access

- Advice: Action taken by an aspect at a particular join point
- Pointcut: A regular expression that matches join points. An advice is associated with a pointcut expression and runs at any join point that matches the pointcut

- weaving:

  - linking aspects with other application types or objects to create an advised object. This can be done at compile time (using the AspectJ compiler, for example), load time, or at runtime. Spring AOP, like other pure Java AOP frameworks, performs weaving at runtime.

## AspectJ vs Spring AOP

- Adv:simpler than AspectJ,

  - can be directly exported into AspectJ if the project becomes more complex

- Disad: Only supports spring beans and method level join points, making it quite limited

---

- Aspectj supports ALL joint points

  - works with any POJO

  -completely supports AOP

  - faster but it can become very complex and WILL increase compilation time.

## Our Goals with AOP

- Create aspects, develop advices, create pointcut expressions build major CRM projects

## advice types

- Before: runs before method

- after finally: run after method

  - after returning: on success it executes
  - after throwing: runs after exception thrown

- Around: runs before and after the method

## Presummed Assumptions

- A Pointcut is a program element that picks out which join point is being executed in various forms or situations

1. Advice is what makes a join point

2. Pointcut decides what join point is executed??

3. All of this exists within the Aspect (which is the container for the other containers(container inception!!))
