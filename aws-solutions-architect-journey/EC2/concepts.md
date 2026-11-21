# EC2

## Concepts

### What is it?

Elastic Compute Cloud (EC2) is an Infrastructure as a Service (IaaS) offering that allows users to rent virtual machines on the AWS cloud. It provides scalable computing capacity and allows users to run applications without having to maintain physical servers.

EC2 works alongside other AWS services:
- **EC2:** Provides virtual machines (compute).
- **EBS:** Provides virtual block storage.
- **ELB:** Distributes incoming traffic across multiple instances.
- **ASG:** Automatically scales the number of instances based on demand.

### Why is it used?

Many a time, there comes a need for users to use an OS that is different from their native OS.

For example, a Windows user may need to work with a Linux OS, or a Linux user may need to work with a Windows environment.

Now, the user may either partition their disk to make room for a virtual machine or use a cloud platform to host the VM. Both local virtualisation and maintaining dedicated hardware can require considerable system resources.

In such cases, it becomes convenient for users to access an EC2 instance through AWS, without having to allocate their own computer's resources to run the virtual machine.

An **AMI (Amazon Machine Image)** contains the operating system, application server and applications or configurations required to launch an instance.

### How it works?

Go to EC2 and navigate to **Instances**.

**Launch the instance:**

1. Enter the name of the instance.

2. Choose the relevant AMI (Amazon Machine Image). Available options include Amazon Linux, macOS, Ubuntu, Windows, Red Hat, etc.

3. Choose the instance type (e.g., `t2.micro` or `t3.micro`, subject to Free Tier eligibility).

4. Enter a key pair value. This is needed to enable SSH authentication when connecting to the instance.

   The key pair configuration includes:
   - Key pair name
   - Key pair type (RSA or ED25519)
   - Private key file format (`.pem` or `.ppk`)

   The private key file gets downloaded and must be stored securely. It should never be shared or uploaded to GitHub.

5. Select appropriate network settings to allow SSH traffic, HTTPS traffic and HTTP traffic from the internet, wherever required.

   **Note:** SSH access should ideally be restricted to your own IP address instead of being allowed from anywhere.

6. Configure storage. By default, the root EBS volume is generally configured to be deleted when the EC2 instance is terminated, depending on the selected settings.

7. Under Advanced Details, navigate to **User Data** and enter the required code snippet.

   This code snippet is generally executed during the first boot of the instance. It can be used to automate initial configurations, install software and run setup commands, making the deployment process easier.
