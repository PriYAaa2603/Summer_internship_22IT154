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

This guide provides a streamlined process for setting up and managing an AWS Lightsail instance.
