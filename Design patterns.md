# **Design-patterns**
Notes on design-patterns
## Creational patterns - How classes are instantiated 
#### Need for recognizing creational patterns 
- sometimes while designing systems you recognize need for having one and only one instance of an object
- sometimes the object creation is very costly 
- sometimes you might have a very complex constructors where some of the elements are optional, very hard for user to understand and remember the construct, right? 

so solution for such problems have already been identified and hence creational patterns
 1. Singleton - pattern to solve 2 problems - 
    1. single instance per execution
    2. Global access to the instance
    
   e.g., Cache, ThreadPool, Database *Remember eager v/s Lazy initialization, Double-check-locking, multi-threading concerns*
   
 2. Builder - Complex step to construct new objects (e.g., to create Car you need to build, chassis, body, install engine, wheels, seats and similar various customizations) so you you abstract the construction of the underlying product in concrete builders and then either call the builders methods directly or delegate even that part to a Director(provide the builder in the constructor) and just use the high level method of the Directors to construct the necessary object. Concreate builder will instantiate the product and keep on customizing it via various setters and then on the final call to get the product it can return to you the finished product. also offers method to reset the state so that you can start afresh after a certain point.
 3. Factory - different from static factory methods 
 4. Abstract factory
 5. Prototype  - create set of objects configured in various ways (prototypes) and then clone them when you need a similar instance for your use.  advantage is that when you "new" something its in init state and then you need to set all the values of the fields (sometimes that are inaccessible from your code(private) ), whereas in prototype - you as the concrete class to give you the instance with the preconfigured data. *Remember deep clone and shallow clone and difficulty in implementing the clone method in case of circular references*

*** 

## Structural patterns - How to assmeble classes and objects into larger structure while keeping them efficient and flexible
#### Need for recognizing structural patterns
 - How to structure objects such in order to reduce coupling
 - To identify relationships between objects inorder to simplify the structure 
 
 1. Adapter - use object composition principle to implement the interface of one of the objects and wraps the other one. So Adapter provides a different interface to the wrapped object. 
 2. Bridge - ![very powerful graphical reprsenetation of what Bridge does] (https://refactoring.guru/images/patterns/content/bridge/bridge-3-en-2x.png "Bridge Pattern")
 3. Proxy
 4. Decorator
 5. Flyweight
 6. Composite
 7. Facade
