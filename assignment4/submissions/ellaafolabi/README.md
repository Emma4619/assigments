## My name is Emmanuella and please file below my submission


# Learning and Experience
Use this section to record you key learnings over the week. This section is very important as it is from here that we will build your profile for your CV for work 

1.   Collaboration: Learned effective teamwork and leveraging individual strengths.
2.   Communication: Enhanced verbal and written communication skills.
3.   Automation/CICD: Explored automation and Continuous Integration/Continuous Deployment practices.
4.   AWS: Developed proficiency in Amazon Web Services (AWS) and its services.
5.   Kubernetes: Mastered container orchestration with Kubernetes.
6.   Terraform: Became proficient in infrastructure as code using Terraform.
7.   Linux: Expanded knowledge of Linux commands and system administration tasks.
8.   System and Application Design: Developed skills in designing scalable and reliable systems.
9.   Productivity: Focused on improving personal productivity and time management.
10.     Self-Development: Explored personal abilities and worked on continuous self-improvement.

## Kubernetes, Docker, Containerisation and Virtualisation

With respect to Kubernetes define what the following entities mean.

1. Pod: A pod is the smallest and most basic unit of deployment in Kubernetes. It represents a group of one or more containers that are tightly coupled and share the same network namespace, IP address, and storage resources. Pods are used to run and manage containers within a Kubernetes cluster.

2. Container: A container is a lightweight, standalone executable software package that includes everything needed to run an application, including the code, runtime, system tools, libraries, and settings. In the context of Kubernetes, containers are used to encapsulate and deploy applications within pods. Kubernetes manages the lifecycle of containers, including their creation, scaling, and termination.

3. Node: A node, also known as a worker node or minion, is a physical or virtual machine that runs the Kubernetes software and hosts pods. Nodes are responsible for running containers and providing the necessary resources, such as CPU, memory, and storage, to execute the workloads deployed in the cluster. Each node has a unique identifier and can be part of a larger cluster.

4. Control Plane: The control plane, also referred to as the master node or the control plane node, is responsible for managing the Kubernetes cluster. It consists of several components, including the API server, etcd (a distributed key-value store), scheduler, and controller manager. The control plane oversees the overall cluster state, handles workload scheduling, manages scaling, and enforces desired configurations and policies.

5. Data Plane: The data plane, also known as the worker plane, is responsible for handling the actual data traffic and workload execution within the Kubernetes cluster. It comprises the nodes (worker nodes) where containers and pods are scheduled and executed. The data plane receives instructions from the control plane and ensures that the desired state of the cluster is maintained by managing the running containers and pods.

## Linux administration and shell scripting

1. You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that?

Check the script's permissions: Use the ls -l command to view the file permissions. Ensure that the script has the execute permission set for the user running the script. If the permission is not set, you can use the chmod command to add the execute permission. For example, chmod +x addAccount.sh grants execute permission to the owner of the file.

Run the script using an elevated user: If you don't have the necessary permissions to execute the script, try running it with elevated privileges using sudo. For example, sudo ./addAccount.sh will execute the script with root permissions. You may need to provide your password to authorize the elevated access.

Check the script's shebang: Ensure that the script has the correct shebang (#!/bin/bash or #!/bin/sh) at the beginning of the file. This shebang specifies the interpreter to use when executing the script. If the shebang is missing or incorrect, the script may fail to run.

Check the script's location: Make sure you are running the script from the correct directory. If the script is not in your current directory, provide the full path to the script when executing it. For example, ./path/to/addAccount.sh.

Verify file ownership and permissions: Ensure that you have read and execute permissions on the script file. Use the ls -l command to view the ownership and permissions. If necessary, you can change the ownership or permissions using chown and chmod respectively.

Check for any dependencies: If the script relies on external programs or dependencies, ensure that they are installed and accessible. If any dependencies are missing, you may need to install them or adjust the script to work without them.

2. What Linux command would your use to find out what commands you have run in the past?

The Linux command that you can use to find out the commands you have run in the past is history. The history command displays a list of previously executed commands from your command-line shell history.

3. Research the following Linux commands

1. chmod:
The chmod command is used to change the permissions (read, write, execute) of files and directories in Linux. It allows you to control access to files and determine which users or groups can perform specific actions on them. The basic syntax of the chmod command is as follows:

chmod [options] mode file(s)
Here, "mode" represents the permissions you want to set, and "file(s)" specifies the file(s) or directory to which you want to apply the permissions. The permissions can be specified using numeric mode (e.g., 644) or symbolic mode (e.g., u=rw,go=r).

