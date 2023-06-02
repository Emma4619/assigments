Kubernetes, Docker, Containerisation and Virtualisation

What is a hypervisor and where does it sit in the server virtualisation stack?
A hypervisor is a software that creates and runs virtual machines (VMs). A VM is a software program that emulates a physical computer. It has its own operating system, applications, and data. VMs can be used to run different operating systems on the same physical hardware, or to isolate applications from each other.
The hypervisor sits at the top of the server virtualization stack. It is responsible for managing the resources of the physical hardware and providing a platform for the VMs to run on.

What is a container runtime and name the two most common runtimes?
A container runtime is a software component that creates and manages containers. Containers are lightweight, isolated environments that allow you to run applications without having to worry about the underlying operating system. The two most common container runtimes are Docker and Kubernetes .

Linux administration and shell scripting

Use just one command to create a directory structure where the directory sports contains a directory called football teams which itself contains africanteam which itself contains pwdkumba.

mkdir -p sports/footballteams/africanteam/pwdkumba
The -p flag tells the mkdir command to create any parent directories that do not exist. So, in this case, the mkdir command will first create the sports directory, then the footballteams directory, then the africanteam directory, and finally the pwdkumba directory.

sports
└── footballteams
    └── africanteam
        └── pwdkumba


Use the tree command to display your directory structure.
.
├── sports
│   └── footballteams
│       └── africanteam
│           └── pwdkumba
└── test.txt


Research the following linux commands a) grep b) sed c) awk
Grep is a command-line utility that searches for patterns in text files. It is one of the most commonly used commands on Linux and Unix systems. For example, grep [OPTIONS] PATTERN [FILE]
Where:
PATTERN is the pattern that you want to search for.
FILE is the file that you want to search. If no file is specified, grep will search the standard input.
OPTIONS are optional flags that can be used to control the behavior of grep.

Sed is a stream editor that can be used to edit text files. It is a powerful tool that can be used to perform a variety of tasks, such as searching, replacing, and deleting text.

Awk is a programming language that can be used to process text files. It is a powerful tool that can be used to perform a variety of tasks, such as searching, sorting, and summarizing text.

CICD, Git, GitHub, GitHub Action, Infrastructure as as Code (IaC), Terraform, Packer and Ansible
You create a repository in GitHub called myfirstrepo. You then clone this repository on your local laptop. On your laptop how would you check its remote address? How would you go about changing the remote address so that it points to repository called mysecondrepo?

To check the remote address of a cloned repository, you can use the following command:
git remote show origin
This will show you the URL of the remote repository, as well as other information such as the name of the remote and the branches that are tracked.

To change the remote address of a cloned repository, you can use the following command:

git remote set-url origin <new-url>

For example, to change the remote address to point to a repository called mysecondrepo, you would use the following command:

git remote set-url origin https://github.com/myusername/mysecondrepo.git

Once you have changed the remote address, you can push your changes to the new remote repository using the following command:

git push origin


You have a workflow running on GitHub Action that has the following code;
jobs:
  deploy_to_production:
    runs-on: ubuntu-latest
    name: deploy to production with soruce code
    steps:
      - name: Checkout GitHub Action
        uses: actions/checkout@v2

      - name: Login via Azure CLI
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: deploy to production step with soruce code
        uses: azure/spring-cloud-deploy@v1
        with:
          azure-subscription: ${{ env.AZURE_SUBSCRIPTION }}
          action: deploy
          service-name: <service instance name>
          app-name: <app name>
          use-staging-deployment: false
          package: ${{ env.ASC_PACKAGE_PATH }}
Describe what you think this code is doing.


The code you have provided is a GitHub Action workflow that deploys a Spring Cloud application to Azure. The workflow consists of three steps:
Checkout GitHub Action: This step checks out the latest code from the GitHub repository.
Login via Azure CLI: This step authenticates with Azure using the credentials stored in the AZURE_CREDENTIALS secret.
Deploy to production step with source code: This step deploys the application to Azure using the azure/spring-cloud-deploy@v1 action.


