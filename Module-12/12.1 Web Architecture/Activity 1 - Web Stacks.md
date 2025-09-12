## Activity Objective

Students will research and analyze various web stacks (such as LAMP, MEAN, MERN, and JAMstack) to understand their architecture, performance, scalability, development speed, and flexibility. By the end of this activity, students should be able to:

1. Identify the core components of each web stack.
2. Explain the architectural differences between the web stacks.
3. Evaluate the performance and scalability trade-offs for each stack.
4. Identify how development speed and flexibility are impacted by different web stacks.
5. Provide recommendations on when to use each stack based on project requirements.

## Activity Instructions
Complete the knowledge check below.

### Knowledge Check
1. Which components make up the typical LAMP stack?
    1. Linux, Apache, MongoDB, PHP
    2. Linux, Apache, MySQL, PHP
    3. Linux, Apache, MySQL, Python
    4. Linux, Apache, MongoDB, Perl
<details closed> <summary>Answer</summary><p>The LAMP stack is a popular open-source framework used to build dynamic web applications. It consists of four main components: Linux as the operating system foundation, Apache as the web server that delivers content to users, MySQL (or MariaDB) as the database that stores and organizes application data, and PHP (sometimes substituted with Perl or Python) as the programming language that generates dynamic content and application logic. Together, these layers work seamlessly to provide a reliable, scalable, and cost-effective environment for hosting and developing websites and web applications.</p></details>

2. What key difference sets the MERN/MEAN/MEVN stacks apart from LAMP?
    1. MERN/MEAN/MEVN stacks use JavaScript across the entire stack.
    2. LAMP is a more scalable stack than MERN/MEAN/MEVN.
    3. MERN/MEAN/MEVN stacks are only used for desktop applications.
    4. LAMP uses NoSQL databases, while MERN/MEAN/MEVN uses relational databases.
<details closed> <summary>Answer</summary><p>In MERN (MongoDB, Express, React, Node.js), MEAN (MongoDB, Express, Angular, Node.js), and MEVN (MongoDB, Express, Vue.js, Node.js), both the front end and back end use JavaScript (or TypeScript). The database (MongoDB) is also NoSQL instead of relational like MySQL.. In LAMP, the back end runs on PHP (with MySQL and Apache on Linux). The front end is typically built separately using HTML/CSS/JavaScript.</p></details>

3. In terms of scalability, which stack(s) is often favored for handling high concurrency and real-time data? Select all that Apply.
    1. MERN
    2. Ruby on Rails
    3. MEAN
    4. MEVN
<details closed> <summary>Answer</summary><p>When it comes to scalability for high concurrency and real-time data, stacks built on Node.js such as MERN, MEAN, and MEVN are often preferred over LAMP. This is because Node.js  allows it to efficiently handle thousands of simultaneous connections, making it ideal for applications like chat platforms, live dashboards, or online gaming. Combined with tools like WebSockets for real-time communication and MongoDB’s ability to scale horizontally through sharding (a database scaling technique) and replication, these stacks provide strong support for low-latency, high-throughput environments.</p></details>

4. What makes the .NET stack ideal for large-scale enterprise applications?
    1. Robust security features
    2. .NET is a full-stack development platform 
    3. Open source
    4. Full integration with Microsoft services and enterprise tools