2. scp:
The scp command (Secure Copy) is used to securely transfer files between local and remote hosts over an SSH connection. It provides a secure alternative to the cp command when copying files between different systems. The basic syntax of the scp command is as follows:

scp [options] source_file(s) destination
Here, "source_file(s)" refers to the file(s) you want to copy, and "destination" specifies the location where you want to copy the file(s) to. The source and destination can be specified using local paths or in the format [user@]host:file. For example, to copy a file from a local system to a remote server:

scp file.txt user@remote:/path/to/destination/
scp uses the SSH protocol for encryption and authentication, ensuring secure file transfers.

3. ssh:
The ssh command (Secure Shell) is used to establish a secure encrypted connection to a remote server or system. It provides a secure way to access and manage remote machines over an unsecured network. The basic syntax of the ssh command is as follows:

ssh [options] [user@]host

Here, "user" represents the username you want to log in as (optional if the same as the local username), and "host" specifies the hostname or IP address of the remote server. Upon successful connection, ssh opens a secure shell session, allowing you to execute commands on the remote system as if you were logged in locally.

The ssh command also supports various options for configuring the connection, such as specifying a different port, using SSH keys for authentication, creating SSH tunnels, and more.

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

1. You want to use the following code to created an AWS EKS resource from the public repository pointed to by the source clause. How could you ensure that any changes made to the public repository you are pointing to does not adversely affect your infrastructure?
module "myeks" {
   source = "terraform-aws-modules/terraform-aws-eks"
   cluster_name = "mycluster"
}

Lock the module version to a specific version.
Perform thorough testing in a non-production environment.
Monitor the public repository for updates and review changelogs.
Establish a change management process for approving modifications.
Utilize version control for your infrastructure code.
Optionally, consider forking the module for more control.

2. When you run the terraform init command in the directory containing Terraform files, it initializes the directory for use with Terraform. It downloads the necessary provider plugins and sets up the backend configuration specified in the Terraform files. It creates a hidden directory called .terraform that contains the downloaded plugins and other initialization files.

3. The purpose of a Terraform provider is to interact with a specific infrastructure platform or service, such as AWS, Azure, or Google Cloud. Providers are responsible for translating Terraform configurations into API calls to provision and manage resources in the target infrastructure. They handle authentication, resource creation, updates, and deletions.

4. The purpose of Terraform state is to store the current state of the infrastructure managed by Terraform. It keeps track of the resources defined in the Terraform configuration, their attributes, and metadata. The state file is used by Terraform to create an execution plan, determine resource dependencies, and perform updates and deletions. It serves as the source of truth for Terraform to understand the current state of the infrastructure.

5. To ensure the security and integrity of the Terraform state in a collaborative environment, you can implement the following practices:

Store the state file in a secure and centralized location, such as an S3 bucket or a remote backend.
Enable state file locking to prevent concurrent modifications and conflicts. This can be done using a distributed locking mechanism provided by the backend or using a tool like DynamoDB for locking.
Implement version control for the Terraform code and state file to track changes and allow for easy collaboration and rollbacks.
Apply proper access controls and permissions to the state file, allowing only authorized users or automation systems to read and modify it.
Educate team members on the importance of not modifying resources outside of Terraform and following the established Terraform workflow to maintain consistency.
6. If you run the terraform apply command after a colleague has made changes to the resource on the AWS console, Terraform will detect that the actual resource configuration no longer matches the expected state defined in the Terraform configuration. It will attempt to reconcile the differences by applying the changes specified in the Terraform configuration. However, it may fail if there are conflicts between the changes made on the AWS console and the changes defined in the Terraform configuration. In such cases, Terraform will display an error message and provide instructions on how to resolve the conflicts.

7. To delete the unwanted resource without deleting the other resources defined in the Terraform file, you can modify the Terraform configuration by removing the resource definition for the unwanted resource. Then, run the terraform apply command to apply the updated configuration. Terraform will detect the removal of the resource from the configuration and initiate the deletion process for that specific resource while leaving the other resources intact.

8. A Terraform backend is responsible for storing the state file and managing state-related operations. It can be a local or remote system where the state file is stored. A backend allows for collaboration, state locking, and remote storage of the state file. It provides features like versioning, encryption, and access controls. The backend is configured in the Terraform code using a backend block, specifying the backend type and the necessary configuration parameters.

9. Terraform can obtain credentials for authentication to an endpoint through various methods:

