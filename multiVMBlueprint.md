# Lesson 4 - Creating and Publishing a Multi-VM Blueprint
[YouTube Video](https://youtu.be/xulmAAAiHL4)

As mentioned in earlier lessons, you can create two different types of blueprints based on the complexity of the application that you need to automate. In the previous lesson, we walked you through the creation of a single VM blueprint to help you familiarize yourself with blueprints.

Now that you know how to create a single VM blueprint, in this lesson, we’ll focus on multi-VM blueprints.

We will start the lesson by covering some of the common blueprint lifecycle management tasks such as cloning, downloading, and uploading a blueprint.

To create a blueprint, you must first create a project and configure the environment. Therefore, we will briefly cover Calm services and substrates and walk you through the process of configuring a Nutanix environment as an example.

We will introduce you to various advanced Calm constructs such as macros, variables, dependencies, library, etc. These concepts will serve as a foundation to understand the process of creating a multi-VM Calm blueprint. Finally, we will wrap-up the lesson by covering each task involved in creating a multi-VM Calm blueprint.

By the end of this lesson, you will be able to perform blueprint lifecycle management tasks, configure a Nutanix environment and create a multi-VM Calm blueprint.

In addition, we will give you an overview of the LAMP stack, the foundation on which we will build our web application. We’ll cover load balancer design with a scaling web service tier to address our “two tier” web application’s high availability and performance.

Let’s get started!

## 2. Calm Blueprint Lifecycle: Cloning a Blueprint
[YouTube Video](https://youtu.be/xHm4v2NH-vk)

This is a topic we’ve discussed earlier in the context of the Calm Marketplace. As you may remember, it’s a very straightforward process which you can complete with a couple of clicks.

You can clone an application blueprint from a pre-seeded application blueprint. Cloning a blueprint is a simple process.

1. From the Marketplace, click the application blueprint you want to clone.
2. Click Clone.
3. Enter a name and select the project that you want to assign it to.
4. Click Clone again.

## 4. Calm Blueprint Lifecycle: Downloading a Blueprint
[YouTube Video](https://youtu.be/85r6DHQGrUI)

The ability to download a blueprint is one of the many blueprint management tasks that we talked about in the previous lesson. And while we went over them at a very high level, it’s worth taking a few moments to go into a little more detail on some of those tasks here.

You can download a configured blueprint to your local machine for later use. You also have the option to download the blueprint with the credentials and secrets used in the blueprint.

To download a blueprint:

1. Click the blueprint icon.
2. Click the blueprint that you want to download.
3. Click Download.
4. Select the check box, if you want to include credentials and secrets and type a password.
5. Click Continue.

You can also perform the same operation by selecting the blueprint and clicking the Download option under the Actions dropdown.

## 6. Calm Blueprint Lifecycle: Uploading a Blueprint
[YouTube Video](https://youtu.be/-Ed3mod0W0g)

Much like the ability to download a blueprint, the ability to upload one is also one of the eleven blueprint management tasks that we briefly discussed in Lesson 3.

You can also upload configured blueprints to the Blueprints tab. To do that:

1. Click the Blueprint icon.
2. Click Upload Blueprint.
3. Browse and select the saved blueprint.
4. Give the blueprint a name and select the project you want to assign it to.
5. Click Upload.

If you have previously downloaded the blueprint with credentials and secrets, then during upload you must provide the same password as previously specified.

## 8. Calm Services and Substrates
[YouTube Video](https://youtu.be/c59QVL__-8I)

We’ve covered some of the tasks involved in managing the blueprint lifecycle. We will next discuss all of the necessary topics to understand the creation of a multi-VM blueprint. Services, substrates, application profile, and actions are primary elements required to create a multi-VM blueprint.

In this section, we will dive into the process of configuring the substrates, and also discuss its importance. Before that, let’s do a quick recap of services and substrates.

### Services Overview
Services are logical entities exposed by an IP that span all application profiles and are managed by Calm. End users and services communicate with each other over a network using their exposed IPs and ports.

### Configuring Substrates
Substrates are combinations of the underlying cloud and the VM instance. When you select the desired cloud in the Calm UI, all the fields required to create a VM instance on that particular cloud are displayed. The combination of these fields is a substrate.

The substrate or VM details are configured in the environment.

The environment depends on the cloud provider selected during the project creation process. The environment consists of the cloud provider and the operating system details. For example, if you choose Nutanix as the provider. You have two options, Nutanix+Linux and Nutanix+Windows.

Calm supports Nutanix AHV, Nutanix Xi Cloud, AWS, VMware, GCP, and Azure as providers for your project. For simplicity, we will be covering the process to configure a Nutanix AHV environment.

### Configuring a Nutanix Environment
The Environment allows you to add multiple credentials and configure VM details for the selected provider. You can configure an environment when creating a project.

If you have configured the environment when creating a project, you can use the configured details while creating a blueprint or launching an application from the marketplace.

Environment is mandatory to publish the applications into the marketplace. If you do not define VM configuration while creating a blueprint, you must define the configuration as part of the environment. Also, during the application blueprint launch from the marketplace, the values are picked from the environment.

Before configuring a Nutanix environment, ensure that you have configured a project with Nutanix as a provider.

To configure the environment for Nutanix:

In the Create Project page, Under the environments tab, select Nutanix.

Under the Nutanix tab:

1. Enter credential details. Nutanix supports both password based and SSH private key based secret type.
2. Select the operating system type.
3. Provide VM configuration details such as name, image, firmware, vCPU, device bus, memory, etc.
4. Confirm whether or not to check log on status after the VM is created.
5. Specify the connection type and port.

## 10. Calm Macros
[YouTube Video](https://youtu.be/QK2boq2Tl_k)

Before we talk about macros, it is important to understand variables.

The properties such as IP addresses, DNS names, and instance IDs that are associated with the services provisioned in blueprints are called variables. They can be static, provided at run time, or generated during blueprint or action runs. Variables can have various data types (strings, integers, dates, or times) and various inputs (generated using single value, single input arrays, multiple input arrays, or an API call), and can be validated through regular expressions (regex).

### Macros Overview
Macros enable you to access the value of variables and properties set on entities, and help you make generic scripts and create reusable workflows.

For instance, a web server install script could use a macro to reference the IP address of a database. At deployment, the system replaces the macro with the actual IP address. Macros begin with “@@{“ and end with “}@@”.

The syntax of a macro is "@@{variable_name}@@", where "variable_name" is the name of the variable.

The syntax to access the value of variables or properties of other entities or dependencies is "@@{.<variable/attribute name>}@@".

* "entity name" is the name of the other entity or dependency
* "variable/attribute" name is the name of the variable or attribute.

For example, if a blueprint contains a service by the name of app_container, you can access the IP address of the app_container service in any other service using "@@{app_container.address}@@" syntax.

Calm macros are part of a templating language for Calm scripts. These are evaluated by Calm's execution engine before the script is run.

Let’s further explore the supported entities, types of variables, access credentials as macros, access macros of an array service, and a lot more.

### Supported Entities
Entities supported by macros include:

* Application
* Service
* Package
* Virtual machine

### Types of Variables
There are two types of variables:

* User-defined
* Built-in.

There are various built-in macros available for use based on different providers. Refer to the links below to view a list of built-in variables for the following providers.

* Nutanix variables
* AWS Variables
* GCP Variables
* Azure Variables
* Kuberenetes Variables
* VMware Variables

### Credentials as Macros
You can also access credentials as macros. The format to access credential is:

"@@{cred_name.username}@@" and "@@{cred_name.secret}@@" "cred_name": Name of the credential with which the cred is created.

### Access Macros of an Array Service
Nutanix Calm allows you to access macros of an array service using a special macro, which starts with "calm_array". You can configure a VM with replicas and access the common macros of all the replicas.

Let’s look at some of the examples:

* Use the following macro to retrieve the name of all the instances of VM separated by commas. "@@{calm_array_name}@@"
* Use the following syntax to retrieve the IP address of all the instances of VM separated by commas. "@@{calm_array_address}@@"
* Use the following syntax to retrieve the ID of all the instances of VM separated by commas. "@@{calm_array_id}@@"

### Supported Data Types
Macro supports string and numbers data types. You can use them in the following format:

* String: "@@{"some string"}@@" or "@@{'some string'}@@" Newline or other such special characters are not supported. You can use \ to escape quotes.
* Numbers: Supports integer and float. For example, "@@{ 10 + 20.63 }@@"

### Supported Operations
Following are the supported macro operations:

* Basic binary operations or numbers. For example, "@@{(2 * calm_int(variable1) + 10 ) / 32 }@@".
* String concatenation. For example, "@@{ foo + bar }@@".
* Slicing for strings. For example, "@@{foo[3:6]}@@".

## 12. Calm Application Profiles
[YouTube Video](https://youtu.be/hMKp0k-i0cg)

One of the tasks involved in creating a multi-VM blueprint is to add an application profile. You must select an application profile while you launch a blueprint.

As we discussed in the previous lesson, application profiles often include choices about where an application should run (AHV or AWS), but they can also be about sizing (small or large), or a combination of the two (small AHV or large AHV or small AWS).

An IT operator or developer should have a good understanding of the underlying differences between these choices, while abstracting that complexity from end users.

Let’s look at some of the tips and best practices when creating an application profile.

### Application Profile Tips and Best Practices

### Using default profile

Every blueprint has a default profile - it can be thought of as a base layer of the blueprint.

The default profile is used in the single-VM blueprint, but it is invisible to the user.
If needed, the default profile can be renamed for a better description for operators.

### Using additional profiles

Additional application profiles provide the operator role (or higher) deployment choices when using an application deployment.

* This increases blueprint reuse (of actions and governance) by eliminating the need to make separate blueprints for each permutation of deployment.
* Use application profiles to reduce the number of delegated run-time properties. Less choice reduces complexity and increases productivity.

### Naming convention

When naming an application profile:

* Make it as simple and user-friendly as possible.
* Use nouns that reflect the audience use case or jargon.
* Capitalized noun, ideally without spaces.
* Make application profiles a set of mutually exclusive choices.
* Avoid overly specific or jargon names when possible.
* Some examples of right naming conventions are as follows:
* Production, Staging, UserAcceptanceTesting, Test, QualityAssurance, Development, ContinousIntegration
* Public, Private, Hybrid
* AHV, AWS, Azure, GCP, ESX, K8s
* DataCenter1, BranchOffice9, Colo3, DisasterRecoveryWest, DisasterRecoveryCentral
* Small, Medium, Large, Jumbo
* Titanium, Gold, Silver, Bronze

### Sample Usage of Application Profiles

Application profiles express the intent of the blueprint developer to allow end-user choice between multiple deployment scenarios. Some typical choices include:

* Capacity Size: small versus medium versus large resource consumption for different needs on different days. For example, developers may need to frequently create new, small deployments with less CPU, storage, and memory using the latest version of today’s application code, so they would choose a “small” application profile. At the beginning of each week, testers could run a new performance test on a large resource environment using double the CPU, the same amount of memory, and quadruple the storage, so they would choose a “large” application profile, which may also be used by operations for production deployments.
* Infrastructure Provider: for a public, private, and/or hybrid deployment using different infrastructure providers. For example, developers may be restricted by governance to deploy daily workloads only on the private cloud, testers may deploy performance testing only on the public cloud when they need ephemeral resources, and staging and production workloads might always be deployed in a hybrid cloud fashion with a mix of multiple public and private clouds.
* Location and Environmental Resources: different scenarios may need different resources, for example a database address with user and password credentials may vary by location or by environment.

For example, you may have developer teams based in Asia, Europe, and the Americas. An application profile named “Asia” might have a Database variable set for db.asia.example.com, while an application profile named “Europe” might have the same database variable set to db.europe.example.com. Another example could incorporate choice for using development versus a staging database, each with different username and password credentials.

A “development” application profile variables may be set for username = development and password = development_password, while an application profile named “staging” could set the same variables to different values for username = staging and password = staging_password. or Limited to full configuration delegation with run-time property overrides.

* Any combination of the above: a hypothetical “Asia Development” application profile could incorporate all of these elements and more, such as: small capacity size, private cloud provider, located in Asia, and a development environment database variables, including allowing run-time override for any of the properties if desired.

## 14. Calm Actions
* [YouTube Video](https://youtu.be/wH_szTPOROc)
* [Action Overview](https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Calm-Admin-Operations-Guide-v3_0_0:nuc-nucalm-components-layer-action-c.html)

Now that we have covered Application Profiles, let’s next learn about application profile actions. An application profile consists of several actions.

Application Profile Actions, or Profile Actions, in short, are a set of operations that you can run on your application. For example, when launching a blueprint, the ‘Create’ action is run. If your application is not needed for a period of time, you could then run the ‘Stop’ action to gracefully stop your application. When you’re ready to resume work, running the ‘Start’ action will bring the app back up.

The default application profile also contains several actions, which appear as gray ovals on a service. Actions consist of one or more tasks. Tasks are executed sequentially on each service. The types of tasks are Execute, Set Variable, HTTP, and Delay.

All services execute their actions and tasks in parallel unless a dependency is created to control orchestration, allowing operational control across the entire application.

Let's review the simplest life cycle actions for IaaS.

### Create and Delete
Create: This action is invoked upon a blueprint launch and covers all services to allow orchestration. It provisions and configures the service in the provider.

Delete: This action deprovisions the services with the provider.

### Start, Stop, and Restart
These actions are available to operate the entire deployment. But in the simplest blueprints, these typically remain empty until populated with tasks. In addition, when the create action is complete, it will immediately call the start action on each service.

Correspondingly, the delete action will call and complete the stop action before performing its tasks on each service.

## 16. Calm Library Overview
[YouTube Video](https://youtu.be/KO-P1hUpuc4)

We covered tasks and variables in the previous sections. Let’s see how these can be reused when configuring an application blueprint.

Calm Library allows you to save user-defined tasks (scripts) and variables that can be used by other application blueprints. By using existing user-defined tasks and variables, you do not have to define the same tasks and variables again. You can share tasks and variables listed as part of the library across different projects. You can also customize an existing task or variable.

### Variable Types Overview
Users can create custom variable types for added flexibility and utility. Beyond just string and integer data types, you can create more data types such as Date/Time, list, and multi-line string. List values can be defined as a static list of values or attach a script (eScript or HTTP task) to retrieve the values dynamically at runtime.

While creating a custom variable type, you are required to select a project. However, you can share the variable type with multiple other projects using the "Share" option on the same page.

### Calm Library Overview
You can create tasks while configuring a blueprint and publish these tasks to the library. Nutanix Calm allows you to import these published tasks while configuring other blueprints across multiple projects.

Tasks can be browsed and loaded from or saved to the library, to promote reuse across blueprints. Tasks from the library are copied into a blueprint. They do not update when the library changes, which keeps the blueprints safe.

[YouTube Video](https://youtu.be/PFZmmhJ49xg)

## 18. The LAMP Stack
[YouTube Video](https://youtu.be/IE9bkgfAlTg)

### LAMP = Linux, Apache, MySQL, PHP

LAMP is the most common example of a web service stack, and is popularly used to build dynamic websites and web applications.

Over time, LAMP has become a term used to refer to a generic software model, and the model itself has been adapted to include different components. Three common examples are:

* A variant in which Linux is replaced by Windows, abbreviated as WAMP
* A variant in which Apache is replaced by Nginx, abbreviated as LEMP. Although it may seem odd to have an ‘E’ in the acronym, that comes from the pronunciation of Nginx, which is read as ‘Engine-X’
* A variant in which Apache is replaced by Internet Information Services (or IIS), amusingly abbreviated as WIMP

The original LAMP stack continues to remain popular, however, largely for its flexibility and because it is capable of hosting a variety of web frameworks. For example, if you are familiar with WordPress, Joomla, or Drupal, you may be interested to know that they run on the LAMP stack.

Owing to both its flexibility and popularity, you are likely to encounter the LAMP stack when working with web applications — which is why we are going to build our three-tier Calm web app on the LAMP stack as well.

But first let’s talk about each component of the LAMP stack.

### Linux
Linux belongs to the family of Unix-like operating systems. It was written by Linus Torvalds and has the features that are typical of a modern Unix OS, including multitasking, virtual memory, shared libraries, demand loading, shared copy-on-write executables, proper memory management, and multistack networking including IPv4 and IPv6.

To use Linux you need to download a distribution, which is a complete Linux system including the kernel and applications. Multiple distributions are available for download and, as you may remember, one that we discussed in an earlier lesson is CentOS.

In the LAMP stack, Linux is the foundation. Everything else runs on top of this layer.

### Apache
The second layer, the web server, is typically the Apache HTTP Server but can also be IIS or Nginx. Apache is used simply because it is a mature, feature-rich product and is arguably the most popular web server on the Internet.

Apache HTTP Server (commonly shortened to just ‘Apache’) is a free, open-source, cross-platform web server that played a pivotal role in the initial growth of the World Wide Web. It overtook NCSA HTTPd, has remained popular since 1996, and became the first web server to host more than one hundred million websites.

Apache’s features include Secure Sockets Layer (SSL) and Transport Layer Security (TSL) support, proxying, large file support, custom log files, and so on. Many features are also implemented as compiled modules, which extend the core functionality of the web server. These include authentication, authorization, support for server-side programming languages such as Perl and Python, and so on.

### MySQL
The third layer is the database layer and has traditionally been filled by MySQL. Popular alternatives include MariaDB and PostgreSQL, as well as NoSQL databases such as MongoDB.

MySQL is a free, open source relational database management system (RDBMS). As with any relational database, it organizes data into one or more data tables, in which the data types are related to each other. These relations help structure data. And from the perspective of the LAMP stack, MySQL stores data that, when queried via scripts, can be used to construct a website.

### PHP
The fourth and final layer of the LAMP stack is the application programming language. While this is commonly PHP, the role can be filled by other languages such as Perl and Python.

PHP was created in 1994 by Rasmus Lerdorf, who wrote a number of common gateway interface programs in C. He extended these programs to work with web forms and communicate with databases, and called this implementation Personal Home Page/Forms Interpreter — which is abbreviated as PHP/FI.

PHP is a general purpose scripting language that is especially useful for web development, and is also used as a general purpose programming language. PHP code is interpreted by a web server via a PHP processor module, which generates the resulting web page.

## 20. Linux Administration
[YouTube Video](https://youtu.be/Y-Qs8fS-PlY)

### Linux Administration Overview
If you’ve never administered Linux, here is a quick overview with some tips on how to manage a system to give you some familiarity with Linux environments. You’ll see that we leverage this knowledge to automate VM operations.

Every user on a Linux system has an account and programs will execute and run under their account name. Programs have file permissions for user ownership and access; they run under your user account.

Remote access to a Linux VM can be accomplished with command line access via SSH. You will use your SSH key to login to a user account on the Linux system. Since we will be creating new VMs from scratch, we'll usually access ephemeral Linux VMs by IP address.

System maintenance requires programs to be run by an administrative user. The administrative account is called the superuser, so administrative tools often start with su. The first administrative account on every Linux system is user root, but for security purposes, root logins are blocked from SSH access.

Therefore, user accounts can be added to the sudo-ers list to be allowed access to administrative tools. This enables user accounts to preface sudo before any command or program, granting superuser access.

To tie this altogether, you will see us add new user accounts with SSH key credentials and sudo permissions in cloud-init!

### Linux Administration Tips
Because Linux derives from Unix, it shares a history and terminology going back to 1971. There can be many interchangeable terms that are synonyms which can confuse new learners, but the following tips will help you.

Case matters, but everything on Linux defaults to use lower-case letters.

Programs are installed by package managers, so application, package, command, and program are roughly equivalent. A whole class of programs provide advanced Internet server functionality on top of an operating system, so synonyms exist for the class of application infrastructure packages: server, service, daemon, facility, and sometimes listener.

We will use the following Internet services for the three tier web application:

* mysqld (MySQL daemon)
* httpd (Apache daemon)
* sshd (SSH daemon)

You will see frequent use of sudo on these server facilities in the automation shell scripts. They will use sudo to execute installation, configuration, and operations of the HAProxy load balancer, Apache web server, and MySQL database.

If you ever wonder what a command is or how to use it, you can learn detailed technical usage on most facilities by prefixing man on the program, which is an abbreviation for manual page. E.g.: man httpd

### CentOS and Red Hat Linux Administration
If you’ve never used a recent CentOS or Red Hat Linux distribution, there are some very basic administrative patterns you should learn. We will use the same release of CentOS and Red Hat in order to keep parity for administrative programs and operations, but there can always be subtle to major differences between Linux distributions and even different releases of the same distribution!

For Firewall and security group access, the SSH service resides on TCP port 22.

Package management uses the command: yum

* ```sudo yum install -y haproxy```

Operations of the load balancer, web server, and database use: systemctl

* ```sudo systemctl start haproxy```

The standard journal log viewer is: journalctl

* ```sudo journalctl -u mysqld``` Note that you can use journalctl -f to keep watching log updates, use Control+C to cancel and return to the command prompt.

Configuration files reside under the /etc/ directory.

Troubleshooting any logs you can’t find with with journalctl mostly reside under /var/log/ directory. The following are important examples to help you understand the essential facilities of SSH and cloud-init:

* /var/log/messages
  * for general Linux system operation messages
* /var/log/secure
  * for SSH login information
* /var/log/cloud-init.log and /var/log/cloud-init-output.log
  * for cloud-init troubleshooting
  
One of the benefits of many Linux distributions is that most of the standards outlined above are upheld. When administering Internet services, you will use the above commands and directory locations!

[Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/)

## 21. Web Server Administration
[YouTube Video](https://youtu.be/7AyzB4f-RwY)

### Apache Web Server Administration
The Apache web server has a standard install and maintenance cycle using:

```sudo yum install -y httpd```
```sudo systemctl {enable,start,status,stop,restart} httpd```

Firewall and security group access details:

* http is TCP port 80
* https is TCP port 443 (outside of the scope of our course)

Configuration files are under the /etc/httpd/ directory and the web document root where programs and web pages reside in the /var/www/html/ directory.

Troubleshooting logs:

* ```sudo journalctl -u httpd```
* ```tail /etc/httpd/logs/\*.log```

Further reference: Apache HTTP Server Project: Documentation

* Apache version: ```httpd -v```

Tip: Although httpd started the project, the Apache project has grown to a large open source organization for many software projects, so the term is used for both the httpd web server and the umbrella parent organization.

Humor: Apache was named after "a patchy server" to indicate the project’s early days of software development.

## 22. Load Balancers
[YouTube Video](https://youtu.be/pD9OAAdbKW4)

Load Balancers are a critical architectural function in modern infrastructure and application design, they serve as a front-end for a service and distribute “load” across service resources. In our lesson, we’ll use a load balancer to split web traffic across the network to a web service array. Often, you will hear the terms request, load, traffic, and transaction used interchangeably. They have very close meanings that may be used separately in each service’s terminology.

For our simple needs, our load balancer will use the simplest distribution mechanism called “round robin.”

A web request from a web client is directed to the load balancer, which picks one web server from the array for the first web request and delivers the web request to it. The web server answers the request and returns the answer through the load balancer back to the web client requestor. For the next web request to the load balancer, it will pick the next web server available in the array. This repeats for each subsequent web request across the entire web server population and will cycle around to the beginning of the web server array.

The load balancer allows flexibility for web operations:

* Performance: distributes web requests, allowing us to scale in and scale out the web tier as transactions grow more complex or resource hungry.
* High uptime: allows removal of an individual web server for maintenance and return once complete while the remaining web servers handle traffic.

Contrast the above benefits to previous strategies to scale up the resources of a single web server to handle more traffic, but this has definite physical limits to scale combined with increasing expense for more CPU and memory and incurs downtime for maintenance.

### Designing the Load Balancer Tier
We’ll use a very popular, open source load balancer called HAProxy, which is included in many Linux distributions, including our choice of CentOS. We’ll install HAProxy and configure it to accept web connections on TCP port 80. Furthermore, we’ll configure HAProxy to distribute requests to the web server array specified using Calm macros for the web service array.

### HAProxy Load Balancer Server Administration
[YouTube Video](https://youtu.be/gr86xfFcgNE)

HAProxy uses the standard install and maintenance cycle:

* ```sudo yum install -y haproxy```
* ```sudo systemctl {enable,start,status,stop,restart} haproxy```

We are using HAProxy to direct traffic to web servers, so the Firewall and security group access is for http on TCP port 80.

The HAProxy configuration file is /etc/haproxy/haproxy.cfg

For troubleshooting logs:

```sudo journalctl -u haproxy```

Further reference: [HAProxy Project: Documentation](http://www.haproxy.org/#docs)

* HAProxy 1.8 Configuration
* HAProxy version: haproxy -v

Tip: HAProxy stands for High Availability Proxy.

## 24. Creating a Multi-VM Calm Blueprint
[YouTube Video](https://youtu.be/7tOcq5djkAs)

Now that you are aware of all the elements required to create a multi-VM blueprint, let’s now learn about the process to create one.

We gave an overview of multi-VM blueprint in the last lesson. Let’s do a recap and explore further.

Multi-VM blueprint is a framework that you can use to create an instance, provision, and launch applications requiring multiple VMs. You can define the underlying infrastructure of the VMs, application details, and actions that are carried out on a blueprint until the termination of the application.

You can create and configure multi-VM blueprints for the Nutanix, AWS, VMware, GCP, and Azure providers. For simplicity we will cover the process for Nutanix.

Once a provider is configured and a project is created, you can then create a multi-VM Calm blueprint. The process involves six tasks:

1. Adding a service.
2. Configuring VM, package, and service for your provider.
3. Setting up the service dependencies.
4. Adding and configuring an application profile.
5. Optionally, adding and configuring scale-out and scale in.
6. Creating an action

Let’s explore each of these tasks one by one.

### Adding a Service
Services are the virtual machine instances, existing machines or bare-metal machines, that you can provision and configure using Nutanix Calm. You can either provision a single service instance or multiple services based on the topology of your application. A service exposes an IP address and ports on which the request is received.

To add a service, from the Blueprint page, click + Create Blueprint and select Multi VM/Pod Blueprint from the dropdown.

In the Blueprint Setup window:

1. Enter the name and description for the blueprint.
2. Select a project. The available cloud options depend on the selected project.
3. Click Proceed.
4. Click + next to the Services. The service inspector panel is displayed.

### Configuring VM, Package, and Service for your Provider
This task involves defining the underlying infrastructure of the VM, application details, and actions that are carried out on a blueprint until the termination of the application on a Nutanix platform.

In the service inspector panel, enter a name for the service. The panel includes three tabs, VM, package and service.

Under the VM tab:

1. Enter a name for the VM.
2. Select either the existing machine or Nutanix for platform.
3. Select the OS type .
4. Specify the environment details or clone from the existing one.
5. Add credential details.
6. Specify the connection details such as port, type and protocol.

Under the Package tab:

1. Enter the package name.
2. Click Configure Install to install a package.
3. Configure tasks.
4. You can even add the default system actions, if needed.

Similarly, you can configure the tasks for uninstalling a package. When configuring the tasks, you have the choice to either reuse a system task or create one based on your requirement.

Under the Service tab:

1. Enter the service name
2. Enter the number of default, minimum and maximum service replicas that you want to create.
3. Add variables.

Once you provide all these details and click Save, the blueprint is saved and listed under the blueprints tab.

### Setting Up Service Dependencies
Dependencies define the order in which the system runs the tasks; Calm visualizes this process in the design phase with arrows indicating the direction of Nutanix Calm execution. You can manually define dependencies—a web server depends on a database—or automatically define them with the Calm engine when macros are referenced.

To set up a service dependency:

1. Select the service.
2. Click the dependency icon.
3. Drag-and-drop to the service on which you need to create the dependency.

### Adding and Configuring an Application Profile
You need to apply the application profile while launching a blueprint. To add and configure an application profile:

1. Click + icon in the Application Profiles.
2. Enter an application profile name.
3. Enter the name and value of the variable.
4. Check the Secret check-box to hide the variable value.

### Adding and Configuring Scale Out and Scale In
Before creating an action, you can optionally add and configure the scale out and scale in task. The scale-in and scale-out functionality lets you decrease or increase the number of service replicas. When you configure the scaling task as part of a profile action, you can define the number of instances to add or remove for the service per scale action or choose to define the number at runtime.

To add a scale in and scale out tasks, under the Application Profile, click + against Actions.

1. Enter the name of the task.
2. Select Scaling from the Type drop-down menu.
3. Select either Scale In or Scale Out.
4. Enter the number in the Scaling Count field.
5. Click Save.

The scaling out and scaling in number should be less than the minimum and maximum number of replicas defined for the service.

### Creating an Action
An action is a set of operations that you can run on your application that are created as a result of running a blueprint. To create an action:

1. Click the + icon in the Actions pane.
2. Select the service on which you want to create the task.
3. Enter the action details.
4. Enter the task details.

Once you have performed all these tasks, you can now see the blueprint in the Blueprints page.

## 26. Exercise - Create a Multi-VM Blueprint

In this series of exercises, you will pull all of the concepts you’ve learned together to build a load-balanced multi-VM web application using the LAMP stack. This is commonly referred to as a “two-tier” web application. You will use a current CentOS distribution for the Linux OS and host the web application on the private cloud with Nutanix AHV as the VM hypervisor.

We’ll walk through these steps together.

[Video 1](https://youtu.be/NquHQtPiTXI
[Video 2](https://youtu.be/ilFzJl_I030)
[Video 3](https://youtu.be/kLx5Rq-WLMU)

In the first exercise, you’ll create a new multi-VM blueprint:

Add your SSH key credentials
Add a WebServer VM and configure CentOS with cloud-init and shell tasks
Install and configure an Apache web server
Configure a one page PHP web application
In the second exercise, you’ll add a load balancer service:

Add an HAProxy VM and configure CentOS with cloud-init and shell tasks
Install and configure HAProxy load balancer to serve requests to the WebServer
And in the third exercise, you’ll add scalability to the WebServer to increase application performance, making it a web-tier array!

(In the next lesson, you will address orchestration between the Web Server and Load Balancer service dependencies.)

Creating a Multi VM Blueprint
From the Prism Central tab on your browser, select the Entities menu > Services and click Calm.

Select the Blueprints icon.

Click + Create Blueprint and select Multi VM/Pod Blueprint.

Type WebApplication in the Name field and select your HybridCloudEngineer project.

In the Description field, type: 2-Tier Web Application.

Select Proceed. You will now be presented with the Calm Blueprint canvas.

Select Credentials above the canvas work area.

Click + and use the information below to complete the dialog box:
```
Credential Name: superuser
Username: centos
Secret Type: SSH Private Key
SSH Private Key: In the upper right corner of the key field, click the box with the arrow, navigate to the C:\cygwin64\workspace.ssh\id_rsa private key and select Open.
Click Save at the upper right and click Back. Note that the blueprint shows a red exclamation mark in the top of the blueprint canvas, this is expected at this early stage of building a new blueprint!
```

Optionally, on the left of the blueprint canvas, click the small, half white square icon to expand the Application Overview palette to full height.

In the configuration panel on the left, which displays Application Profile Name, change the name from Default to Nutanix.

Immediately below the Application Profile Name, click + next to Variables.

For this variable, click the running man icon to toggle the color from grey to blue. This indicates a runtime variable that is changeable upon blueprint launch.

Add the following variable fields, please note that uppercase value of USER_INITIALS is important and that you should change the value of xyz to your initials or any name you prefer.

Name: USER_INITIALS
Data Type: String
Value: xyz
Secret: Do not change; keep unchecked.
Runtime: Click to toggle from grey to blue (already set in the previous step)
Click Save at the top of the blueprint canvas and then click Configuration. Note that the blueprint still shows a red exclamation mark - this is expected!

Click + next to Downloadable Image Configuration (0) to add a URL for a network accessible image.

Use the values below to complete the form. You can open C:\Scripts\CentOS8_URL.txt in a text editor, then copy and paste the contents for Source URL, below.

Package Name: CentOS_8_Cloud
Description Image: CentOS 8 Cloud Image
Image Name: CentOS_8_Cloud
Image Type: Disk Image
Architecture: X86_64
Source URI: [https://cloud.centos.org/centos/8/x86_64/images/CentOS-8-GenericCloud-8.2.2004-20200611.2.x86_64.qcow2]

Product Name: CentOS

Product Version: 8
Click Save at the upper right and then click Back. Note that the blueprint still shows a red exclamation mark - this is expected!

Click the Blueprints icon in the left column. Check the box next to your blueprint and from the Action menu, select Download to save your blueprint to your workstation. Check the box for Downloading credentials and type the passphrase nutanix/4u.

Click Continue and save the file. Open File Manager from the desktop task bar and go to the Downloads folder. Copy the saved blueprint file into your Workspace folder on the desktop. Your WebApplication blueprint is now saved up to this point for this exercise. You can also, right-click the blueprint in the folder and click Download with Frame and save to your local computer.

Now that the general settings in the blueprint have been configured and saved, add a new service to the blueprint to support web server configurations. From the Blueprint page, click your WebApplication blueprint.

Select + next to Service in the Application Overview window at the bottom left.

A new service will be created in the blueprint canvas and at the right a service configuration pane will populate information for the new Service1 service. Configure the following fields:

Service Name: Change Service1 to WebServer
Name: Change VM1 to WebServerAHV
Cloud: Nutanix
Operating System: Linux
Immediately below these settings is the Clone from environment option. This option will populate the VM configuration based on the VM settings in the Calm Project selected for this blueprint. Click Clone from environment and use the following to verify the settings.

* VM Name: WebServer-@@{calm_time}@@
* vCPUs: 1
* Cores per vCPU: 1
* Memory (GiB): 2
* Guest Customization: Check box selected
* Type: Cloud-init
* Script: Cloud-init configuration. If empty, select the Upload icon in the upper right hand corner of the cloud-init text box and browse to: C:\scripts\cloud-init.txt.
* Device Type: Disk
* Device Bus: SCSI
* Operation: Clone from Image Service
* Image: CentOS_8_Cloud
* Bootable: Check box selected
* NETWORK ADAPTERS (NICS): NIC 1 shows default-net.

Under NETWORK ADAPTERS (NICS), next to Private IP, click the radio button next to Dynamic.

Under CONNECTION, ensure the check box next to Check log-in upon create is selected. For the Credentials menu, select superuser.

Click Save at the top of the page: the red exclamation mark should disappear. If the exclamation mark remains, click on the exclamation mark to see what remediation steps are required. Make corrections and save your blueprint, repeat until the exclamation mark disappears.

Select Download to save your blueprint to your workstation. Check the box for Downloading credentials and type the passphrase nutanix/4u.

Click Continue and save the file. Go to the Downloads folder and copy the file to your Workspace folder. Your WebApplication blueprint is now saved up to this point for this exercise.

On the left side, for the WebServer service, click on the turn-down arrow to reveal the service actions. Note that you can toggle the turn-down arrow to reveal or hide service actions.

Choose the Restart service action. Note that the service on the blueprint canvas changes to display the Restart action, which is empty.

On your blueprint canvas, select + Task to add a task in the WebServer service Restart service action and fill out the following fields in the configuration panel:

* Task Name: WebServer_Restart
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_ServiceAction_Restart.txt file and click Open. This will upload the script to the Script box.
* On the left side, for the WebServer service, choose the Start service action. Note that the service on the blueprint canvas changes to display the Start action, which is empty.

On your blueprint canvas, select + Action to add a Start service action in the WebServer service and fill out the following fields in the configuration panel:

Task Name: Leave blank; this will be automatically populated.
Service Actions: Choose the Restart action.
Note: This reuses the existing Restart service action, because for the Apache web server, these service actions are effectively the same operation.

On the left side, for the WebServer service, choose the Stop service action. Note that the service on the blueprint canvas changes to display the Stop action, which is empty.

On your blueprint canvas, select + Task to add a Stop service action in the WebServer service and fill out the following fields in the configuration panel:

* Task Name: WebServer_Stop
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_ServiceAction_Stop.txt file and click Open. This will upload the script to the Script box.
* On the blueprint canvas, click on the “WebServer” service white box to display the VM Service Configuration panel on the right and select the Package tab next to VM.

Type WebServer_Package under Package Name.

Click Configure Install.

In the blueprint canvas, you will see Package Install appear within the WebServer service you have created.

Click + Task and configure the following in the right-hand Configuration panel.

If you previously saved this task to the library, provide just the Task Name and Type as specified below, then click the Browse Library button to source the Linux_OS_Update task and save a few steps. If not found, provide all of the task configuration:

* Task Name: Linux_OS_Update
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the Linux_OS_Update.txt file and click Open. This will upload the script to the Script box.
* Below the Script field, click Publish to Library.

In the Publish Task dialog box, note the saved task name and verify your install task configuration and click Publish at the lower right. This saves this task so it can be used in other blueprints or other services in the same blueprint.

Verify the entry in the task library. Click Browse Library at the top of the configuration panel. Select your saved task and review the settings at the right.

Click Cancel.

Click + Task to add a second task and configure the following in the right-hand Configuration panel:

Task Name: Install_WebServer
Type: Execute
Script Type: Shell
Endpoint (Optional): Skip; leave blank
Credential: superuser
Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_Install.txt file and click Open. This will upload the script to the Script box.
Click + Task to add a third task and configure the following in the right-hand Configuration panel:

* Task Name: 2Tier_Webapp
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_2Tier_Webapp.txt file and click Open. This will upload the script to the Script box.

Note: For this lesson, we are using a two tier web application. In the next lesson, we will update the web application to use the database, so please DO NOT USE the WebServer_3Tier_Webapp.txt by accident!

Click WebServer in the WebServerAHV service icon in the blueprint canvas and select the Package tab in the Configuration Panel.

Click Configure uninstall.

On your blueprint canvas, select + Task to add another task in the WebServer service and fill out the following fields in the configuration panel:

* Task Name: Uninstall_WebServer
* Type: Execute
* Script Type: Shell
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_Uninstall.txt file and click Open. This will upload the script to the Script box.
Click WebServer in the WebServerAHV service icon in the blueprint canvas and select the Service tab in the Configuration Panel.

Change the Number of Replicas to reflect the following values:

* Default: 2
* Min: 2
* Max: 4

Click Save.

Select Download to save your blueprint to your Frame workstation. Check the box for Downloading credentials and type the passphrase nutanix/4u.

Click Continue and save the file. Go to the Downloads folder and copy the file to your Workspace folder. Save only the most recent copy!

## 28. Exercise: Add Load Balancer Service
### Exercise: HAProxy Configuration
Now let’s walk through the steps to configure a load balancer to depend on a web server service in a two-tier web application.

1. Select the Entities menu > Services and click Calm.

2. Select the Blueprints icon in the left column.

3. If WebApplication is present, click on the blueprint and skip to step 7. If the blueprint is not present, this means you received a new cluster deployment and will need to upload your saved blueprint. Continue with the following steps.

4. Click Upload Blueprint and browse to the Workspace folder on your desktop and select your saved WebApplication JSON file. Click Open.

5. In the Upload Blueprint dialog box, select HybridCloudEngineer in the Project pull-down menu and type nutanix/4u in the Passphrase field. Click Upload. This will place you into the WebApplication blueprint you created and saved in previous exercises.

6. On the blueprint canvas, click WebServer in the WebServerAHV service and then the VM tab in the right configuration panel, scroll down to NETWORK ADAPTERS (NICS) and click + to add a NIC:

* Under NIC 1 click the dropdown and select default-net.
* Select Dynamic next to Private IP.
* Click Save.

7. Select + next to Service in the Application Overview window on the bottom left of the blueprint canvas.

The right configuration pane will populate information for the new Service2 service. Select the VM tab and enter in the following information:

```
Service Name: HAProxy
Name: HAProxyAHV
Cloud: Nutanix
Operating System: Linux
```

8. Click Clone from environment to populate the VM configuration from the Project. Use the information below to verify your settings.

```
VM Name: HAProxy-@@{calm_time}@@
vCPUs: 2
Cores per vCPU: 1
Memory (GiB): 2
Guest Customization: Check box selected
Type: Cloud-init
Script: CloudInit script is shown.
Device Type: Disk
Device Bus: SCSI
Operation: Clone from Image Service
Image: CentOS_8_Cloud
Bootable: Select check box
NETWORK ADAPTERS (NICS): NIC 1 has default-net selected.
```

10. Under NETWORK ADAPTERS (NICS), next to Private IP, click the radio button next to Dynamic.

11. Under CONNECTION, ensure the check box next to Check log-in upon create is selected. For the Credentials menu, select superuser.

12. Click Save at the top of the page. If any errors or warnings exist, hover your cursor over the red exclamation mark to see what remediation steps are required.

13. On the left side, for the HAProxy service, click on the turn-down arrow to reveal the service actions.

14. Choose the Restart service action. Note that the service on the blueprint canvas changes to display the Restart action, which is empty.

15. On your blueprint canvas, select + Task to add a task in the HAProxy service Restart service action and fill out the following fields in the configuration panel:

* Task Name: HAProxy_Restart
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the HAProxy_ServiceAction_Restart.txt file and click Open. This will upload the script to the Script box.

16. On the left side, for the HAProxy service, choose the Start service action.

On your blueprint canvas, select + Action to add a Start service action in the HAProxy service and fill out the following fields in the configuration panel:

* Task Name: Leave blank; this will be automatically populated.
* Service Actions: Choose the Restart action.

Note: This reuses the existing Restart service action, because for the HAProxy Load Balancer, these service actions are effectively the same operation.

18. On the left side, for the HAProxy service, choose the Stop service action.

19. On your blueprint canvas, select + Task to add a Stop service action in the HAProxy service and fill out the following fields in the configuration panel:
```
Task Name: HAProxy_Stop
Type: Execute
Script Type: Shell
Endpoint (Optional): Skip; leave blank
Credential: superuser
Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the HAProxy_ServiceAction_Stop.txt file and click Open. This will upload the script to the Script box.
```

20. Scroll to the top of the configuration panel on the right and select Package next to VM.

21. Type HAProxy_Package under Package Name and click Configure Install.

22. In the blueprint canvas, you will see Package Install appear within the HAProxyAHV service. Click the Click + Task and configure the following in the right-hand Configuration panel.

If you previously saved Linux_OS_Update task to the library, provide just the Task Name and Type as specified below, then click the Browse Library button to source the Linux_OS_Update task and save a few steps. If not found, provide all of the task configuration:

* Task Name: Linux_OS_Update
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the Linux_OS_Update.txt file and click Open. This will upload the script to the Script box.

23. Select + Task to add a second task and configure the following in the right-hand configuration panel:

* Task Name: HAProxy_Install
* Type: Execute
* Script Type: Shell
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the HAProxy_Install.txt file and click Open. This will upload the script to the Script box.

24. Select HAProxy within the HAProxyAHV service in the blueprint canvas and select the Package tab in the Configuration Panel.

25. Click Configure uninstall.

26. Select + Task and fill out the following fields in the configuration panel:

* Task Name: Uninstall_HAProxy
* Type: Execute
* Script Type: Shell
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the HAProxy_Uninstall.txt file and click Open. This will upload the script to the Script box.

27. Select Save.

28. Download the blueprint. Check the box for Downloading credentials and type the passphrase nutanix/4u.

29. Click Continue and save the file. Go to the Downloads folder and copy the file to your Workspace folder. Only keep the latest copy. Your WebApplication blueprint is now saved up to this point for this exercise.

Note: You can also download the file to your personal computer by right-clicking the file and choosing Download from Frame. This will save the file to your local systems default downloads folder.
