## Activity Objectives:

Students will apply their understanding of various cloud service models by analyzing real-world scenarios and determining the most appropriate service model for each situation. Afterwards providing a justification for their choices by considering the specific requirements, advantages, and constraints associated with each service model and provide a detailed rationale for their decisions.

## Activity Instructions:
Read each case study scenario, and determine which "as-a-service" model will best fit the customer's use case.

#### Activity Terminology:

**FaaS (Functions as a Service):** Provides a serverless computing model where users can execute individual functions or pieces of code in response to events without managing servers.

**DBaaS (Database as a Service):** Offers cloud-based database solutions managed by a provider, including features like automatic backups, scalability, and maintenance, without the need for physical hardware.

**SaaS (Software as a Service):** Provides access to software applications over the internet, which are hosted and managed by a third-party provider, eliminating the need for local installation and maintenance.

**SECaaS (Security as a Service):** Delivers security services and solutions through the cloud, including threat detection, protection, and compliance management, managed by a third-party provider. SECaaS providers are referred to as Managed Security Providers (MSPs).

**PaaS (Platform as a Service):** Delivers a platform allowing developers to build, deploy, and manage applications without handling the underlying infrastructure, including development tools and runtime environments.

**IaaS (Infrastructure as a Service):** Offers virtualized computing resources over the internet, including servers, storage, and networking, allowing users to build and manage their own IT infrastructure.

### Knowledge Check
1. **Scenario:** A marketing agency, "Creative Solutions," needs a comprehensive tool to manage client relationships, track campaign performance, and handle project management. They want a solution like HubSpot that requires minimal setup, is accessible from anywhere, and is easy to use without needing extensive IT resources.

    **Question:** Which cloud model should the startup choose? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
Creative Solutions should use a Software as a Service (SaaS) solution because it provides an all-in-one tool that can handle client management, campaign tracking, and project management without requiring the agency to manage infrastructure or IT resources. SaaS platforms are easy to set up, accessible from anywhere through a web browser, and include built-in features that support collaboration and reporting. Since the provider manages updates, security, and scalability, the agency can focus on its marketing work rather than technical maintenance.
  </p>
</details>

2. **Scenario:** An e-commerce startup, "ShopSmart," is launching its online store. They need scalable virtual servers to handle variable traffic, storage for product images and customer data, and networking capabilities. They want a flexible infrastructure solution that can grow with their business.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
ShopSmart should use an Infrastructure as a Service (IaaS) solution because it provides scalable virtual servers, storage, and networking that can grow with their business. IaaS gives them flexibility to handle variable traffic, especially during peak shopping seasons, without needing to invest in physical hardware. Since the infrastructure is managed by the provider, the startup can focus on building and running its online store while still having control over the operating systems, applications, and configurations needed to support their e-commerce platform.
  </p>
</details>

3. **Scenario:** A software development company, "DevMasters," is building a new web application and needs a development and deployment platform that simplifies app creation, testing, and deployment without managing the underlying infrastructure.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
DevMasters should use a Platform as a Service (PaaS) solution because it provides a ready-made environment for developing, testing, and deploying web applications without the need to manage servers, storage, or networking. PaaS streamlines the entire application lifecycle by offering built-in tools, frameworks, and automation for continuous integration and deployment. This allows developers to focus on writing and improving code instead of handling infrastructure tasks, making it faster and easier to bring their web application to market.
  </p>
</details>

4. **Scenario:** A company, "Eventify," creates an application that processes real-time events, such as user clicks and data updates. They need a serverless solution to execute code in response to these events without having to maintain the servers themselves.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
Eventify should use a Function as a Service (FaaS) solution, often called serverless computing, because it allows them to run code in response to real-time events without managing any servers. With FaaS, the cloud provider automatically handles infrastructure, scaling, and availability, so the company only pays for the compute time when their code runs. This makes it ideal for processing user clicks, data updates, and other event-driven tasks efficiently, while freeing the developers from worrying about server setup or maintenance.
  </p>
</details>

5. **Scenario:** An online publishing platform, "PublishNow," requires a scalable, managed solution to be able to store articles, user data, and analytics without investing in physical hardware or database management.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
PublishNow should use a Database as a Service (DBaaS) solution because it provides a fully managed, scalable database environment without the need to purchase hardware or handle database administration tasks. With DBaaS, the platform can easily store and manage articles, user data, and analytics while the cloud provider takes care of backups, updates, scaling, and security. This allows PublishNow to focus on improving its publishing platform while ensuring reliable data management and performance.
  </p>
</details>

6. **Scenario:** A DevOps team at "TechWave" is building and deploying microservices-based applications. They need a platform that simplifies container orchestration and management, allowing for efficient deployment and scaling.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
TechWave should use a Container as a Service (CaaS) platform, such as a managed Kubernetes service like Amazon EKS, Azure AKS, or Google GKE. CaaS provides built in container orchestration for microservices based applications, including automated scaling, service discovery, rolling updates, and health checks, while the provider manages the control plane and most infrastructure tasks. This lets the DevOps team deploy and scale efficiently, keep environments consistent from development through production, and focus on delivery rather than cluster maintenance.
  </p>
</details>

7. **Scenario:** A financial institution, "SecureBank," needs robust security solutions to protect sensitive financial data, comply with regulations, and manage security threats without maintaining an in-house security team.

    **Question:** Which cloud service will fit their needs? Why?
<details closed>
<summary>Answer Key</summary>
  <p>
SecureBank should use Security as a Service (SECaaS) because it delivers cloud-based security tools such as data encryption, threat monitoring, intrusion detection, and compliance management without requiring an in-house security team. With SECaaS, the provider handles updates and monitoring, ensuring the institution stays protected against evolving threats while meeting strict financial regulations. This allows SecureBank to safeguard sensitive financial data, maintain compliance, and reduce costs by relying on a trusted cloud security provider instead of building and managing its own security infrastructure.
  </p>
</details>