Environment variables: Credentials can be set as environment variables, such as AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY for AWS.
Shared credentials file: Terraform can use the credentials stored in a shared file, such as the ~/.aws/credentials file for AWS.
Instance metadata: When running Terraform on an AWS EC2 instance, it can automatically retrieve credentials from the instance metadata service.
Provider-specific methods: Some providers may have their own methods for obtaining credentials, such as configuration files or specific environment variables.
10. To ensure that external module dependencies are resolved before provisioning resources, you need to run the terraform init command in the directory containing your Terraform configuration. This command downloads the necessary provider plugins and resolves any module dependencies specified in your code. It ensures that all required modules and their versions are available locally, allowing Terraform to provision resources correctly.

11. To check the resources created using Terraform, you can query the state file. You can use the terraform show command to display the current state of your infrastructure. It provides detailed information about the resources, their attributes, and their current configuration as stored in the state file.

12. The recommended approach for editing the Terraform state is to make changes through Terraform itself by modifying the Terraform configuration files. Directly editing the state file can lead to inconsistencies between the state file and the actual infrastructure, causing issues during future Terraform operations. It is best to use Terraform commands like terraform apply or terraform destroy to modify the infrastructure and let Terraform handle the state management automatically.

13. The provided Terraform code configures the backend for storing the Terraform state in an S3 bucket named "techoutcomes-terraforms.tfstate" in the "eu-west-1" region. It specifies the bucket name, the key (filename) for the state file, and the region where the bucket is located. This configuration enables Terraform to store and retrieve the state file from the specified S3 bucket.

14. The provided code defines an AWS provider block specifying that the provider configuration should use the value of the local.region variable for the AWS region. It indicates that the region where AWS resources will be provisioned is determined by the value of the local.region variable.

15. Locking the Terraform state file means preventing concurrent modifications to the state file by multiple users or processes. It is important to implement a locking mechanism for the state file to prevent conflicts and ensure that only one Terraform operation can modify the state at a time. This helps maintain consistency and avoids race conditions where multiple operations attempt to modify the state simultaneously.

16. Detailed explanations of each Terraform command:
a) terraform init: Initializes the Terraform working directory, downloads provider plugins, and sets up the backend configuration.
b) terraform apply --auto-approve: Applies the Terraform configuration and provisions or modifies the resources as necessary. The --auto-approve flag skips the confirmation prompt and automatically approves the execution.
c) terraform fmt: Formats the Terraform configuration files to follow the standard style and indentation.
d) terraform validate: Validates the syntax and configuration of the Terraform files, checking for errors and warnings.
e) terraform destroy: Destroys all resources defined in the Terraform configuration, releasing the allocated resources and cleaning up the infrastructure.

17. To ensure that a file is recognized by Terraform when running terraform plan or terraform apply, you need to name the file with a .tf extension. Terraform recognizes files with this extension as configuration files and includes them in its execution.

18. The purpose of the Terraform plan command is to generate an execution plan that shows the proposed changes to the infrastructure. It compares the current state (as stored in the state file) with the desired state (as defined in the Terraform configuration) and provides a detailed overview of what resources will be created, modified, or destroyed. It is important to carefully read the output of the plan to understand the impact of the changes before applying them to the infrastructure.

19. The Terraform concept used to ensure code reusability is called modules. Modules are self-contained units of Terraform configurations that can be used to create and manage resources. They encapsulate a set of resources with defined inputs and outputs, allowing them to be reused across different environments or projects. Modules promote code organization, modularity, and maintainability by providing a way to abstract and encapsulate common infrastructure patterns.

20. To create different environments (dev, test, production) from a single directory, you can organize your file and directory system as follows:

Create separate directories for each environment (e.g., dev/, test/, production/).
Place the main Terraform configuration files (main.tf, variables.tf, etc.) in the root directory.
Create environment-specific directories and place environment-specific configuration files in each directory.
Use Terraform workspaces or input variables to differentiate between environments and load environment-specific configurations.
21. Terraform partial backend configuration refers to specifying only a subset of the required backend configuration options, leaving the rest to be filled in at runtime. This allows flexibility in configuring the backend and enables dynamic or environment-specific configuration values to be provided during execution.

22. The "Chicken-and-Egg" problem in Terraform backend configuration refers to the challenge of configuring the backend when the backend itself depends on the infrastructure provisioned by Terraform. For example, if the backend is an S3 bucket, Terraform needs to create the bucket, but it requires a backend configuration to store the state file in the bucket. This problem is typically solved by using a separate initial state backend or manual steps to create the initial bucket before configuring the backend.

23. To use the "terraform-aws-modules/ec2-instance/aws" public module, you need to provide some interface values to create the module. These values may include:

