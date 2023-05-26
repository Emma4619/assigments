## My name is emmaafolabi and please find below my submission. I collaborated with Oluwafunbi.

## Kubernetes, Docker, Containerisation and Virtualisation

1. Both containers and virtual machines have their strengths and weaknesses, and the choice between them depends on specific use cases, application requirements, and the infrastructure environment.

Advantages of Containers:
Containers are more lightweight compared to virtual machines, as they share the host operating system's kernel. This results in faster startup times and efficient resource utilization.
Containers encapsulate the application and its dependencies, making them highly portable across different environments. They can be easily moved between development, testing, and production environments.

Disadvantages of Containers:
Containers rely on the host operating system's kernel, so they are limited to running on compatible operating systems. This can be a constraint if you need to run applications that require specific OS versions or features not available on the host.

Advantages of Virtual Machines:
Virtual machines offer complete isolation since they run on a virtualized hardware layer. Each virtual machine has its own operating system and resources, providing a high level of security and independence.
Virtual machines can run different operating systems, allowing you to deploy applications that require specific OS environments or configurations. This flexibility is useful when dealing with legacy applications or diverse software requirements.

Disadvantages of Virtual Machines:
Each virtual machine requires its own operating system, consuming additional resources such as CPU, memory, and storage. This overhead can be relatively high compared to containers, resulting in less efficient resource utilization.
Virtual machines take longer to start compared to containers because they need to boot an entire operating system. This slower startup time can impact scalability and agility in certain scenarios.

Docker image is like a snapshot or a template that contains everything needed to run an application, including the code, dependencies, libraries, and system configurations. It is a standalone package that can be used to create and run containers.

Docker images are created through a process called "Docker image build." Here's a simplified explanation of how Docker images are created:

Dockerfile: The creation of a Docker image starts with a text file called a Dockerfile. The Dockerfile contains a set of instructions that specify how the image should be built. It defines the base image, sets up the environment, installs dependencies, and copies the application code.

Building the Image: Once the Dockerfile is ready, you use the Docker command-line tool to build the image. The Docker engine reads the Dockerfile and executes each instruction step by step. It pulls the necessary base image, applies the instructions in the Dockerfile, and creates a new image layer for each instruction.

Caching: Docker uses a layer-based approach, which means that each instruction in the Dockerfile creates a new layer. If an instruction hasn't changed since the previous build, Docker can use the cached layer, which speeds up subsequent builds. This caching mechanism improves the efficiency of building and sharing Docker images.

Tagging and Publishing: After the image is built, you can assign a tag to it, which is like a version or a label for the image. Tags help identify and differentiate different versions of the same image. You can also publish the image to a container registry like Docker Hub or a private registry, making it accessible to others.

Docker container is a lightweight, isolated, and executable environment that encapsulates an application and all its dependencies. It allows applications to run consistently across different systems, providing portability and reproducibility.

To run a Docker container, you need to follow these steps:
Obtain a Docker Image: Docker containers are created from Docker images. You can either build your own Docker image using a Dockerfile or use an existing image from a public or private container registry like Docker Hub.

Run the Container: Using the Docker command-line tool, you can run a container based on the Docker image. The command typically looks like this:

docker run <image-name>

Replace <image-name> with the name or ID of the Docker image you want to run. Docker will automatically download the image if it's not available locally.

Container Execution: When you run a Docker container, it starts an isolated instance of the application defined in the image. It runs in its own namespace, with its own file system, network, and process environment. You can interact with the container through the command line or access the application within the container through network ports.

Container Lifecycle: Containers can run in the foreground, providing real-time logs and outputs, or in the background as detached processes. They can be stopped, started, and restarted as needed. Once a container is stopped, it retains its state and can be restarted later with the same state intact.

Container Management: Docker provides various commands to manage containers. For example, you can list running containers, view container logs, execute commands within a container, or remove containers when they are no longer needed.

## Linux administration and shell scripting

