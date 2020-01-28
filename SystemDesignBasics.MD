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
 cache invalidation schemes, eviction policies( LRU ), in-memory cache, application v/s database cache
 
 #### Cache invalidation schemes - keeping cache coherent with source
     - Write-through cache - write data into cache and DB at the same time. Although, write through minimizes the risk of data loss, since every write operation must be done twice before returning success to the client, this scheme has the disadvantage of higher latency for write operations.
     - Write-around cache: write to permanent storage first bypassing cache. 
     - Write-back cache: data written to cache alone and confirmation provided to client. periodic conditional writes to permanent storage
     
#### Cache eviction policies
    - *F*irst*I*n*F*irst*O*ut
    - *L*ast*I*n*F*irst*O*ut
    - *L*east*R*ecently*U*sed
    - *M*ost*F*requently*U*sed
    - *L*east*F*requently*U*sed
    - *R*andom*R*epalcement
 
 
 #### Content distribution networks (CDN) 
     Distribution network for static media for global websites. So takes the load off app server to serve static media and provide geographic distribution
 
 
