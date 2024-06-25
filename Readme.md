# AWS Lightsail Instance Setup Guide

## Week 1

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
- [SQL Tutorial](https://www.w3schools.com/sql/)

This guide provides a streamlined process for setting up and managing an AWS Lightsail instance.
