## Lesson 4 - Creating and Publishing a Multi-VM Blueprint
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