Introduction: I have done my internship as a DevOps Trainee for 5 weeks in offline mode and working with different services of AWS having practical insights to the projects which can be helpful for the company. Here is the weekly report of the work done by me:

## Week 1:  AWS Lightsail Instance Setup and Management

- **Create an AWS Free Tier Account**
  - Sign up at [AWS Free Tier](https://aws.amazon.com/free) and log in to the AWS Management Console.

- **Create a Lightsail Instance**
  - Navigate to Lightsail, click "Create instance".
  - Select "Linux/Unix" as the OS, choose the free tier plan, name your instance, and click "Create".

- **Connect to the SSH Shell**
  - In the Lightsail dashboard, select your instance and click "Connect using SSH".
  - Or use an SSH client:
    ```bash
    ssh -i /path/to/your/private-key.pem username@your-instance-public-ip
    ```

- **Explore Instance Features**
  - **Networking**: Configure static IPs, DNS, and firewalls in the Networking tab.
  - **Storage**: Manage attached disks in the Storage tab.
  - **Monitoring**: Track instance performance using built-in tools.

- **Basic Linux Commands**
  - Run commands to manage your server:
    ```bash
    sudo apt-get update        # Update package lists
    sudo apt-get install -y package-name  # Install a package
    df -h                      # Check disk space
    ls -la                     # List files
    top                        # Check running processes
    ```

- **Create a Snapshot**
  - In the instance management page, go to the "Snapshots" tab.
  - Click "Create snapshot", name it, and confirm.

## Resources

- [AWS Lightsail Documentation](https://docs.aws.amazon.com/lightsail/index.html)
- [Basic Linux Commands](https://www.tutorialspoint.com/unix/unix-useful-commands.htm)
- [SSH Access Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)


# Week 2: Installing MS-SQL on Ubuntu 22.04

## Steps

- **Install MS-SQL Server**
  - Follow the [official guide](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu) to install MS-SQL Server on Ubuntu 22.04:
    ```bash
    curl -sSL https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    sudo add-apt-repository "$(curl -sSL https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list)"
    sudo apt-get update
    sudo apt-get install -y mssql-server
    sudo /opt/mssql/bin/mssql-conf setup
    sudo systemctl status mssql-server
    ```

- **Install Command-Line Tools**
  - Install the SQL Server command-line tools:
    ```bash
    curl -sSL https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    sudo add-apt-repository "$(curl -sSL https://packages.microsoft.com/config/ubuntu/22.04/prod.list)"
    sudo apt-get update
    sudo apt-get install -y mssql-tools unixodbc-dev
    echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
    source ~/.bashrc
    ```

- **Connect to the Server Locally**
  - Connect using the command-line tool:
    ```bash
    sqlcmd -S localhost -U SA -P 'your_password'
    ```

- **Create a Database**
  - Create a new database:
    ```sql
    CREATE DATABASE TestDB;
    GO
    ```

- **Insert Data into the Database**
  - Insert data into the newly created database:
    ```sql
    USE TestDB;
    GO
    CREATE TABLE TestTable (ID INT, Name NVARCHAR(50));
    INSERT INTO TestTable (ID, Name) VALUES (1, 'John Doe');
    INSERT INTO TestTable (ID, Name) VALUES (2, 'Jane Smith');
    GO
    ```

## Resources

- [MS-SQL Server on Linux Documentation](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-overview)
- [SQL Server Tools Documentation](https://docs.microsoft.com/en-us/sql/tools/sqlcmd-utility)
- [SQL Tutorial](https://www.w3schools.com/sql

# Week 3: Managing MS-SQL and Working with .NET Core on Linux

## Steps

- **Start, Stop, and Restart the MS-SQL Service**
  - Start MS-SQL Server:
    ```bash
    sudo systemctl start mssql-server
    ```
  - Stop MS-SQL Server:
    ```bash
    sudo systemctl stop mssql-server
    ```
  - Restart MS-SQL Server:
    ```bash
    sudo systemctl restart mssql-server
    ```

- **Zipping and Unzipping a File**
  - Install `rar` and `unrar`:
    ```bash
    sudo apt-get install -y rar unrar
    ```
  - Zip a file:
    ```bash
    rar a archive_name.rar file1 file2
    ```
  - Unzip a file:
    ```bash
    unrar x archive_name.rar
    ```

- **Discover and Manipulate Memory Usage and Disk Space**
  - Check memory usage:
    ```bash
    top
    free -h
    ```
  - Check disk space:
    ```bash
    df -h
    du -sh /path/to/directory
    ```
  - Find services running on a specific port:
    ```bash
    sudo lsof -i :port_number
    ```

- **Connect to the Live Server through Local Machine**
  - Connect to MS-SQL server using `sqlcmd` from a local machine:
    ```bash
    sqlcmd -S server_ip -U username -P 'password'
    ```

- **Learn through SQL Server Management Studio (SSMS)**
  - Download and install SSMS on your local machine from [SSMS Download](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms).
  - Connect to the remote SQL Server instance using SSMS by providing the server IP, username, and password.

- **Run a Basic .NET Core Application on Linux**
  - Install .NET Core SDK:
    ```bash
    wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
    sudo dpkg -i packages-microsoft-prod.deb
    sudo apt-get update
    sudo apt-get install -y dotnet-sdk-7.0
    ```
  - Create and run a new .NET Core application:
    ```bash
    dotnet new console -o MyApp
    cd MyApp
    dotnet run
    ```

## Resources

- [MS-SQL Server on Linux Documentation](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-overview)
- [System Monitoring Commands](https://www.tecmint.com/command-line-tools-to-monitor-linux-performance/)
- [SQL Server Management Studio (SSMS) Documentation](https://docs.microsoft.com/en-us/sql/ssms/sql-server-management-studio-ssms)
- [.NET Core on Linux Documentation](https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu)

- # Week 4: Creating and Managing APIs with Node.js and AWS Lightsail

## Steps

### Creating Basic APIs with Node.js and Using Postman
- Set up a basic Node.js server using Express to create RESTful APIs.
- Use Postman to send requests to these APIs and verify their responses.

### Creating APIs for Uploading and Deleting Files in Lightsail Bucket
- **Uploading Files**: Create an API endpoint to upload files to an AWS Lightsail bucket using `multer` for handling file uploads and `aws-sdk` for interacting with AWS services.
- **Deleting Files**: Create an API endpoint to delete files from the Lightsail bucket using `aws-sdk`.

### Creating APIs for Creating and Deleting Folders in Lightsail Bucket
- **Creating Folders**: Develop an API to create folders in the Lightsail bucket by simulating folder creation through object keys in S3.
- **Deleting Folders**: Develop an API to delete folders by removing all objects within the specified folder in the bucket.

### Adding JWT Tokenization for Authentication
- Implement JWT (JSON Web Token) to secure your APIs. Generate tokens upon user authentication and validate these tokens for protected routes.

### Making a Backup Script for Daily Bucket Backup
- Write a script to back up your Lightsail bucket.
- Schedule this script to run daily at a specific time using `cron` jobs on your server.

# Week 5: AWS Lambda Setup and Deployment Guide

### 1. Creating a Lambda Function in AWS

- First, I navigate to the AWS Management Console and select the Lambda service.
- Next, I click on "Create function" and choose the "Author from scratch" option.
- I provide a function name, select the runtime environment (Node.js or .NET Core), and choose an existing role or create a new one with sufficient permissions.

### 2. Running Basic Node.js and .NET Code in the Function

- I write my Node.js or .NET Core code in the Lambda function's code editor.
- I ensure that my code handles event input and produces appropriate output.

### 3. Uploading a Zip File as Code in the Function

- If my codebase exceeds the Lambda function editor's size limit, I package my code into a zip file.
- I upload the zip file directly to the Lambda function creation wizard or update the existing function code via the console.

### 4. Using S3 Bucket Objects for Uploading Larger Zip Files

- First, I create an S3 bucket in the AWS Management Console if I haven't already.
- Then, I upload my zip file containing Lambda function code to the S3 bucket.
- I use the Lambda function creation wizard or AWS CLI to reference the S3 bucket object as the source for my function's code.

### 5. Testing It Through Various JSON Inputs

- I use the Lambda console to configure test events with different JSON payloads.
- I verify that my Lambda function handles each input correctly and produces expected outputs.

### 6. Making API Gateway and Setting Up Resource and Method

- First, I navigate to the API Gateway service in the AWS Management Console.
- I create a new API or select an existing one.
- Then, I define a resource and method that integrates with my Lambda function.
- I configure request and response mappings as needed.
- Finally, I deploy the API to a stage and test the integration using various HTTP methods and payloads.


This guide provides instructions for managing MS-SQL services, handling file compression, monitoring system resources, connecting to servers, and running .NET Core applications on Linux.