Write a shell script that takes a single input arguments and echoes it back when it is run.

1. #!/bin/bash

# Check if an argument is provided
if [ $# -eq 0 ]; then
  echo "No argument provided."
  exit 1
fi

# Echo the provided argument
echo "You entered: $1"

Save the above script in a file with a ".sh" extension (e.g., echo_argument.sh). Then, make the script executable by running the following command in the terminal:

chmod +x echo_argument.sh

To use the script, pass an argument when executing it:

./echo_argument.sh Hello World

The script will then echo back the argument:

You entered: Hello

Write a shell script that creates a directory call "sports" and inside the "sports" directory create two other subdirectories called "football" and "handball". You should be able to run the script multiple times without it failing.

#!/bin/bash

# Create the "sports" directory if it doesn't exist
if [ ! -d "sports" ]; then
  mkdir sports
  echo "Created 'sports' directory."
fi

# Create the "football" directory if it doesn't exist
if [ ! -d "sports/football" ]; then
  mkdir sports/football
  echo "Created 'football' directory."
fi

# Create the "handball" directory if it doesn't exist
if [ ! -d "sports/handball" ]; then
  mkdir sports/handball
  echo "Created 'handball' directory."
fi

Save the script in a file with a ".sh" extension (e.g., create_sports_directories.sh). Make the script executable by running the command:

To run the script, execute the following command:
./create_sports_directories.sh

Copy the code below into a file called hello.sh and run it. Explain the behaviour.

The user navigates to the technologiesoutcomes directory using the cd command. The user creates a file named hello.sh using the Vim editor by running the vim hello.sh command.
The user enters the provided script content in the Vim editor, which is a simple Bash script that greets each command-line argument passed to it.

The user saves and exits the Vim editor.
The user sets the executable permission for the hello.sh script using the chmod +x hello.sh command.

The user checks the contents of the current directory using the ls -l command.
The output shows the hello.sh script file along with other directories and files.
The hello.sh script file has the executable permission (-rwxr-xr-x).

Copy the script below into a file called addme.sh and analyse it line by line. Run it and describe in details the behavior.

The script addme.sh is a simple telephone list program implemented in Bash. It allows users to add phone numbers to a list and retrieve phone numbers from the list. Here's a summary of its behavior:

If no command-line parameters are provided, it prompts the user to specify whose phone number they want and exits.
If the first command-line parameter is "new", it prompts for a name and number, adds them to the phone list, displays a success message, and exits.
If the phone list file is empty, it displays a message indicating that there are no names in the list and exits.
If a name is provided as a command-line parameter, it searches for the name (case-insensitive) in the phone list.
If the name is found, it displays the corresponding phone number.
If the name is not found, it displays a message indicating that the name was not found in the list and exits.
The script uses the ~/.phonelist.txt file as the storage location for the phone list.
To run the script, save it as addme.sh, make it executable (chmod +x addme.sh), and run it with the desired parameters as described in the script's comments.

Create a script that reads in three positional parameters from the command line, assigns those parameters to variables names ONE, TWO, and THREE, respectively, and then outputs that information in the following format: There are X parameters that include Y. The first is A, the second is B, the third is C. Replace X with the number of parameters and Y with all parameters entered. Then replace A with the contents of variable ONE, B with variable TWO, and C with variable THREE.

#!/bin/bash

ONE=$1
TWO=$2
THREE=$3

count=$#
parameters=$*

echo "There are $count parameters that include $parameters."
echo "The first is $ONE, the second is $TWO, the third is $THREE."

Here's how the script works:

The positional parameters $1, $2, and $3 are assigned to variables ONE, TWO, and THREE, respectively.
The variable count is assigned the value of $#, which represents the number of positional parameters.
The variable parameters is assigned the value of $*, which represents all the positional parameters entered.
The script outputs the desired information using echo statements, replacing the placeholders with the appropriate variables.

To run the script, save it as a file (e.g., parameter_info.sh), make it executable (chmod +x parameter_info.sh), and run it with three positional parameters:

./parameter_info.sh value1 value2 value3

## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

What do you understand by the term Idempotence?

Idempotence means that applying an operation multiple times produces the same result as applying it once.

What are the benefits of adopting a DevOps way of working for an organisation?
Improved collaboration and communication.
Faster and more frequent software delivery.
Enhanced software quality and reliability.
Increased stability and uptime.
Scalability and flexibility.
Enhanced security and compliance.
Empowered teams and culture of innovation.

What are the benefits of provisioning infrastructure using tools like Terraform and Ansible?
Infrastructure as Code: Enables version control, documentation, and reproducibility.
Automation and Efficiency: Reduces manual effort and eliminates human error.
Infrastructure Consistency: Ensures standardized and repeatable configurations.
Scalability and Flexibility: Supports dynamic provisioning and resource scaling.
Infrastructure Orchestration: Manages complex setups and interdependencies.
Cloud-agnosticism and Multi-Cloud Support: Works across multiple cloud providers.

Some provisioning and configuration management tools require the installation of agents on managed servers. Can you list the advantages and disadvantages of tools based on agents?

Advantages of provisioning and configuration management tools based on agents:
Granular control and management of individual servers
Real-time monitoring capabilities
Offline management and configuration
Secure communication with encryption
Customization and extensibility options

Disadvantages of provisioning and configuration management tools based on agents:
Time-consuming agent installation and maintenance
Resource consumption on managed servers
Potential security risks and vulnerabilities
Compatibility and dependency challenges
Ongoing agent maintenance and updates required

Compare and contrast mutable and immutable infrastructures design paradigms.
Mutable Infrastructure:
Servers and components are modified and updated in-place.
Changes are applied directly to existing infrastructure.
Configuration drift and inconsistencies can occur.

Servers and components are treated as disposable and not modified once deployed.
Infrastructure is created as immutable artifacts.
Updates are made by creating new instances with updated configurations.
Infrastructure is immutable and stateless, ensuring consistency.

Comparison:
Mutable: Updates in-place, configuration drift, managing server state.
Immutable: New instances, consistency, statelessness, recreating from a known state.
Contrast:

Mutable: Direct modification, configuration drift, long-lived server state.
Immutable: Instance replacement, consistency, disposable and stateless servers.

Name some commercial and enterprise tools and the circumstances under which you would recommend them.
AWS: Scalable and flexible cloud services for various infrastructure needs.
Azure: Integration with Microsoft technologies and comprehensive cloud services.
Google Cloud Platform (GCP): Advanced machine learning and data processing capabilities.
VMware: Virtualization and cloud solutions for efficient infrastructure management.
Ansible: Agentless configuration management and automation across environments.
Puppet: Centralized management and orchestration of complex infrastructures.
Chef: Infrastructure automation and configuration management with focus on infrastructure-as-code.
Terraform: Declarative infrastructure provisioning and management for multi-cloud environments.
Jenkins: Customizable CI/CD workflows and integrations for automated software delivery.
Splunk: Data analytics and monitoring platform for insights from machine-generated data.

What do you understand by imperative and declarative way of provisioning infrastructure?

Imperative Provisioning:
Infrastructure is provisioned by specifying explicit instructions and steps.
Focuses on the specific actions and commands required.
Requires manual definition of each provisioning step.

Infrastructure is provisioned by specifying the desired end state.
Focuses on the desired configuration and properties.
The provisioning tool determines and executes the necessary steps.
Promotes idempotent operations and consistency.
Examples: Terraform, AWS CloudFormation, declarative mode of Puppet and Chef.

Describe the role that GitHub Actions plays in a fully automated CICD integrated toolchain?
GitHub Actions is a vital component of a fully automated CI/CD integrated toolchain. It enables developers to automate CI/CD workflows by defining custom workflows that build, test, and deploy code changes. It offers flexibility, scalability, and integration with various tools and services. GitHub Actions promotes collaboration, provides visibility into the CI/CD process, and supports workflow automation across multiple repositories. It plays a crucial role in streamlining software development processes and facilitating continuous integration and deployment.

What is a Runner in the context of a provisioning pipeline?
In summary, a Runner is an agent or machine responsible for executing tasks in a provisioning pipeline. It pulls pipeline configurations, performs the defined actions, and communicates with the CI/CD platform. Runners can be self-hosted or provided by the platform, and they enable parallel execution, resource configuration, and efficient pipeline execution. They play a crucial role in executing and orchestrating the provisioning pipeline.

What GitHub Action code syntax would you implement to trigger a GitHub Action workflow upon a pull request on a codebase?

name: Pull Request Workflow
on:
  pull_request:
    types:
      - opened
      - synchronize

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      # Perform actions or tasks as needed
      - name: Checkout code
        uses: actions/checkout@v2

      # Add more steps as required
      - name: Build and Test
        run: |
          # Build and test commands here

In the context of GitHub Actions, what are actions and where might you obtain them?

GitHub Actions are reusable and configurable units of work that perform specific tasks within workflows. They can be obtained from GitHub Marketplace, community repositories, or created by your organization. Actions allow you to automate tasks such as building, testing, and deploying code, enhancing the flexibility and efficiency of your workflows.

## System Architecture and Application Design, Cloud Computing (AWS)

Draw a solution architecture diagram illustrating the flow of information in a provisioning pipeline comprising AWS, GitHub, your laptop, Terraform and Terraform state file stored in AWS.

Local Laptop         GitHub                AWS
     |                   |                    |
     |   git push        |                    |
     | --------------->  |                    |
     |                   |                    |
     |   GitHub Webhook  |                    |
     | <---------------- |                    |
     |                   |                    |
     |   Terraform       |                    |
     | --------------->  |                    |
     |                   |    Terraform       |
     |                   |  State File (S3)   |
     |                   | <---------------- |
     |                   |                    |


Explanation:

Local Laptop:

Command: git push
Pushes the code changes to the GitHub repository.
GitHub:

Receives the push event from the local laptop.
Triggers a webhook.
AWS:

Stores the Terraform state file in an S3 bucket.
Receives the webhook event from GitHub.
AWS:

Triggers a Terraform provisioning process using the state file stored in S3.
Terraform:

Retrieves the Terraform state file from S3.
Applies the infrastructure changes or provisions resources in AWS based on the Terraform configuration.
The flow of information starts with the local laptop pushing code changes to the GitHub repository. GitHub triggers a webhook, which AWS receives. AWS, using the Terraform state file stored in S3, initiates the Terraform provisioning process. Terraform retrieves the state file, applies the infrastructure changes or provisions resources in AWS.

You run a command on your local laptop to clone a public repository and then run another command to push the cloned repository to your own GitHub repository. Draw a solution architecture diagram to depict the flow of information.

Local Laptop              GitHub
     |                        |
     |     git clone          |
     | ---------------------> |
     |                        |
     |    git push            |
     | <--------------------- |

Explanation:

Local Laptop:

Command: git clone <public repository URL>
Clones the public repository from the specified URL to your local laptop.
Local Laptop:

Command: git push <GitHub repository URL>
Pushes the cloned repository to your own GitHub repository, which is specified by the URL.
The flow starts with the git clone command, which fetches the repository from the public URL and creates a local copy on your laptop. Then, the git push command is used to push the cloned repository to your GitHub repository, which resides on GitHub's servers.

Please note that this diagram represents the flow of information between the local laptop and GitHub, and it does not include any intermediate steps or additional components that may be involved in the process.

## Site Reliability Engineering (SRE), Troubleshooting, Observability

You are asked by your manager to implement an automated system to collect metrics from your infrastructure by using a third party vendor's product. What steps might you take to ensure the system is not going to cause unwanted effects? How might you check that?

To ensure the implementation of an automated system for collecting metrics from your infrastructure using a third-party vendor's product doesn't cause unwanted effects, follow these steps:

Research and evaluate the vendor's product and reputation.
Test compatibility and assess any conflicts with existing tools.
Set up a sandbox environment for testing and evaluation.
Conduct a pilot implementation in a controlled subset of the infrastructure.
Implement robust monitoring and alerting mechanisms.
Perform performance testing to assess scalability and resource utilization.
Conduct a security assessment to identify vulnerabilities and risks.
Document the implementation process and provide training to relevant personnel.
Continuously monitor and evaluate the system's performance and impact.
Promptly address any issues or emerging risks.

Your manager asked you to run a script that is unfamiliar to you. How are you going to go about ensuring that this operation is done safely?

To ensure the safe execution of an unfamiliar script:
Review the script to understand its purpose and potential impact.
Test the script in a sandbox environment to assess risks and unintended consequences.
Backup data and configuration before running the script.
Limit permissions to minimize potential risks.
Test the script step-by-step to identify errors or unexpected outcomes.
Have a rollback plan in place to revert changes if needed.
Monitor the system during and after running the script for any issues.
Seek expert advice if unsure about the script or its impact.
Document the process and learn from the experience for future operations.
By following these steps, you can ensure the safe execution of an unfamiliar script.

## DevOps and Agile Transformation principles and methodology

Read the blog article given in Reference 1 (Become A DevOps Engineer in 2023: A Comprehensive Guide) and answer the following question. According to the author, what are the key technologies, tools and systems an aspiring DevOps should learn?

Version Control Systems: Git, SVN
Continuous Integration/Continuous Delivery (CI/CD): Jenkins, Travis CI, CircleCI, GitLab CI/CD
Configuration Management: Ansible, Chef, Puppet
Infrastructure as Code (IaC): Terraform, CloudFormation
Containerization: Docker, Kubernetes
Orchestration: Kubernetes, Docker Swarm, Apache Mesos
Monitoring and Logging: Prometheus, Grafana, ELK stack (Elasticsearch, Logstash, Kibana)
Cloud Platforms: AWS, Azure, Google Cloud Platform
Scripting and Automation: Bash, Python, PowerShell
Collaboration and Communication: Slack, Jira, Confluence, GitHub/GitLab

New commands logs - Enter up to ten new commands you have learnt this week
grep: Search for a specific pattern or regular expression within files.
awk: Process text files line by line, applying patterns and actions.
chmod: Change file permissions and access modes.
chown: Change ownership of files and directories.
echo used to display text or variables on the terminal. 
:wq to save and quit Vim.
:q to quit Vim.
:w to save the file
cut: Extract sections or columns from files or output.
sed: Stream editor for filtering and transforming text.

Glossary of the week - Enter new technical words you have learnt this week and their meanings.
Containerization: The process of encapsulating an application and its dependencies into a container, which provides isolation and allows for consistent deployment across different environments.

Orchestration: The management and coordination of multiple containers or services to work together as a single system, typically done by a container orchestration platform like Kubernetes.

Continuous Integration (CI): A software development practice where developers frequently merge their code changes into a shared repository, and automated build and test processes are triggered to ensure early detection of issues.

Continuous Delivery (CD): An approach in software development where software changes are automatically built, tested, and deployed to production-like environments, enabling frequent and reliable releases.

Infrastructure as Code (IaC): A practice of managing and provisioning infrastructure resources using machine-readable configuration files, enabling automated and repeatable infrastructure deployments.

Serverless Computing: A cloud computing model where the cloud provider manages the infrastructure and automatically provisions and scales resources as needed, allowing developers to focus on writing code without worrying about server management.

Microservices: An architectural approach where an application is composed of small, independent services that can be developed, deployed, and scaled independently, promoting flexibility and scalability.

Load Balancing: The distribution of network traffic across multiple servers or resources to optimize performance, maximize availability, and ensure efficient resource utilization.