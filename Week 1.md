# AWS Lightsail Instance Setup and Management

Here is a brief overview of the tasks performed by me in Week 1.

- **Creating an AWS Free Tier Account and Logging In**
  - Sign up for an AWS Free Tier account at [AWS Free Tier](https://aws.amazon.com/free).
  - Follow the instructions to complete the registration process.
  - Log in to the AWS Management Console.

- **Creating a Lightsail Instance and Selecting Linux as the OS**
  - Navigate to the AWS Lightsail service in the AWS Management Console.
  - Click on "Create instance".
  - Choose "Linux/Unix" as the operating system.
  - Select the instance plan (the free tier option is available).
  - Provide a name for your instance and click "Create".

- **Connecting to the SSH Shell**
  - After the instance is created, go to the Lightsail dashboard.
  - Click on the instance to open its management page.
  - Click on the "Connect using SSH" button to open the web-based SSH client.

- **Learning About the Networking, Storage, and Other Aspects of an Instance**
  - **Networking**:
    - Explore the Networking tab to configure static IPs, DNS, and firewalls.
    - Understand inbound and outbound rules and how to manage them.
  - **Storage**:
    - Check the attached disks in the Storage tab.
    - Learn to attach/detach and manage additional storage volumes.
  - **Monitoring**:
    - Use the metrics and monitoring tools to track the performance of your instance.

- **Implementing Basic Linux Commands on the Server**
  - Run basic commands to navigate and manage your server:
    ```bash
    # Update package lists
    sudo apt-get update
    
    # Install a package
    sudo apt-get install -y package-name
    
    # Check disk space
    df -h
    
    # List files in a directory
    ls -la
    
    # Check running processes
    top
    ```

- **Building a Snapshot of the Instance**
  - Go to the Lightsail instance management page.
  - Click on the "Snapshots" tab.
  - Click "Create snapshot" to take a snapshot of your instance.
  - Provide a name for the snapshot and confirm the creation.
  - Use snapshots to restore the instance or create new instances with the same configuration.

## Additional Resources

- [AWS Lightsail Documentation](https://docs.aws.amazon.com/lightsail/index.html)
- [Basic Linux Commands](https://www.tutorialspoint.com/unix/unix-useful-commands.htm)
- [SSH Access Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

This README file provides a step-by-step guide to setting up and managing an AWS Lightsail instance. Follow each step carefully to ensure successful implementation.
