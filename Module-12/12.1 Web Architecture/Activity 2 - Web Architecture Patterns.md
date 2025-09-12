## Activity Objective

Students will explore and analyze various web application architecture patterns, including monolithic, microservices, serverless, and layered architectures. Through this activity, they will research the defining characteristics, advantages, and disadvantages of each pattern. Students will then demonstrate their understanding by completing a quiz that assesses their ability to differentiate between these architectures and apply their knowledge to real-world scenarios. This will enhance their critical thinking skills and prepare them for making informed architectural decisions in software development.



## Activity Instructions

Complete the knowledge check below.

### Knowledge Check
1. What is a defining characteristic of monolithic architecture?
    1. It consists of independent services that communicate over APIs.
    2. All components are integrated into a single codebase and deployed together.
    3. It is always the fastest architecture available.
    4. It allows for different technology stacks for each component.
<details closed> <summary>Answer</summary><p>A defining characteristic of monolithic architecture is that the entire application is built as a single, unified codebase where all components (like the user interface, business logic, and data access) are tightly connected and run together. This makes it easier to start with, but harder to scale or update parts independently, since a change in one area often means redeploying the whole system.</p></details>

2. Which of the following is a key advantage of microservices architecture?
    1. Simplicity in deployment
    2. Scalability of independent services
    3. Single codebase for the entire application
    4. Faster performance due to minimal network calls
<details closed> <summary>Answer</summary><p>A key advantage of microservices architecture is that the application is divided into smaller, independent services that can be developed, deployed, and scaled separately. This allows teams to work on different parts of the system at the same time, improves flexibility, and makes it easier to update or expand features without affecting the entire application.</p></details>

3. In a serverless architecture, what is primarily managed by the cloud provider?
    1. Database schema
    2. API documentation
    3. Server management and scaling
    4. User authentication
<details closed> <summary>Answer</summary><p>In a serverless architecture, the cloud provider primarily manages the servers and infrastructure needed to run the code. This means developers only focus on writing and deploying functions, while the cloud provider automatically handles scaling, availability, and maintenance of the underlying resources.</p></details>

4. Which architecture pattern is best suited for applications that require high availability and can handle variable workloads?
    1. Serverless
    2. Microservices
    3. Monolithic
    4. Layered
<details closed> <summary>Answer</summary><p>The architecture pattern best suited for applications that require high availability and can handle variable workloads is  a serverless architecture. In a serverless architecture, the cloud provider automatically scales resources up or down based on demand, ensuring the application remains available and efficient without the need to manage servers directly.</p></details>

5. What is a potential disadvantage of monolithic architecture?
    1. Easier to test and debug
    2. Does not allow the independent scaling of components
    3. Difficult to deploy in cloud environments
    4. Performance can degrade with increasing complexity
<details closed> <summary>Answer</summary><p>A potential disadvantage of monolithic architecture is that it does not allow the independent scaling of components. Because everything is built as one large, unified codebase, if a single feature needs more resources, the entire application must be scaled, which is inefficient and resource-heavy.</p></details>

6. Which architecture pattern is characterized by running code in response to events and only consuming resources while the code is executing?
    1. Monolithic
    2. Microservices
    3. Serverless
    4. Layered
<details closed> <summary>Answer</summary><p>The architecture pattern characterized by running code in response to events and only consuming resources while the code is executing is serverless. In this model, functions are triggered by specific events, and the cloud provider automatically allocates and releases resources, so you only pay for the actual execution time.</p></details>

7. What is a common challenge when using microservices architecture?
    1. All components are tightly coupled.
    2. All services must be written in the same programming language.
    3. All services must be written in the same programming language.
    4. Requires complex orchestration and inter-service communication management.
<details closed> <summary>Answer</summary><p>A common challenge when using microservices architecture is that it requires complex orchestration and inter-service communication management. Because services are independent and distributed, coordinating how they interact, share data, and remain reliable adds extra complexity compared to a single unified system.</p></details>

8. Which architecture pattern allows for the combination of multiple technology stacks within the same application?
    1. Monolithic
    2. Serverless
    3. Layered
    4. Microservices
<details closed> <summary>Answer</summary><p>The architecture pattern that allows for the combination of multiple technology stacks within the same application is microservices. Because each service is independent, different teams can use the programming language, framework, or database that best suits their needs, making it possible to mix technologies within one overall system.</p></details>

9. Which architecture pattern organizes an application into separate layers such as presentation, business logic, and data access, with each layer having a distinct responsibility?
    1. Microservices
    2. Layered
    3. Monolithic
    4. Serverless
<details closed> <summary>Answer</summary><p>The layered architecture pattern organizes an application into separate parts such as presentation, business logic, and data access. Each part has its own responsibility and interacts only with the part directly above or below it. This clear division of responsibilities makes the system easier to design, update, and troubleshoot, since changes in one part usually do not affect the others.</p></details>

10. Which architecture pattern builds an application as a single unified codebase where all components such as the user interface, business logic, and data access are tightly connected?
    1. Monolithic
    2. Microservices
    3. Serverless
    4. Layered
<details closed> <summary>Answer</summary><p>The monolithic architecture pattern builds the entire application as one large unit where all parts are closely linked together. This makes it easier to start with because everything is in one place, but it becomes harder to update or scale individual parts since any change usually requires redeploying the whole system.</p></details>
