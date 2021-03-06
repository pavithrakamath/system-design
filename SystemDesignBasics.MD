# SOLID Design Principles
- **S**ingle Responsibility - A class must have only one reason to change (think of writing a domain object that even persists the object. If domain logic changes or persistence changes, the class will change)
- **O**pen Closed Principle - A software entity should be open for extension but closed for modification
think of classes that have strategies defines as switch case / if else statements. If a new strategy is added, then code needs to be updated. Consider Interfaces to define the **Closed** part of the principle and different implementations to achieve the Open for modification by creating new implementations.
- **L**iskov substitution principle -  Objects of subclass should have in the same way as the objects of superclass. i.e., Objects of the superclass shall be replaceable with objects of its subclass without breaking the application. This in turn means that the validations in the subclass cannot be stricter than the ones in the superclass.
e.g., If you have an IceCream as base class, IceLolly extends IceCream and overrides addScoop method to throw Exception then it is a violation of the principle because the superclass objects cannot be replaced by the subclass without breaking the application. 
- **I**nterface segregation - Interface should be broken into small related collection of methods that will be implemented by all classes that implement it. e.g.,
If Bird is your interface and fly is a method of that interface, then you break this principle because not all birds can fly. So rather have Flyable as the interface and make flight birds implement them.
- **D**ependency Inversion - invert an application's dependency from concretions to abstractions. High level modules should not depend on low level modules, and details should depend on abstractions.
e.g., repository model of object persistence, where you create a repository object for each type of the underlying database and make your service layer have an instance of the repository injected at runtime.
# Key Characteristics of Distributed Systems
-  **M**anageability - How easy is it to maintain and operate. how fast you can recover from failed system, how easy to upgrade, monitor
-  **A**vailability - system operational to perform its required function in a specific period
-  **R**eliability - guarantee that the requested operation will be completed
-  **S**calability 
    -  vertical i.e., add more power to existing server(CPU, RAM, Storage etc), limited to the capacity of the server and cannot scale beyond that upper limit 
    - horizontal i.e., scale by adding more servers
-  **E**fficiency 
    - Throughput - 
    - Latency -

# Load Balancing Algorithms
    - Least connection method - useful when there are a large number of persistent client connections which are unevenly distributed between the servers.
    - Least response time - 
    - Least Bandwidth method - selects the server that is currently serving the least amount of traffic measured in megabits per second (Mbps).
    - Round robin method - useful when not many persistent connections and all servers are of equal spec
    - Weighted Round robin method - useful when servers in the pool are of different spec. servers with higher weight receive more traffic than ones with less weights.
    - IP Hash - hash of client IP used to redirect request to a server (server affinity)
    
 To avoid making LBs as the single point of failure, configure another as passive and form a cluster. 
 
 # Caching
 cache invalidation schemes, eviction policies( LRU ), in-memory cache, application v/s database cache
 
 #### Cache invalidation schemes - keeping cache coherent with source
     - Write-through cache - write data into cache and DB at the same time. Although, write through minimizes the risk of data loss, since every write operation must be done twice before returning success to the client, this scheme has the disadvantage of higher latency for write operations.
     - Write-around cache: write to permanent storage first bypassing cache. 
     - Write-back cache: data written to cache alone and confirmation provided to client. periodic conditional writes to permanent storage
     
#### Cache eviction policies ####
 - **F**irst**I**n**F**irst**O**ut
 - **L**ast**I**n**F**irst**O**ut
 - **L**east**R**ecently**U**sed
 - **M**ost**F**requently**U**sed
 - **L**east**F**requently**U**sed
 - **R**andom**R**epalcement
 
 
 #### Content distribution networks (CDN) 
     Distribution network for static media for global websites. So takes the load off app server to serve static media and provide geographic distribution
 
 
# Data Partitioning
 1. Horizontal partition (Data sharding)
 1. Vertical partition
 1. Directory based partitioning

# Proxy Servers
1. Open Proxy -proxy server that is accessible by any Internet user
    * anonymous proxy - doesn't reveal the initial IP so beneficial to hide the client IP address
    * transparent proxy - first ip can be viewed via HTTP headers. benefit is to cache the websites
1. Reverse Proxy - retrieves resources on behalf of a client from 1 or more servers while appearing to the client as if they originated from the proxy server itself.


# Entities and Value Objects
1. Entities - Identifier / Reference Equivalence implies object equivalence. Like ( 2 person with same name are nt same, they are same only if the Identifier / reference is same)
1. Value Objects - Structural / reference Equivalence implies object equivalence. e.g., ( 2 co-ordinates are pointing to same position if the X and Y have same values, 2 1 dollar bills are same as long as their value is 1 dollar). So they don't have identity fields. They are generally immutable. They are part of an entity and generally never by themselves.

#Microservices communication Patterns
1. Async Services communicating via events
    * use of queuing technology like RabbitMQ 
    * fire and forget interactions
1. Competing Workers Patterns
    * Use of Message Brokers 
    * Multiple instances of subscribing services compete to consume the event from the broker
1. Fanout Pattern
    * event sent to message broker (fanout exchange)
    * event copied to multiple subscribers for each of them to process
1. Async API call
    * Client calls the service and registers a callback method
    * Service carries out the task and responds back by calling the callback method
    * Client receives response