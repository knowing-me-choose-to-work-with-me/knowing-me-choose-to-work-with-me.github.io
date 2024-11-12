# My Tech Stack
- [My Java Stack & Few Titbits ](#my-java-stack--few-titbits)
- [microservices](#microservices)
- [flourishing And Relevant Java Stack](#flourishing-and-relevant-java-stack)
- Note: under construction
## My Java Stack & Few Titbits   
- Please see my Java view also in [Fascinating Technologies](fascinating-technologies.md#fascinating-technologies)
- if you r thinking  sustainability, 
        - [comment]: https://ionutbalosin.com/2024/03/analyzing-jvm-energy-consumption-for-jdk-21-an-empirical-study/
        - [energy-efficiency](https://thenewstack.io/which-programming-languages-use-the-least-electricity/)
        - [awspblog - Rust is also interesting](https://aws.amazon.com/blogs/opensource/sustainability-with-rust/?pg=devrust)
- My stack, my View on  Java & a bit on its Ecosystem
- At low-level lot of core-java conecpts are pretty much neutral and  common to data-structure, algorithms in general. My grip strongly comes from having deeper understanding on java internals, aggregation on large-object-graphs, multithreading conrtol, hashing techniques of java.
- Relevant:  
### microservices
    - Springboot 
    - more to come 
### data-centric 
- of course in my 18years, i have seen the evoultion of lot of Java technogies many fading to constantly flourshing like Spring, spring-boot, Jdbc
- its multi-paradigm 
- what i personally like in java one side is imperative sytle,  fine grained control on mutation of objects for large data sets , imagining a thread on jvm heap of course we have to trade off the heavy verbose code for it. 
- also for my thinking style, JVM , its memory model, garbage-collection techniques, multithreading, concurrency etc suite well , probably in few of my attempts I failed to understand this in python
- just see below database technologies written in java, if you would like to research more.
- if you are new to java or need to know what stuff could be built with to excite you or broaden on mindset
    - [dynamodb](https://en.wikipedia.org/wiki/Amazon_DynamoDB), [cassandra](https://en.wikipedia.org/wiki/Apache_Cassandra) [kafka](https://en.wikipedia.org/wiki/Apache_Kafka) [neo4j](https://en.wikipedia.org/wiki/Neo4j)
- jdk-21 
    - in my view , the most promising release  after java-8,  I am yet to leverage java 9 modularity yet in some real world project
    - very exciting with virtural-threads, just a conigruation-change(spring.thread-executor=virtual) in springboot should boost performance, though i need to test for a heavy thread centric micro-service in pilot mode, before productionizing it. 
    - record pattern, simplicity at best with implicit(immutablity,adaptive defaults), data-oriented programming,
        - complemented with streams we could do some good aggregations, reduction with 1-step closer towards matrix operations
        - atleast we  can now get rid of lombok annotation, 
- just my view dont take it to heart if you are still using EJB, applets etc - Rephrase
    - some flourish and current trend (spring,springboot) leveraging aop, DI, cloud integrations
    - ehy EJB failed near to endagered (EJB) , in my view also http-statless helps a lot, so stateful bean, hyped entity beans didnt make sense as data-volume growth increased
    - to extinct(Java applet) 
- ### flourishing And Relevant Java Stack
- [springboot](https://spring.io/projects/spring-boot)
    - this is a game changer in java for building production ready microservices 
    - leveraging cloud integration support, 
    - vast data-acess libraries from simple-powerful-jdbc to nosql(cassandra,neo4j)
- JDBC
    - my goto tool to access data
    - @JDBCTemplate simplifies all the boiler plate and good to use especially while pulling large data sets in batch, complex sql joins for transparency (orm tools really fail here only in my view and experience)
    - ofcourse for simple cases could be replaced by @Entity from spring
[comment]: to add to my stack Micronaut, and Quarkus | learning tools such as ELKI, DL4J, and JAVA-ML | 
    
- ### My Java Old-Stack
- experience-in-building :  
    ### desktop-application first 6+ years
    - [Java Swing](https://en.wikipedia.org/wiki/Swing_(Java)), tables, tabletrees, gridbaglayouts(my-goto-layout-manager)
    -  I pretty much built whatever came to me, end-to-end with backend jdbc/hibernate/ejb 
    - notable works to recall inventory-search, appoinment-scheduler, HQ-store-hierarchy,field-technician-application, 
    - had build lot reubsable-components be it at user-interface level or backing data-models especially leveraging components
        - on a side note, also had worked on a proprietary RIA canoo ULC , which was a half-object server side technology
    - last used 2014
    ### web-applications 
        - Servlet, JSP, JSF EJBs, Hibernate backed by JBOSS, now wildfly servers
        - back in those times we used several custom patterns like facade, dto, dao layers to leverage on these verbose technologies.
        - last used 2014
    ### mobile-application 2+years
    - blackberry-field-technician-app, primarily leveraged more or less the knowledge of java-swing over here, 
    - last used 2012
    ### web services 1+years
    - soapful-webservices, officially this is my first web 
- a bit on technologies once like dinosaurs and now pretty much superceeded by annotations @Restcontroller, @Service
- servlet 
    - first J2ee technology to serve data on top of http-request-response library component in 2000s now abstracted by Spring framework by @Restcontroller
- JSP
    - dynamic content + static html served by underlying servlet technology, no more relevant now
- JSF
    - building web components as a developer, i didnt like it much, never got comfortable with it, as i recall it was due to verbose of tagging and inflexibility etc
- CORBA 
    - it was really complex to understand and complex enough to explain now as well
    - just FYI in case intersted, then as I recall it helped even  hetergeneous  java, c++ objects to communicate with interfaces and technology defined by corba-interfaces
- RMI (simply superceded by @RestController)
    - last used 2016, 2017
    - first basic block of distributed programming in java
    - uses socket programing  leveraging tcp/ip with java interfaces 
    - java agnostic not hetergenous like Corba
- SOAP  (simply superceded by @RestController from spring)
    - last used in 2014,2015
    - xml over http , to serve data
    - Restful architectural style did a good job in getting rid of strict-xml-schema-wsdl-verbose
    - this is my first web api development experience around 2012
    - had good exposure to  xml-parsers( sax and jax ) , a bit of http
- [JMS](https://en.wikipedia.org/wiki/Jakarta_Messaging)