<details closed> <summary>Answer</summary><p>The .NET stack is considered ideal for large-scale enterprise applications because it provides a robust, flexible, and enterprise-grade framework backed by Microsoft. It supports multiple programming languages (like C#, F#, and VB.NET), which gives teams flexibility while maintaining strong integration with enterprise systems like the Windows Server, Active Directory, SQL Server, and Microsoft Azure, which are already widely used in corporate environments.</p></details>

5. Which web stack(s) would be best suited for a startup looking to quickly develop a dynamic web app with minimal setup and fast iteration? Select all that apply.
    1. MERN
    2. MEAN
    3. WISA
    4. MEVN
<details closed> <summary>Answer</summary><p>For a startup that wants to quickly build a dynamic web application with minimal setup and the ability to iterate fast, stacks like MERN (MongoDB, Express, React, Node.js) and MEVN (MongoDB, Express, Vue.js, Node.js) are often the best choices. Both stacks use JavaScript end-to-end, which means the same language is used on the front end and back end, reducing complexity and speeding up development. MongoDB as a NoSQL database makes it easy to adapt to changing requirements without rigid schemas, while Express and Node.js provide a lightweight, fast, and scalable server environment. On the front end, React (MERN) or Vue.js (MEVN) offer powerful frameworks for building dynamic user interfaces with rapid iteration. Together, these stacks give startups the flexibility to launch quickly, make changes easily, and scale their applications as demand grows.</p></details>

6. In terms of development speed, what advantage does the LAMP stack offer over other stacks?
    1. It is faster for building mobile apps
    2. LAMP is more secure by default
    3. Easier to set up and widely supported, including prebuilt tools and libraries
    4. Better suited for handling front-end JavaScript
<details closed> <summary>Answer</summary><p>The LAMP stack offers an advantage in development speed because it is mature, widely used, and has a massive ecosystem of prebuilt tools, libraries, and community support. Developers can quickly set up a server with Linux, Apache, MySQL, and PHP since many hosting providers offer it out of the box, and PHP has a wealth of frameworks (like Laravel or CodeIgniter) that simplify building dynamic applications. Its long history also means there are countless tutorials, documentation, and troubleshooting resources available, reducing the time needed to solve problems. This makes LAMP especially appealing for teams that want to get a functional web application running quickly with minimal setup.</p></details>

7. In the MEAN/MERN/MEVN stacks, what is the purpose of Node.js?
    1. It’s used as a front-end framework.
    2. It handles front-end client-side logic with JS.
    3. It handles the back-end server-side logic with JS.
    4. It is the database layer for MEAN.
<details closed> <summary>Answer</summary><p>In the MEAN, MERN, and MEVN stacks, the purpose of Node.js is to serve as the runtime environment that runs JavaScript on the server side, enabling developers to use the same language for both front-end and back-end development.</p></details>

8. If a web application needs to handle heavy relational data processing (i.e. processing large volumes of structured information that is tightly connected) with complex queries, which stack(s) would be the most suitable? Select all that apply.
    1. LAMP (with MySQL)
    2. .NET (with SQL Server)
    3. MEVN (with MongoDB)
    4. Ruby (with PostgreSQL)
<details closed> <summary>Answer</summary><p>If a web application needs to handle heavy relational data processing with complex queries, stacks like LAMP with MySQL, .NET with SQL Server, and Ruby on Rails with PostgreSQL are the most suitable. These stacks are built around powerful relational database systems that excel at managing structured data, enforcing relationships, and executing advanced queries efficiently. MySQL, SQL Server, and PostgreSQL all support robust features like transactions, indexing, and stored procedures, making them well-suited for applications where data integrity and complex querying are critical. Combined with their respective frameworks, these stacks provide stability, maturity, and strong database integration, which makes them reliable choices for data-intensive applications.</p></details>

9. For a project focused on flexibility and cross-platform development, which web stack(s) could you choose? Select all that apply.
    1. LAMP
    2. MERN
    3. MEAN
    4. WISA
<details closed> <summary>Answer</summary><p>For a project that prioritizes flexibility and cross platform development, MERN and MEAN are excellent choices. Both use JavaScript end to end, letting teams share code and skills across the stack. Node.js and Express run on any operating system and container platform, while MongoDB offers a flexible schema that adapts as requirements change. On the front end, React in MERN or Angular in MEAN supports rapid UI development and a rich ecosystem of components.</p></details>

10. The typical Windows stack is often referred to as the WISA stack, stands for?
    1. Windows, IIS, SQL Server, .NET
    2. Windows, IIS, PostgreSQL, ASP.NET
    3. Windows, IIS, SQL Server, ASP.NET
    4. Windows, IIS, SQL Server, .NET
<details closed> <summary>Answer</summary><p>The typical Windows stack is often referred to as the WISA stack, which stands for Windows, IIS, SQL Server, and ASP.NET. In this setup, Windows provides the operating system foundation, IIS (Internet Information Services) acts as the web server, SQL Server handles the relational database needs, and ASP.NET provides the framework for building dynamic web applications. Together, these components form a tightly integrated stack commonly used in enterprise environments where Microsoft technologies are the standard.</p></details>

11. For an e-commerce platform that requires high performance, scalable architecture, and the ability to handle large amounts of traffic, which stack(s) could be used? Select all that apply.
    1. LAMP
    2. MERN
    3. .NET
    4. Ruby on Rails
<details closed> <summary>Answer</summary><p>For an e-commerce platform that needs high performance, scalability, and the ability to handle heavy traffic, strong options include MERN, .NET, and Ruby on Rails. The MERN stack leverages Node.js’s event-driven, non-blocking model to efficiently handle large numbers of concurrent users, while MongoDB provides flexible data storage that can scale horizontally. The .NET stack, particularly with ASP.NET Core and SQL Server, offers enterprise-grade performance, reliability, and integration with cloud services, making it a robust choice for large-scale deployments. Ruby on Rails, though traditionally known for rapid development, has proven scalability when paired with PostgreSQL, caching systems like Redis, and horizontal scaling. Each of these stacks provides the tools needed to build a responsive, scalable e-commerce system capable of supporting large customer bases.</p></details>

12. Relational databases are databases that store data in structured tables with pre-defined schemas. Which database technology are considered relational databases? Select all that apply.
    1. MySQL
    2. PostgreSQL
    3. NoSQL
    4. Oracle Database
    5. Microsoft SQL Server
<details closed> <summary>Answer</summary><p>Relational databases store data in structured tables with defined schemas, and some of the most widely used technologies are MySQL, PostgreSQL, Oracle Database, and Microsoft SQL Server. MySQL is popular for web applications because of its speed and ease of use, while PostgreSQL is known for its advanced features, strong standards compliance, and reliability. Oracle Database is often chosen by large enterprises for its scalability, performance, and comprehensive toolset, and Microsoft SQL Server is widely used in corporate environments for its deep integration with the .NET ecosystem and Windows services. Together, these systems represent the core of relational database technology, providing powerful tools for managing structured data and ensuring data integrity.</p></details>
