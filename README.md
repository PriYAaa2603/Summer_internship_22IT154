# Internship Weekly Report

## Introduction
I completed a 5-week internship as a DevOps Trainee, working offline and gaining practical insights into various AWS services. This report provides a detailed summary of the tasks and projects I worked on each week. The experience allowed me to enhance my skills in cloud computing, server management, and automation, which are crucial for a career in DevOps.

## Weekly Report

### Week 1: Setting Up the Environment
- **Creating an AWS Free Tier Account and Logging In**: I began by setting up a new AWS Free Tier account, which provided free access to a variety of AWS services for a limited time. This step involved configuring account settings and familiarizing myself with the AWS Management Console.
- **Creating a Lightsail Instance**: AWS Lightsail is a simplified service for managing virtual private servers. I created an instance with Linux as the operating system, ideal for learning server management and deploying web applications.
- **Connecting to the SSH Shell**: Using SSH (Secure Shell), I securely connected to the Lightsail instance to perform command-line operations.
- **Learning About Networking, Storage, and Other Aspects of an Instance**: I explored essential components such as networking (VPC, subnets), storage (block storage, snapshots), and security (firewalls, security groups).
- **Implementing Basic Linux Commands**: Practiced basic Linux commands like navigating directories, managing files, and checking system status, which are fundamental for server administration.
- **Building a Snapshot of the Instance**: Created a snapshot of the instance, a crucial step for backup and disaster recovery, ensuring data and configuration safety.

### Week 2: Database Management
- **Installing MS-SQL on Ubuntu 22.04**: Followed the official AWS guide to install Microsoft SQL Server on an Ubuntu instance, providing a robust database solution for enterprise applications.
- **Installing Command-Line Tools**: Set up tools like `sqlcmd` and `bcp` for interacting with the MS-SQL server from the command line.
- **Connecting the Server Locally**: Established a secure connection to the SQL server using credentials, allowing local machine access to the database server.
- **Creating a Database**: Created a new database using T-SQL commands, setting up tables and schemas as needed.
- **Inserting Data into the Database**: Populated the database with sample data to practice CRUD (Create, Read, Update, Delete) operations and SQL queries.

### Week 3: Advanced Server Management
- **Managing MS-SQL Service**: Learned commands to start, stop, and restart the MS-SQL service, essential for maintenance and troubleshooting.
- **Zipping and Unzipping Files**: Practiced file compression and decompression using `zip` and `unzip` commands, focusing on `.rar` files for efficient storage and transfer.
- **Monitoring Memory Usage and Disk Space**: Used tools like `top`, `htop`, and `df` to monitor system performance, memory usage, and disk space, ensuring optimal resource allocation.
- **Connecting the Live Server Locally**: Configured local machine settings to connect to the live server, facilitating remote management.
- **Learning SQL Server Management Studio**: Explored SQL Server Management Studio (SSMS), a powerful GUI tool for managing SQL Server instances and databases.
- **Running .NET Core on Linux**: Deployed and executed a basic .NET Core application on the Linux server, demonstrating cross-platform capabilities.

### Week 4: API Development and Management
- **Creating Basic APIs with Node.js**: Developed RESTful APIs using Node.js, a popular JavaScript runtime, and tested endpoints with Postman.
- **Managing Lightsail Bucket with APIs**: Created APIs to interact with Lightsail object storage, handling file and folder operations programmatically.
- **Implementing JWT Tokenization**: Added JWT (JSON Web Token) authentication to secure APIs, ensuring only authorized access.
- **Automating Backups**: Wrote a shell script to automate daily backups of the Lightsail bucket, scheduled with cron jobs for regular execution.

### Week 5: Working with AWS Lambda
- **Creating AWS Lambda Functions**: Deployed serverless functions with AWS Lambda, reducing infrastructure management and enabling scalable execution.
- **Running Node.js and .NET Code in Lambda**: Tested Lambda functions with both Node.js and .NET Core runtimes, demonstrating flexibility in supported languages.
- **Uploading Code as Zip Files**: Packaged code and dependencies into zip files for Lambda deployment, simplifying the upload process.
- **Using S3 Buckets for Larger Files**: Utilized S3 buckets for storing and managing larger zip files, integrating with Lambda for seamless code execution.
- **Testing with JSON Inputs**: Conducted extensive testing of Lambda functions using various JSON inputs, ensuring robustness and reliability.
- **Setting Up API Gateway**: Configured API Gateway to create and manage RESTful APIs, linking them to Lambda functions for dynamic, scalable backend services.

## Conclusion
This internship provided valuable hands-on experience with AWS services, Linux server management, database operations, API development, and automation. The skills and knowledge gained will be instrumental in future projects and career growth in DevOps and cloud computing. I am now more proficient in setting up and managing cloud infrastructure, developing and securing APIs, and automating routine tasks, all of which are critical skills for a successful career in DevOps.