name: A name for the EC2 instance.
instance_type: The EC2 instance type to be launched.
vpc_id: The ID of the VPC where the EC2 instance should be deployed.
subnet_id: The ID of the subnet where the EC2 instance should be deployed.
security_group_ids: A list of security group IDs to associate with the EC2 instance.
key_name: The name of the key pair to associate with the EC2 instance for SSH access.
tags: Optional tags to assign to the EC2 instance.

## System Architecture and Application Design, Cloud Computing (AWS)

1. You have an application running on one server in the cloud serving requests from customers. There is a sudden increase in request from customers reaching the application and a lot of requests are failing or are extremely slow.
Draw a diagram showing this architecture.
How could you re-architect the application to allow it to handle more request?
Draw a diagram of the new design.

Diagram of the initial architecture:

lua
Copy code
        +-------------------+
        |   Customer        |
        +-------------------+
                  |
                  |
        +-------------------+
        |   Cloud Server    |
        +-------------------+
                  |
                  |
        +-------------------+
        |   Application     |
        +-------------------+
        |   Database        |
        +-------------------+
To re-architect the application to handle more requests, you can introduce scalability and load balancing. Here's an example of a new design:

lua
Copy code
        +-------------------+
        |   Customer        |
        +-------------------+
                  |
                  |
        +-------------------+
        |   Load Balancer   |
        +-------------------+
                  |
        +---------+---------+
        |                   |
        |     Cloud Server 1|
        |                   |
        +-------------------+
        |                   |
        |     Cloud Server 2|
        |                   |
        +-------------------+
        |                   |
        |     Cloud Server 3|
        |                   |
        +-------------------+
                  |
                  |
        +-------------------+
        |   Application     |
        +-------------------+
        |   Database        |
        +-------------------+
In the re-architected design:

A load balancer is introduced to distribute incoming requests across multiple cloud servers.
Multiple cloud servers are added to handle the increased request load. Each server runs a copy of the application.
The load balancer intelligently distributes requests among the cloud servers, ensuring a balanced workload.
The database remains in the backend to store and retrieve data for the application.
This design allows for horizontal scaling, where additional cloud servers can be added or removed dynamically based on demand. It helps increase the application's capacity to handle more requests by distributing the load effectively across multiple servers.

2. To enable SSH access from your local laptop to an AWS server:

On your local laptop:

Install an SSH client (e.g., OpenSSH).
Generate an SSH key pair (public and private key).
Copy the public key to the AWS server.
On the AWS cloud:

Launch an EC2 instance and specify the key pair during the launch.
Configure the security group to allow incoming SSH traffic from your IP.
SSH into the EC2 instance using the private key.
The database in business system design:

3. The database serves as a central repository for storing and managing critical business data.
To ensure database resilience and high availability:
Implement database replication for redundancy.
Regularly backup the database and test the restoration process.
Configure high availability mechanisms like failover clustering.
Monitor and optimize database performance.
Create a disaster recovery plan.

4. Three-tier architecture:

It separates an application into three layers: presentation, application, and data.
The presentation layer handles the user interface and is typically exposed to the internet.
The application layer contains the business logic and processing.
The data layer stores and manages the application data.

5. 
To create an EC2 instance in your AWS account:

Log in to the AWS Management Console.
Open the EC2 service.
Launch an instance using the desired Amazon Linux AMI and Free Tier-eligible instance type.
Configure instance details, storage, and security groups.
Review and launch the instance.
To log onto the EC2 instance from your local machine:

Use the ssh command with the private key file and the instance's public IP.
Example: ssh -i /path/to/private_key.pem ec2-user@<public_ip>
To copy a file from your local machine onto the EC2 instance:

Use the scp command with the private key file and file paths.
Example: scp -i /path/to/private_key.pem /path/to/local_file ec2-user@<public_ip>:/path/on/instance
To allow someone else to log onto your server:

Share the instance's public IP and the private key file securely.
Instruct them to use the SSH command with the private key to connect.

6. A bastion server, also known as a jump server or a bastion host, is a specially configured server that acts as an intermediary between the external network (such as the internet) and the internal network of a secure infrastructure. It is required in some network architectures to provide a controlled and secure access point to the internal network. The bastion server acts as a gateway, allowing authorized users to connect to the internal network while implementing security measures like access controls, monitoring, and auditing.

7. In terms of accessibility:

