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
    
 To avoid making LBs as the single point of failure, configure another as passibve and form a cluster. 
 
 # Caching
 Read about caching strategies
