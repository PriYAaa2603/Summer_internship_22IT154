# AWS Lightsail Instance Setup Guide

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

## Example Commands and Code Snippets

### Install Dependencies for Node.js Project
```bash
npm install express aws-sdk multer jsonwebtoken


This guide provides instructions for managing MS-SQL services, handling file compression, monitoring system resources, connecting to servers, and running .NET Core applications on Linux.
