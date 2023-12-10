# System Design
<details>
<summary>
  Table of Contents
</summary>

 1. [Horizontal vs Vertical Scaling](#horizontal-vs-vertical-scaling)
 2. [Distributed System](#distributed-system)
 3. [Load balancing](#load-balancing)
 4. [Consistent Hashing](#consistent-hashing)
 5. [Message Queue](#message-queue)
 6. [Database Sharding](#database-sharding)
 7. [Blob/object Storage](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#blobobject-storage)
 8. [CDN](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#cdn)
 9. [Database Indexes](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#database-indexes)
 10. [API Gateway](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#api-gateway)
 11. [Data Replication](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#data-replication)
 12. [Web sockets](https://github.com/dhananjaya-poojari/Interview-preparation/tree/main/System%20Design#web-sockets)
</details>

### Horizontal vs Vertical Scaling
 | Horizontal | Vertical |
| ------------- | ------------- |
|Scale Out|Scale up|
|Horizontal scaling involves adding `more machines` to a system|Vertical scaling involves adding `more power` to an existing machine.|
|Automatically scales by adding or reducing computing nodes as workload increases or decreases.|Adding more power to an existing machine, such as CPU, RAM, storage, or network speed.|
|Load balancing is essential for efficiently distributing the workload across multiple nodes.|Not required in the single node.|
|Workload is distributed across multiple nodes.|A single node handles the entire workload.|
|Minimize downtime by ensuring that if one system fails, another will seamlessly handle the request.| The occurrence of system failure results in downtime.|
|Add as many machines as you can|Limited to the resource capacity the single machine can handle|

![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/014bd462-a886-4e99-8663-0bc49b26d6d7)
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/22b8fa9e-612f-451d-ae71-83b1f7e9101b)
> https://www.cloudzero.com/blog/horizontal-vs-vertical-scaling/
### Distributed System
A distributed system is a collection of computer programs that utilize computational resources across multiple, separate computation nodes to achieve a common, shared goal.Distributed systems aim to remove bottlenecks or central points of failure from a system.
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/ec12fd07-5858-4ca4-bd11-2aae3eb611cb)
> https://www.atlassian.com/microservices/microservices-architecture/distributed-architecture <br />
> https://youtu.be/K0Ta65OqQkY?feature=shared
### Load balancing
If the system requires High Availability,Performance, and Throughput, we should consider using a Load Balancer.Load balancing directs and controls internet traffic between the application servers and their visitors or clients. As a result, it improves an application’s availability, scalability, security, and performance.< br />
Some examples of load balancing include: 
- Round-robin method
- Least connection method
- Least response time method
- Weighted round-robin method
- IP hash method
- Weighted least connection method

![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/38757066-2857-41ba-afd7-dd872c22b84e)
> https://aws.amazon.com/what-is/load-balancing/
### Consistent Hashing
Consistent hashing is a distributed hashing technique that assigns positions to servers and objects in a hash ring.It works well when the number of machines storing data may change. Consistent hashing minimizes the number of keys that need to be remapped when the number of nodes changes.

![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/7cb7d3bb-995b-4622-90f8-803378db9faf)
> https://vishalrana9915.medium.com/consistent-hashing-36fa25892b4f#:~:text=WHAT%20IS-,CONSISTENT,-HASHING%3F
### Message Queue
A message queue is a type of middleware that allows communication between programs, services, and other components. It's a queue of messages sent between applications. 
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/94fab944-d05b-410e-95d1-4ce5ad87beb7)
> https://aws.amazon.com/message-queue/ <br />
> https://youtu.be/oUJbuFMyBDk?feature=shared
### Database Sharding
Database sharding is a technique for splitting a large database into smaller chunks, called shards.Sharding, also known as horizontal partitioning, is a popular scale-out approach for relational databases.
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/c8f95167-b970-4f78-bfbd-7e3165a41348)
> https://aws.amazon.com/what-is/database-sharding/
### Blob/object Storage
  Binary Large Object (blob) storage is a type of object storage. Blob storage keeps these masses of data in non-hierarchical storage areas called data lakes; a data lake/pool is a large collection of unstructured data.

  File and block storage are often not flexible enough or scalable enough for modern organizations. By contrast, object storage is so scalable that some consider it to be "unlimited" storage. However, using object storage instead of file or block storage can make data retrieval more complicated.

  Example: <br />
  Imagine Alice stores her clothes in curated outfits that are ready to be worn, while Bob simply tosses his clothes into a pile. Bob's method is more like blob storage: any item of clothing can go into his pile, and the clothes do not have to be organized in any particular way. Bob's method is advantageous in that he can quickly and almost endlessly grow his pile of clothes: he can just toss more on, instead of folding and organizing them like Alice.
  > https://www.cloudflare.com/en-gb/learning/cloud/what-is-blob-storage/
### CDN
A content delivery network (CDN) is a group of servers that are spread out across the world. CDNs are also known as content distribution networks.CDNs cache content from a network location that is closest to a user. This speeds up the delivery of content. 

CDNs can cache the following types of content: <br />
`HTML pages, JavaScript files, Stylesheets, Images, Videos, Large file downloads, Video streaming.`<br />

CDNs can also: 
- Improve page load speed
- Handle high traffic loads
- Reduce bandwidth consumption
- Load balance between multiple servers
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/31d5de55-f3f0-4940-809f-5dacf060ccf8)

  > https://www.cloudflare.com/en-gb/learning/cdn/what-is-a-cdn/
### Database Indexes
A database index is a data structure that allows for faster access to data. It's made up of two columns: a search key and a data pointer.The key stores the value you want to search for, and the pointer points to the block where the data is located.

When to use? `If the system requires high performing database queries, we should consider using Database Indexes.`
### API Gateway
An API gateway is a software layer that acts as a mediator between client applications and backend services.It's a single endpoint for various APIs that performs tasks such as: Request composition, Routing, Protocol translation.

Some benefits of using an API gateway include: 
- Securing traffic between API consumer requests and the execution of services
- If the system has microservices, we should consider using an API Gateway (Authentication, SSL Termination, Routing etc).
### Data Replication
Data replication is the process of copying data from one location to another. It can be used to create identical copies of data across multiple storage locations, systems, or databases.
### Web sockets
WebSocket is a communication protocol that allows for two-way communication between a client and a server over a single TCP connection. This protocol allows for real-time, event-driven communication.You can send messages to a server and receive event-driven responses without having to poll the server for a reply.
### Microservice Arhitecture
### SQL or No-SQL based on ACID 