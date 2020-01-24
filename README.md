# design-patterns
Notes on design-patterns
## Creational patterns - How classes are instantiated 
#### Need for recognizing creationsal patterns 
- sometimes while designing systems you recognize need for having one and only one instance of an object
- sometimes the object creation is very costly 
- sometimes you might have a very complex constructors where some of the elements are optional, very hard for user to understand and remember the construct, right? 

so solution for such problems have already been identified and hence creational patterns
 1. Singleton - single instance per execution e.g., Cache, ThreadPool, 
 2. Builder
 3. Factory and abstract Factory
 4. Prototype  - create set of objects configured in various ways (prototypes) and then clone them when you need a similar instance for your use.  advantage is that when you "new" something its in init state and then you need to set all the values of the fields (sometimes that are inaccessible from your code(private) ), whereas in prototype - you as the concrete class to give you the instance with the preconfigured data. *Remember deep clone and shallow clone and difficulty in implementing the clone method in case of circular references*