A Public IP is a globally unique address assigned to a device connected to a public network, such as the internet. It allows the device to be accessible from anywhere on the internet. Public IPs are used for communication with external networks and are necessary for services that need to be publicly accessible.
A Private IP is an address assigned to a device within a private network. It is not directly accessible from the internet. Private IPs are used for communication within a private network and are not globally routable. They provide internal connectivity between devices within the network and are typically used for security and privacy reasons.
8. At a high level, the SSH (Secure Shell) system works as follows:
The client initiates an SSH connection request to the server.
The server responds and initiates a secure cryptographic handshake with the client.
The client and server negotiate encryption algorithms, exchange cryptographic keys, and establish a secure channel.
Once the secure channel is established, the client and server can securely exchange encrypted data, including commands, file transfers, and terminal sessions.
The SSH system ensures confidentiality, integrity, and authenticity of the communication, protecting against eavesdropping, tampering, and spoofing.
9. When you create a key pair on AWS, the public key and the corresponding private key are generated. The public key is stored on the AWS infrastructure, while the private key is provided to you for download. AWS retains the public key, and it is used for cryptographic operations like encrypting credentials or verifying signatures when you interact with AWS services securely.

10. When you create an EC2 instance on AWS, a network interface is also created and assigned a Private IP address. This private IP is important because it allows the EC2 instance to communicate with other resources within the same private network or Virtual Private Cloud (VPC). The private IP facilitates internal network communication, including traffic between instances, load balancers, databases, and other services within the VPC. It is used for secure and efficient communication within the isolated network environment without exposing the instance directly to the public internet.

## Site Reliability Engineering (SRE), Troubleshooting, Observability

1. Site Reliability Engineering (SRE): SRE is an approach that combines software engineering and operations to build and maintain highly reliable and scalable systems. It focuses on automation, monitoring, incident response, and performance optimization to ensure the reliability of services.

Troubleshooting: Troubleshooting is the process of identifying and resolving issues or problems in a system. It involves investigating symptoms, diagnosing root causes, and applying solutions to restore normal system operation.

Observability: Observability refers to the ability to understand and gain insights into the internal state and behavior of a system based on its external outputs. It involves collecting and analyzing various metrics, logs, and traces to gain visibility into system performance, errors, and dependencies.

## DevOps and Agile Transformation principles and methodology

1. DevOps and Agile Transformation involve streamlining software development and delivery processes. 

2. Key principles/methodologies:

Collaboration and Communication: Promote teamwork and effective communication.
Automation: Automate tasks for efficiency and faster delivery.
CI/CD: Continuously integrate, test, and deliver code.
Infrastructure as Code (IaC): Manage infrastructure through code.
Monitoring and Feedback: Monitor, gather feedback, and improve performance.

3. Agile Transformation:

Agile Manifesto: Embrace values like customer collaboration and iterative development.

4. Scrum: Use roles, artifacts, and ceremonies to manage work.
Kanban: Visualize workflow and optimize task flow.
Empowered Teams: Encourage self-organizing, cross-functional teams.
Continuous Improvement: Foster a culture of learning and growth.
DevOps + Agile = Efficient, collaborative, customer-centric software development.

## New commands logs - Enter up to ten new commands you have learnt this week

| Number      | Commands | What does it do and how might you check its effect     |
| :---        |    :----:   | :---  |
| 1  | ls             | Lists files and directories   |
| 2  | pwd            | Prints the current working directory   |
| 3  | cd             |  Changes the current directory   |
| 4  | mkdir          | Creates a new directory   |
| 5  | cp             | Copies files or directories   |
| 6  | rm             | Removes files or directories   |
| 7  | mv             | Moves or renames files or directories   |
| 8  | cat            | Displays the contents of a file   |
| 9  | grep           | Searches for a pattern in files   |
| 10 | chod           | Changes file permissions   |

## Glossary of the week - Enter new technical words you have learnt this week and their meanings.

| Number   | Word | Meaning     |
| :---     | :----:   |  :---  |
| 1  | Containerization       | Encapsulating applications and dependencies into self-contained units known as containers for consistent deployment   |
| 2  | Microservices    | Architectural approach dividing applications into smaller, independent services for easier development and scalability   |
| 3  | API              | (Application Programming Interface) - Set of rules enabling different software applications to communicate and interact.   |
| 4  | DevOps           | Methodology combining development and operations for collaboration, automation, and continuous delivery.   |
| 5  | CI/CD            | (Continuous Integration/Continuous Deployment) - Practices and tools for automated code integration, testing, and deployment.   |
| 6  | Serverless Computing | Cloud model where providers manage infrastructure, allowing developers to focus on code.   |
| 7  | Machine Learning | Subset of AI training systems to learn from data and make predictions or take actions.   |
| 8  | Big Data         | Refers to large and complex datasets requiring specialized processing and analysis techniques.   |
| 9  | Orchestration         | Coordination and automation of multiple systems, services, or processes to achieve desired outcomes.   |
| 10 | Continuous Monitoring | Ongoing monitoring of systems and applications to ensure performance, availability, and security.   |
