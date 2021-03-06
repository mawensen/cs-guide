#### What components or methods have you used to improve website performance, usability and concurrency
- Improve hardware capabilities and increase system servers. (When the server increases to a certain extent, the concurrent access that the system can provide is almost unchanged, so the problem cannot be fundamentally solved)
- Use cache (local cache: JDK's own Map, Guava Cache. Distributed cache: Redis, Memcache. Local cache is not suitable for increasing the concurrency of the system, generally used in the program).
- Use Browser cache.
- CDN acceleration (cache some static resources such as pictures, videos, etc. to the network node closest to the user)
- Database Split (read-write separation), sub-table (horizontal sub-table, vertical sub-table)
- Use the appropriate connection pool (database connection pool, thread pool, etc.)
- Message queue (decoupling + peak clipping + asynchronous)
- Adopt a cluster (multiple machines provide the same service)
- Use distributed development - Use micro-service architecture. (different services are deployed on different machine nodes, and a service can also be deployed on multiple machines, and then use Nginx load balancing access. This solves the shortcomings of single point deployment (All In), greatly Increased system concurrency)

#### Common methods for designing high-availability systems
- Downgrading Service: Service downgrading refers to the strategic downgrading of some services and pages based on current business conditions and traffic when server pressure increases sharply, so as to release server resources to ensure the normal operation of core tasks. Downgrades often specify different levels and perform different treatments for different abnormal levels. According to the service method: the service can be rejected, the service can be delayed, and sometimes the service can be random. According to the scope of service: you can cut off a certain function, you can also cut off some modules. In short, service degradation requires different degradation strategies according to different business requirements. The main purpose is that although the service is damaged, it is better than nothing;
- Current limit: Prevent malicious request traffic, malicious attacks, or prevent traffic from exceeding the peak value of the system;
- Caching: Avoid a large number of requests from directly falling into the database, which will destroy the database;
- Timeout and retry mechanism: Avoid avalanche caused by request accumulation;
- Rollback mechanism: Quickly fix the wrong version.

#### What are the characteristics of modern Internet application systems?
- High concurrency and large traffic;
- High availability: system 7×24 hours uninterrupted service;
- Mass data: need to store and manage mass data, and need to use a large number of servers;
- The users are widely distributed and the network situation is complicated: many large-scale Internet services provide services for users around the world, and the users are distributed in a wide range, and the network conditions in various regions are very different;
- Poor security environment: Due to the openness of the Internet, the Internet is more vulnerable to attacks, and large websites are attacked by hackers almost every day;
- Rapid changes in demand and frequent releases: Unlike the release frequency of traditional software versions, Internet products quickly adapt to the market and meet user needs, and their product release frequencies are extremely high;
- Progressive development: Unlike traditional software products or enterprise application systems that plan all functional and non-functional requirements from the beginning, almost all large-scale Internet websites start from a small website and develop gradually.

#### Do you know about performance testing? Tell me about the performance testing tools you know?
Performance testing refers to the use of automated testing tools to simulate a variety of normal, peak and abnormal load conditions to test various performance indicators of the system. Performance testing is a general term, usually subdivided into:
- Benchmark test: When lower pressure is applied to the system, check the operating status of the system and record the relevant data as a basic reference
- Load test: Refers to the continuous increase of pressure on the system or the duration under a certain pressure, until one or more performance indicators of the system reach a safety critical value, for example, a certain resource has reached a saturated state. At this time, continue to pressurize, and the processing capacity of the system will decrease.
- Stress test: Under the condition of exceeding the safe load, keep applying pressure (increasing concurrent requests) until the system crashes or cannot handle any requests, so as to obtain the maximum stress tolerance of the system.
- Stability test: The tested system runs for a long period of time under specific hardware, software, and network environment with a certain business pressure (simulating different time points in the production environment, uneven requests, showing wave characteristics) to check whether the system is stable.
- The most commonly used testing tool for back-end programmers or testing is JMeter (official website: https://jmeter.apache.org/). Apache JMeter is a Java-based stress testing tool (100% pure Java application) designed to load test functional behavior and measure performance. It was originally designed for Web application testing but later expanded to other testing areas.

#### Micro-Service Questions:
https://www.knowledgehut.com/interview-questions/microservices