System Architecture and Application Design, Cloud Computing (AWS)
You have worked thus far with systems that you have had to download and install on your local laptop as well as systems hosted remotely on some external cloud. Describe in details the features and capabilities of all the systems (local and remote) that you have worked with thus far on this training. Draw a solution architecture diagram depicting these systems and where they fit in your solution landscape.
For all the systems that you have installed locally, write a manual for its installation and configuration.
In a general manner describe would you would interact with AWS account
AWS provide a public and a private area in which you could deploy your services. In which of these would you deploy the following services? a) EC2 instances b) DynamoDB databases c) VPC network d) S3 buckets e) IAM users
Site Reliability Engineering (SRE), Troubleshooting, Observability

Research on what APM (application programming monitoring)
Application Performance Monitoring (APM) is a software solution that helps IT organizations monitor and analyze the performance of their applications. APM tools collect data from various sources, such as application logs, system metrics, and network traffic, to provide insights into application performance. This data can be used to identify and troubleshoot performance issues, optimize application performance, and improve the user experience.

There are many different APM tools available on the market, each with its own strengths and weaknesses. Some of the most popular APM tools include: Dynatrace, New Relic, AppDynamics, IBM AppMonitor, Amazon CloudWatch

What is a system metric and why might it be useful to collect metrics?

A system metric is a measurement of a system's performance or health. Metrics can be collected from a variety of sources, such as hardware, software, and network devices.
Identifying performance bottlenecks: By monitoring system metrics, you can identify areas where your system is performing poorly. This can help you identify performance bottlenecks and take steps to improve performance.

What is a system log and why might you want to collect logs?

A system log is a file that records events that occur on a computer system. These events can include things like user logins, system startup and shutdown, and errors. System logs can be used to troubleshoot problems, track system usage, and comply with regulations.
Tracking system usage: System logs can be used to track how your system is being used. This information can be used to identify areas where your system is being underutilized or overused. This information can also be used to identify trends in system usage.

DevOps and Agile Transformation principles and methodology
DevOps is a set of practices that combines software development (Dev) and IT operations (Ops). It aims to shorten the systems development life cycle and provide continuous delivery with high quality.
Agile Transformation is a process of adopting Agile principles and practices into an organization. It involves changing the way people work, the way teams are structured, and the way the organization is managed.


Communication, Collaboration and Automation and key aspects of a successful DevOps implementation. Describe why these traits are important in a DevOps transformation process.
You work for an organisation that is very keen to make their work visible across the organisation. What do you understand by this and how would you suggest they go about it?
Making work visible across an organization means making sure that everyone in the organization knows what everyone else is doing. This can be a challenge in large organizations with many different teams and departments. However, it is important to make work visible in order to: Improve communication and collaboration, Increase transparency and Improve alignment.

New commands logs - Enter up to ten new commands you have learnt this week
Number	Commands	What does it do and how might you check its effect
1	history: This command will show a list of all the commands that have been executed in the current shell.
2	fc: This command will allow you to search through the history of commands.
3	!!: This command will repeat the last command that was executed.
4	!string: This command will repeat the last command that started with the string "string".
5	!n: This command will repeat the nth command in the history.
7	XXXXXXXX	YYYYYYYY
8	XXXXXXXX	YYYYYYYY
9	XXXXXXXX	YYYYYYYY
10	XXXXXXXX	YYYYYYYY
Glossary of the week - Enter new technical words you have learnt this week and their meanings.
Number	Word	Meaning
1	Agile Transformation: A process of adopting Agile principles and practices into an organization. It involves changing the way people work, the way teams are structured, and the way the organization is managed.
System metric: A measurement of a system's performance or health. Metrics can be collected from a variety of sources, such as hardware, software, and network devices.
System log: A file that records events that occur on a computer system. These events can include things like user logins, system startup and shutdown, and errors. System logs can be used to troubleshoot problems, track system usage, and comply with regulations.
Communication, Collaboration and Automation: Key aspects of a successful DevOps implementation. Describe why these traits are important in a DevOps transformation process.
Making work visible across an organization: Making sure that everyone in the organization knows what everyone else is doing. This can be a challenge in large organizations with many different teams and departments. However, it is important to make work visible in order to:
Improve communication and collaboration
Increase transparency
Improve alignment
2	
6	XXXXXXXX	YYYYYYYY
7	XXXXXXXX	YYYYYYYY
8	XXXXXXXX	YYYYYYYY
9	XXXXXXXX	YYYYYYYY
10	XXXXXXXX	YYYYYYYY
