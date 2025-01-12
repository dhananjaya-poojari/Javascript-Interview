
<details>
<summary>
  Interview Questions
</summary>

 1. [Difference between HTTP 302 Redirect and HTTP 301 Redirect](#difference-between-http-302-redirect-and-http-301-redirect)
 1. [How to Improve API Performance?](#how-to-improve-api-performance)
 2. [What’s the difference between a load balancer and an API gateway?](#whats-the-difference-between-a-load-balancer-and-an-api-gateway)
 3. [What’s the difference between a Kafka and RabbitMQ?](#whats-the-difference-between-a-kafka-and-rabbitmq)
 4. [What are the best practices for designing a scalable system that handles unpredictable traffic spikes?](#what-are-the-best-practices-for-designing-a-scalable-system-that-handles-unpredictable-traffic-spikes)
</details>

### Difference between HTTP 302 Redirect and HTTP 301 Redirect
`HTTP 302 Redirect` status is sent back to the browser instead of `HTTP 301 Redirect`. A 301 redirect means that the page has permanently moved to a new location. A 302 redirect means that the move is only temporary. Thus, returning 302 redirect will ensure all requests for redirection reaches to our backend and we can perform analytics (Which is a functional requirement).

### How to Improve API Performance?
![image](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/8d0ae19d-7ace-42e8-8db9-ff62739d4c4a)

Result Pagination: 
This method is used to optimize large result sets by streaming them back to the client, enhancing service responsiveness and user experience.

Asynchronous Logging: 
This approach involves sending logs to a lock-free buffer and returning immediately, rather than dealing with the disk on every call. Logs are periodically flushed to the disk, significantly reducing I/O overhead.

Data Caching: 
Frequently accessed data can be stored in a cache to speed up retrieval. Clients check the cache before querying the database, with data storage solutions like Redis offering faster access due to in-memory storage.

Payload Compression: 
To reduce data transmission time, requests and responses can be compressed (e.g., using gzip), making the upload and download processes quicker.

Connection Pooling: 
This technique involves using a pool of open connections to manage database interaction, which reduces the overhead associated with opening and closing connections each time data needs to be loaded. The pool manages the lifecycle of connections for efficient resource use.
### What’s the difference between a load balancer and an API gateway?
API Gateway acts as a single entry point for all API requests and provides features such as request routing, rate limiting, authentication, and API versioning and also hide the complexities of the underlying microservices from the client applications.

Load Balancer, on the other hand, is responsible for distributing incoming request across multiple instances of a microservice to improve availability, performance, and scalability. It helps to evenly distribute the workload across multiple instances and ensures that each instance is utilized to its fullest potential.

### What’s the difference between a Kafka and RabbitMQ?
RabbitMQ and Apache Kafka allow producers to send messages to consumers. Producers are applications that publish information, while consumers are applications that subscribe to and process information.

 | Kafka | RabbitMQ |
| ------------- | ------------- |
|RabbitMQ is a general-purpose message broker that prioritizes end-to-end message delivery.|Kafka consumers, however, are more proactive in reading and tracking information.|
|RabbitMQ brokers allow producer software to escalate certain messages by using the priority queue.|Apache Kafka doesn't support priority queues. It treats all messages as equal when distributing them to their respective partitions. |
|RabbitMQ sends and queues messages in a specific order. |Kafka uses topics and partitions to queue messages.|
|A RabbitMQ broker routes the message to the destination queue. Once read, the consumer sends an acknowledgement (ACK) reply to the broker, which then deletes the message from the queue.|Apache Kafka appends the message to a log file, which remains until its retention period expires. That way, consumers can reprocess streamed data at any time within the stipulated period.|

![Message Queue](https://github.com/dhananjaya-poojari/Interview-preparation/assets/77887564/5a350516-63c7-4c3d-b121-9ed7e2863023)

### What are the best practices for designing a scalable system that handles unpredictable traffic spikes?
**Strategies to Handle Traffic Spikes**

1. **Load Balancing**
   Implement load balancing to distribute incoming traffic across multiple servers. This helps prevent any single server from becoming overloaded.
   - **Software Load Balancers**: Nginx, HAProxy
   - **Cloud Load Balancers**: AWS ELB, Azure Load Balancer, Google Cloud Load Balancing

2. **Caching**
   Use caching to store frequently accessed data and reduce the load on your servers.
   - **CDN**: Content Delivery Networks cache static assets like images, CSS, and JavaScript files closer to users.
   - **In-Memory Caching**: Use Redis or Memcached to cache dynamic data and database queries.

3. **Auto-Scaling**
   Automatically scale your infrastructure up or down based on demand to handle traffic spikes.
   - **Horizontal Scaling**: Add more servers or instances to your infrastructure.
   - **Vertical Scaling**: Upgrade server resources (CPU, memory) to handle increased load.

4. **Database Optimization**
   Optimize your database to handle high read and write operations efficiently.
   - **Indexing**: Ensure proper indexing to speed up query performance.
   - **Replication**: Use read replicas to distribute read operations and offload the primary database.

5. **Content Delivery Networks (CDNs)**
   Distribute your content across multiple servers worldwide to reduce latency and handle traffic spikes.
   - **Cloudflare**: Provides CDN, DDoS protection, and security services.
   - **Akamai**: Offers CDN and edge computing services.
   - **Fastly**: Content delivery network with real-time analytics and caching.

6. **Rate Limiting**
   Implement rate limiting to prevent abuse and ensure fair usage of your resources.
   - **API Rate Limiting**: Control the rate of requests to your APIs to prevent overload.
   - **User Rate Limiting**: Limit the number of requests per user to prevent abuse.

7. **Queuing**
   Use message queues to manage and process high volumes of tasks asynchronously.
   - **RabbitMQ**: Open-source message broker that supports multiple messaging protocols.
   - **Kafka**: Distributed streaming platform for building real-time data pipelines and streaming applications.

8. **Monitoring and Alerts**
   Monitor your infrastructure and set up alerts to get notified of potential issues before they impact your website.
   - **Monitoring Tools**: Prometheus, Grafana, Datadog
   - **Alerting Systems**: PagerDuty, Opsgenie, VictorOps
