# On-Premises Private Cloud Automation
Nutanix Private Cloud Training for SaaS 3 Tier Web Architecture - Software as a Service

In this course, we will cover various tools and features that Nutanix provides to eliminate the process of manually operating infrastructure while extending up the stack to incorporate applications and maintenance operations. You will discover how Nutanix Prism Central eliminates IT intervention in performing repetitive, laborious tasks with Nutanix Calm automation to deliver simple, repeatable, and automated management of application creation, self-service consumption, and governance.

## Project - Private Cloud SaaS: Three-Tier Web Application
In the project at the end of the On Premises Private Cloud Automation course, I will:

* Create a three-tier web application blueprint that satisfies the IaaS business requirements for self-service private cloud deployment and security scenarios.
* Enhance the blueprint to provide PaaS by configuring the web application and creating web-tier scaling. Test the web application works by confirming scale-out load balancing across the web tier and database write updates.
* Enhance the blueprint to provide an action to update the database password and update the web application to use the new password, achieving a SaaS-like experience for developers with delegated, post deployment operations. Test the web application works with the new password.

## Lesson 1 Overview - Managing Multiple Clusters and Workspaces
In this course, we will cover various tools and features that Nutanix provides to eliminate the tedious, time-consuming process of manually operating parts of the cloud. We will walk you through how Nutanix Prism and Nutanix Calm increase visibility and eliminate IT intervention in performing repetitive, laborious tasks.

We will discuss how Nutanix Prism helps you manage multiple clusters and workloads. We will also illustrate how Nutanix Calm delivers simple, repeatable, and automated management of application creation, consumption, and governance. We have also included demo videos explaining these features and processes in the Nutanix environment.

## Glossary of Key Terms in these Lessons

### Authentication

Authentication is about verifying a user's identity against a trusted source of truth like Active Directory or any other IDP (Identity Provider).
Authorization

After a user has been authenticated, authorization determines what permissions/access they have, and what they are allowed or not allowed to do.

### Categories

Categories are used to define groups of entities in which policies and enforcement are applied.
### Image management

A Prism Central feature that enables you to upload images to clusters and maintain an inventory of the images on them.

### Image service

Ensures that uploaded images are saved to a cluster, and copied to additional clusters whenever you need them, on-demand.

### IT governance

IT governance is an element of corporate governance, intended at enhancing the overall administration of IT and reaping improved value from investment in information and technology.

### Prism Central

The Nutanix scale-out control plane to manage multiple joined Nutanix clusters and provide advanced management capabilities from a single pane of glass web console.

### Project

A project defines a set of Active Directory with a common set of requirements or a common function, such as a team of people collaborating on an engineering project.

### Quota

A quota specifies a usage limit on an infrastructure resource (compute, memory, or storage) for the project.

### Role-Based Access Control (RBAC)

Role-Based Access Control ensures that only specified individuals get access to the data they should have access to and all access, requests, and grants are fully auditable.

### Blueprint 
Blueprints are essentially recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a blueprint is executed it results in an application.

### Calm  
See: Nutanix Calm, below.

### CentOS 
A Linux distributable. For more information, see: Linux, below.

### Cloud-init 
Cloud-init is the industry standard multi-distribution method for cross-platform cloud instance initialization. It is supported across all major public cloud providers, provisioning systems for private cloud infrastructure, and bare-metal installations.

### Linux 
Linux belongs to the family of Unix-like operating systems. It was written by Linus Torvalds and has the features that are typical of a modern Unix OS. To use Linux, you need to download a distributable, which is a complete Linux system.

### Marketplace 
The Marketplace is a common platform for both the publisher and the consumer, and provides you with the ability to provision an application instantly.

### Nutanix Calm 
Nutanix Calm is a software product that provides advanced application-level orchestration that transforms how IT teams manage applications and support the business. Fully integrated into the Nutanix platform, Calm delivers a powerful, common management framework that can be simultaneously leveraged by multiple IT teams to rapidly create and deliver applications.

### Project 
A project defines a set of Active Directory groups with a common set of requirements or a common structure and function, such as a team of engineers collaborating on a product. The project also specifies the roles to associate with its members, networks that they can use, infrastructure to deploy onto, and (optionally) usage limits on infrastructure resources.

### Providers 
Providers are cloud service providers, bare-metals, or existing machines that you can use to deploy, monitor, and govern your applications.

### Role-Based Access Control (RBAC) 
Role-Based Access Control lets you define different roles in an organization and assign permissions accordingly.


### Application Profile Actions
Application Profile Actions (or Profile Actions for short) are a set of operations that you can run on your application. For example, when launching a blueprint, the ‘Create’ action is run.

### Application Profiles
Application Profiles expose simple choices to your end users. These choices are often about where an application should run (AHV or AWS), but they can also be used for ‘t-shirt’ sizing (small or large), or a combination of the two (small AHV or large AHV or small AWS).

### Blueprint  
Blueprints are essentially recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a Blueprint is executed it results in an application.

### CI/CD 
CI/CD stands for Continuous Integration/Continuous Delivery or Continuous Integration/Continuous Deployment. It is a term that is commonly used when discussing modern software development and is the solution to the problems that integrating new code can cause for development and operations teams. CI/CD solves those problems by requiring ongoing automation and continuous monitoring through the lifecycle of an application, from integration and testing to delivery and deployment.

### Custom Profile Actions 
Custom Profile Actions are created by the blueprint developer, and should be added whenever you need to expose a set of operations to the end user.

### Custom Service Actions 
Custom Service Actions are created by the blueprint developer, and should be added for any repeatable operations within the blueprint, like a function definition in a programming language.

### Marketplace Manager 
The Marketplace Manager is a section of the Calm UI that allows you to manage both custom blueprints and marketplace application blueprints. From the Marketplace Manager, you can publish, unpublish, and delete blueprints.

### Multi-VM Blueprints 
A multi-VM blueprint is a framework that you can use to create an instance, provision, and launch applications that require multiple VMs.

### Package Install/Uninstall  
Package Install/Uninstall are operations which are run during the ‘Create’ or ‘Delete’ profile actions. In other words, they are operations that run when a user first launches a blueprint, or finally deletes the entire application.

### Profile Actions 
See: Application Profile Actions, above.

### Service Actions 
Service Actions are a set of operations to be run on an individual service. Services span application profiles, so their actions (and the operations underlying those actions) do as well.

### Services 
Services are logical entities exposed by an IP, which span all application profiles, and are managed by Calm.

### Single VM Blueprint 
A single VM blueprint is a framework that you can use to create an instance, provision, and launch applications requiring only a single VM.

### Substrates 
Substrates are a combination of the underlying cloud and the virtual machine instance. When the desired cloud is selected in the Calm UI, all of the fields required for creating a virtual machine instance on that particular cloud are displayed — the combination of all these fields make up a substrate.

### System Defined Profile Actions 
System Defined Profile Actions are automatically created by Calm in every blueprint and underlying application.

### System Defined Service Actions 
System Defined Service Actions are automatically created by Calm in every blueprint and underlying application. While these actions cannot be individually invoked, they are called when the corresponding profile action is run.

### VM Pre-create/Post-delete 
VM Pre-create/Post-delete are operations which are run before the substrate is created, or after it is deleted.

## Lesson 1: Managing Multiple Cluster and Workload Resources
In this lesson, we will explain the difference between Prism Element and Prism Central. We will describe some of the key features of Prism Central such as identity management, role-based access control, image management, self-service, and categories. These features contribute in effective management of VMs and workloads.

By the end of this lesson, you will be familiar with how to manage categories, images, and create custom roles. You will also explore how to configure projects using Prism Self Service.

## 3. The Big Picture
In your previous studies about modern private cloud infrastructure, you learned how to operate VM workloads on a single Nutanix cluster with the AHV hypervisor. When you have more than one Nutanix cluster, management can become split and uncoordinated between each cluster. You must reproduce your work in each cluster to have a consistent configuration, governance policy, and resources. The on-premise management problem compounds quickly when you have multiple Nutanix clusters with different hypervisors, as many of our customers do! Furthermore, the public cloud typically represents even further fragmentation as a separate silo for IT governance, operations, and security, so we will address hybrid cloud management in a later course.

In this first lesson of this course, we'll introduce you to the advanced version of the Prism control plane, which manages multiple clusters and provides additional facilities across those clusters, allowing management at scale. Nutanix Prism Central unites management across all different types of Nutanix clusters and their workloads, from a single pane of glass preventing the need for multiple consoles. Rather than learn about all of the capabilities and features of Prism Central, we will focus on governance with projects and roles, AHV VM image management, and Calm automation.

## 4. Introduction to Cluster and Workload Management
It is easy and simple to work with one of anything because configuration and operations are instant and atomic. As soon as you have a second cluster, your configuration and operational work can easily double in order to maintain consistency! You have crossed over to the new world of scale, where we work to eliminate any single points of failure in our infrastructure, architecture, operations, and culture. Working at scale provides many new challenges for failures and remediation, but this is how organizations mature to tackle bigger initiatives with faster time to market.

To enable delegation for customer self-service as well as automation, there must be guard rails for safety, security audits, and resource management. All of these topics fit under the umbrella of governance and they must be addressed altogether systematically. When governance and operations are divided across multiple systems, the fragmentation it causes makes it harder to achieve consistency while also driving up complexity. As a hybrid cloud engineer, the trade offs between governance, consistency, and convenience are critical evaluations you must make for short-term and long-term business requirements.

## 5. Prism Element vs. Prism Central
Nutanix Prism provides central access for administrators to configure, monitor, and manage virtual environments in a simple and elegant way. Prism is a part of every Nutanix deployment and has two core components, Prism Element and Prism Central. Let us explore the difference between the two.

### Management

The primary difference between Prism Element and Prism Central is its capability of management. Prism Element provides the ability to fully configure, manage, and monitor Nutanix clusters running any hypervisors. However, Prism Element can only be used to manage a single cluster.

Alternatively, Prism Central allows you to manage different clusters across separate physical locations on one screen and offers an organizational view into a distributed environment.

### Example

To simplify, think of Prism Central as the manager of managers. Whether you have a single Nutanix cluster in your datacenter or as an example, let us say you have 10 remote offices each running a Nutanix cluster, and you also have a Nutanix cluster at HQ, Prism Element is the one managing the individual clusters.

Prism Central is your single pane of glass that allows you to simply manage all of your Nutanix clusters no matter where in the world they are located.

* Architecture

Prism Element is a distributed service within every Nutanix cluster and provides users access to the distributed system. Prism runs on every node in the cluster and, like other components, it elects a leader. The system forwards all requests from followers to the leader. If the Prism leader fails, the system elects a new leader. This configuration allows administrators to access Prism using the cluster IP or any Controller VM (CVM) IP address.

### 7. Understanding Prism Central
Prism is powered by advanced data analytics and heuristics and rich automation and combines several aspects of infrastructure management into a single, easy-to-use solution.

Prism Central provides a comprehensive set of features, we will focus on five primary features. Let us go through them one by one.

### Identity Management

The primary aspect of security is ensuring that only trusted users are provided with access to the cloud environment. Prism offers two types of user accounts for authentication.

The first type is local accounts where you can create and manage users within the given Prism instance. The second type of account is authentication based on Identity Provider (IDP), which serves as an authentication source to control access to Prism.

### Role-based Access Control (RBAC)

Prism Central provides IT administrators with role-based governance that limits user operations based on their role and permissions. You can maintain granular control over which IT staff can perform specified actions on entities such as VMs, applications, reports, and clusters.

### Categories

Prism Central enables you to group entities into a key-value pair called category. Typically, new entities are assigned to a category based on some criteria. Policies can then be tied to those entities that are assigned a specific category value.

Categories allow you to implement various policies across entity groups, and Prism Central allows you to quickly view any established relationships.

### Self-Service

One of the core capabilities that developers and business users love in the hybrid cloud is the ability to provision applications and virtual machines without the intervention of IT. Having development teams and lines of business satisfy IT needs through self-service using a private cloud model can help them be more productive, decrease time to market, and save IT staff time.

Prism Self Service radically simplifies application development and delivery, and brings automation to the process.

### Image Management

Image management plays a vital role when dealing with a higher number of clusters. Prism Central provides a highly available repository for your images. These images may be guest OS ISOs or your application disk images, which are uploaded through Prism Central and stored on a cluster.

## 9. Prism Central and Governance

Governance of resources is another primary aspect of Prism Central. Now that we’ve covered the various features of Prism Central that help in management of multiple clusters and workload, let’s next explore how Prism Central helps you achieve IT governance. If you are new to IT governance, don't worry, we will cover the basics.

### Introduction to IT Governance
IT governance is an element of corporate governance, intended at enhancing the overall administration of IT and reaping improved value from investment in information and technology.

It empowers businesses to manage their IT risks effectively and assure that the activities connected with information and technology are aligned with their overall business objectives.

### Challenges of Achieving IT Governance
In a real-time environment, tracking cloud consumption for efficient use is often a manual process.

A general lack of visibility into who is using what resources make it challenging for managers to predict future consumption, manage resources, and analyze risk. This lack of visibility into cloud usage can also result in resources being overutilized and becoming unavailable to the users for whom they were initially provisioned.

### IT Governance Using Prism Central
IT governance can be achieved only when there is a provision to visualize IT resource consumption, analyze risks, and plan for future requirements. Prism Central caters to these requirements through the following capabilities:

### Prism Capabilities

1. Infrastructure Management

Prism Central can manage your global Nutanix HCI infrastructure from one console. Prism simplifies and streamlines common workflows to make hypervisor and workload management as easy as checking your email.

2. Just in Time Forecast

Prism provides IT teams with visibility into how capacity is being used, an accurate forecast on how it will meet business demands, and a real-time insight of any hidden waste.

3. Automatic Remediation

It provides you with real-time performance behaviour of VMs, detects anomalies automatically, and enables the IT team to automate remediation.

4. One Click Upgrades

Prism solves update reluctance by offering one-click upgrades for each product within a cluster. The one-click upgrade process downloads the next version or allows you to upload manually as needed.

## 11. Identity Management

Previously, we had briefly covered various features of Prism Central that help organizations manage a multi-cluster environment. Going forward, we will dive deep into each of these features and explain its significance.

The first feature we will be discussing is identity management. Let’s understand how authentication and authorization are the key components of identity management.

Authentication is all about verifying a user's identity against a trusted source of truth like Active Directory or any other IDP (Identity Provider). Once the identity has been authenticated, the next piece is to determine what they are authorized to do or what they can access; this is the authorization piece.

To ensure that trusted users are provided with access to Prism, Prism Central supports user authentication. It is important to know user authentication because it is the fundamental requirement to configure other Prism Central features such as Role-Based Access Control and Prism Self Service. The user accounts configured are later used to assign Role-Based Access Control and create a project using Prism Self Service. There are three authentication options within Prism Central.

### Local User Authentication
Each Nutanix cluster includes a Prism Central admin user account that is created automatically. You can add more locally defined users as needed and update the permissions as necessary.

### Active Directory Authentication
Users can authenticate using their Active Directory or OpenLDAP credentials when Active Directory support is enabled for Prism Central.

Active Directory (AD) is a directory service implemented by Microsoft for Windows domain networks. OpenLDAP is a free, open source directory service, which uses the Lightweight Directory Access Protocol (LDAP), developed by the OpenLDAP project. Nutanix currently supports the OpenLDAP 2.4 release running on CentOS distributions only.

### SAML Authentication
Users can authenticate through a qualified identity provider when SAML support is enabled for Prism Central. The Security Assertion Markup Language (SAML) is an open standard for exchanging authentication and authorization data between two parties, ADFS as the identity provider (IDP) and Prism Central as the service provider.

As mentioned earlier, once user authentication is configured, you can later use these user groups/accounts to assign explicit roles and permissions.

## 13. Exercise - Identity Management

1. To begin, navigate to Authentication in the Settings.
2. Create a New Directory.
3. Enter the following details in Authentication Configuration:
  * Name: Active Directory
  * Domain: mydomain.com 
  Then, scroll down.
4. Enter the ```idap://myurl``` in the Directory URL and scroll down.
5. Enter the following details in Directory List:
  * Name: serviceaccount@mydomain.com
  * Service Account Password: P@ssword1
  Then, click Save.
6. Configure role mapping to this directory.
7. Click New Mapping in Role Mapping Window.
8. Enter the following details in the form:
  * Type: group
  * Values: AAPM
  Then, click Save.
9. Close the Role Mapping Management Window.

## 14. Role-Based Access Control
In large enterprises, it is essential to control the level of access across users. For instance, hardware resources are costly, shared, and in limited supply. Allowing all users to consume, manage, and monitor IT resources can lead to fast and inefficient consumption of resources. Thus, we want to restrict a selected group of users to manage them - someone like an infrastructure admin. However, entities like VMs, applications, clusters, etc. are best defined by the corresponding administrators. So you would want to allow corresponding administrators to access such entities but prevent them from altering hardware resources.

Consider another example, where you are dealing with vendors or contractors. Allowing these users to view or edit sensitive and confidential information can lead to a security breach. In such scenarios, you would want to restrict them from editing certain details of a project and also selectively limit access to certain resources.

All this can be implemented with Role-Based Access Control and Prism Central makes it a simpler process.

Role-based access control ensures that only specified individuals get access to the data they should have access to and all access, requests, and grants are fully auditable.

Prism Central supports role-based access control (RBAC) that you can configure to provide customized access permissions for users based on their assigned roles.

### Built-in Roles
To simplify the process of creating roles and providing access permissions, Prism Central includes a set of pre-built roles that are defined by default. Let us explore each of these roles and their corresponding access permission.

* Super admin: Full administrator privileges.
* Prism admin: Full administrator privileges but cannot create or modify user accounts.
* Prism viewer: View-only privileges.
* Self-Service admin: Permissions to manage cloud-oriented resources and services.
* Project admin: Manages cloud objects such as roles, VMs, apps, and marketplace belonging to a project.
* Developer: Has access to develop, troubleshoot, and test applications in a project.
* Consumer: Has access to deploy applications and blueprints in a project.
* Operator: Has access to the run actions on deployed applications in a project.

The project admin, developer, consumer, and operator roles are available when assigning roles in a project.

### Custom Roles
If the built-in roles are not sufficient for your needs, you can create one or more custom roles. But these features are restricted to AHV only.

To create a custom role:

1. Go to the roles dashboard.
2. Click the Create Role button.
3. Enter a name for the new role and describe the role.
4. Select an entity, the permissions listed for that entity are listed.
5. Select the permissions you want to apply. If you want to specify custom permissions, click the Change link and check all the permissions you want to enable.
6. Click Save.

To modify a custom role:

1. Go to the roles dashboard.
2. Select the desired role from the list.
3. Select Update Role from the Actions pull-down list.
4. Update the field values as desired.
5. Click Save.

## 16. Categories
[YouTube Video](https://youtu.be/f5OMlJWJm5M)
Categories are used to define groups of entities in which policies and enforcement are applied. They typically apply, but are not limited to: environment, application type, application tier, etc.

These categories can then be used by policies to determine what rules/actions to apply.

For example, you might have a Department category that includes values such as engineering, finance, and HR. In this case, you could create one backup policy that applies to engineering and HR and a separate backup policy that applies to finance. Categories allow you to implement various policies across entity groups, and Prism Central allows you to quickly view any established relationships.

### Creating a Category
To create a category:

1. Go to the categories dashboard.
2. Click the Create Category button.
3. Enter a name, and describe the category purpose.
4. Enter a category value in the Value field.

You can add a second and subsequent value for a category. To do that, click the plus sign (+). Enter the next value. Repeat this step for all the values you want to include in the category and click Save.

For example, if the category name is Departments, values might include Engineering, HR, Sales, Marketing, and so on.


### Modifying a Category
Built-in categories cannot be modified or deleted. To update an existing custom category:

1. Go to the Categories dashboard.
2. Select the desired category from the list.
3. Select Update from the Actions pull-down menu.
4. Update the field values as desired.
5. Click Save.


### Deleting a Category
1. Go to the Categories dashboard.
2. Select the desired category from the list.
3. Select Delete from the Actions pull-down menu.
4. Click OK when prompted.

Note: You cannot delete a category if it is used in an existing policy. All associations with existing policies must be removed before a category can be deleted.


### Assigning a Category
To assign a category value to one or more entities, such as cluster, VM, image, or subnet:

1. Go to the entity type dashboard.
2. Select all the entities of that type you want to tag with the same category value.
3. Select Manage Categories from the Actions pull-down menu.
4. In the Manage [Cluster|VM|Image|Subnet] Categories page: 
   a. Enter a category name. 
   b. Select the target value from the list. 
   c. Click the plus sign (+) to assign that category value to the selected entities. Repeat this step to assign a value for a second category.
5. Click Save.

Note: Categories support multi-cardinality, which means you can assign multiple category values to the same entity.

## 18. Prism Central Projects

A well-designed hybrid cloud can allow IT users—such as developers and line-of-business managers—to gain access to IT infrastructure and services through a self-service portal. This not only gives administrators with immediate access to services, but also reduces the burden on IT since it no longer has to serve as the middleman.

Prism Self Service represents a special view within Prism Central. While Prism Central enables infrastructure management across clusters, Prism Self Service allows end users to consume that infrastructure in a self-service manner.

Administrators can then set up self-service access for their Nutanix environment in a few clicks out of Prism Self Service.

### Working with Projects in Prism
The Prism Self Service feature allows you to create projects where consumers of IT infrastructure within an enterprise—individual users or teams such as development, test, and DevOps—can provision and manage VMs in a self-service manner, without having to engage IT in day-to-day operations.

### What is a Project?
A project defines a set of Active Directory users and groups with a common set of requirements or a common function, such as a team of people collaborating on an engineering project.

### Creating a Project
Before creating a project ensure to configure authentication.

To create a project, navigate to the Projects dashboard and click the Create Project button. On the page that is displayed, you must provide information in five major sections: General Settings; Cluster; User, Groups, and Roles; Network; and Quotas. Of these, Quotas is optional.

A quota specifies a usage limit on an infrastructure resource (compute, memory, or storage) for the project. Project members cannot use more than the specified limit.

A quota does not guarantee the project a certain amount of infrastructure resources. Instead, it ensures that a single project or a small number of projects do not overrun the infrastructure.

If the Nutanix cluster runs out of a resource, project members might not be able to use the resource even if the project has not reached its specified limit. However, if a project requires more resources, you can increase its quota.

If you do not specify a quota, no usage limit is applied. However, usage statistics are collected even if you do not specify a quota.

On the Create Project page:

1. In the General Settings section, enter a name and description for the new project.
2. In the Cluster section, select the target cluster on which the project has to be created.
3. Add Users, Groups, and Roles.
4. Check Allow Collaboration, to allow any group member to see the VMs, applications, and other objects created by other members of the group.
5. Select the usable network and the default network for the project.
6. Optionally, you can check the Quotas box to specify usage limits for compute, storage, and memory.
7. Click Save.

### Modifying a Project
To modify an existing project:

Go to the projects dashboard.
Select the target project.
Select Update Project from the Actions pull-down menu.
Update the field values as desired.
Click Save.

### Deleting a Project
To delete a project:

Go to the projects dashboard.
Select the target project.
Select Delete from the Actions pull-down menu.
Click OK.
Note: Before you can delete a project, you must first remove any VMs and networks, in that order, from the project.

## 21. Image Management

### Introduction to Image Management
Prism Central provides a centralized location to manage the images you require on registered AHV clusters.

### Uploading An Image from a Remote Server
The process of uploading an image from a Remote Server is very similar to the process of uploading from a workstation. The difference is instead of uploading an image file, you will specify the URL of the image in the Add Image page. You can also specify URLs to multiple images as part of a single operation.

When you specify image URLs, Prism Central uploads the images to all registered clusters. Uploading from a remote server also allows you to overcome file size limitations imposed by modern browsers. The file size limitation is usually 2 GB.

### Modifying an Image
To modify an image:

1. Go to Images.
2. Select the image you want to modify.
3. Select Update Image from the Action pull-down menu.
4. Make the desired changes.
5. Click Save.

To delete an image, select the target image and then select Delete from the Action pull-down menu.

### Importing Images to Prism Central
You can import images from registered clusters and manage the images centrally from Prism Central. An image imported to Prism Central continues to reside on the cluster that owns it. Prism Central only creates and stores image metadata locally, and it uses that metadata when you perform an action on the image.

After you import an image, the image remains visible on the cluster from which you imported it, but you cannot update the image from the cluster. You can update the image only from Prism Central.

To import images:

1. Go to Images.
2. Click the import Images button.
3. Select Import type. a. To import all images from all registered clusters, click All Images. b.To import all images from a selection of registered clusters, click Images On a Cluster, and then select the clusters. c. To import specific images from a given cluster, click the Select Images link provided for the cluster. Select the images that you want to import and click Done. d. Repeat this step for all the clusters from which you want to import images.
4. To begin the import, click Save.

Prism Central imports the metadata of the selected images and marks the images as read-only entities on the clusters.

Before introducing image management, the image service ensured that uploaded images were saved to a cluster, and copied to additional clusters whenever you needed them, on-demand. As the number of clusters grew, on-demand replication of images became too slow. If you had narrow network links to remote locations, this could add to copy time, making this process frustrating.

Prism Central image management now enables you to upload images to the clusters and maintains an inventory of the images on them.

### Benefits of Image Management
The first key benefit is hands-free image replication to your clusters. Nutanix has built a simple, policy-based method to replicate images to the clusters where you decide they are needed. Simply upload new or updated images, and Nutanix Prism Central copies them everywhere you want them automatically.

The second key benefit is a simple, straightforward option to upload images through Prism Central and directly choose the clusters to copy them to. You can also simply place your images where you need them and then decide on replication later.

### Adding an Image
You can add an image by uploading it from a workstation or a remote server.

### Uploading an Image from a Workstation
Using this method, you can select multiple images and upload them as part of a single operation.

With this method of upload, Prism Central identifies a single registered cluster for each specified image and uploads the image to it. The choice of a cluster is random.

The image becomes active in Prism Element on the selected cluster and inactive on other clusters registered to Prism Central.

To upload an image from a workstation:

1. Go to Images.
2. Click the Add Image button.
3. Navigate and upload the image file. a. Give the image a unique name. b. Select the image type. c. Describe the image. Repeat step 3 to add as many images as you want.
4. Click Next.
5. In the Placement Method, you can either assign categories to the images or manually select the target clusters.
6. Click Save.

When you assign categories to images, image placement decisions are delegated to configured policies. When you choose to manually select the target clusters, you have the option to place on all clusters registered to the PC or only on a subset of registered clusters.

Here is a demo that provides you with a detailed explanation on the procedure. [YouTube Video](https://youtu.be/0iWBvGyTfKs)

### Lesson Conclusion - Managing Multiple Clusters and Workspaces
To summarize, Prism Central manages multiple clusters across different locations and Prism Element manages an individual cluster. Prism is rich with various features that help to achieve IT governance.

In order to manage multiple clusters and workloads Prism supports:

* User authentication to authorize user’s identity.
* Role-Based Access Control to ensure right users have access to the right resources.
* Categories to define groups of entities for which policies and enforcement can be applied.
* Prism Self Service to create projects without IT intervention.
* Image management to manage images from a centralized location.

## Lesson 2 Overview - Calm Automation for Application Lifecycle Management
In the last lesson, we spoke at length about Prism Central and its capabilities, because Prism lays the foundation for automation in both private and hybrid clouds.

To give you some context, although they’re beyond the scope of this lesson, other Nutanix products – Karbon, for containers; Era, for databases; Prism Pro, a license that adds machine learning, analytics, and advanced automation to Prism – are all closely integrated with Prism. And to truly make the most of Calm, which automates application deployment and simplifies lifecycle management, it was important that you understand Prism in more detail than we covered in the Modern Private Cloud Infrastructure course.

Now that we’ve crossed that bridge, we can dive into the centerpiece of this Private Cloud Automation course – a product called Nutanix Calm.

Calm answers the growing challenge of enterprise application management, a problem that IT teams across the world have been wrestling with for years. It allows enterprises to address the challenges that arise from both the increasing volume of applications, as well as the increased complexity of the apps themselves. Calm accomplishes this by turning application management into streamlined, automated, and repeatable work.

In the rest of this course, we’ll walk through the various Calm capabilities that enable our vision of application automation.

We will start by introducing you to Nutanix Calm. We’ll talk about what Calm is, why it exists, and what it helps you accomplish. We’ll walk through several key capabilities, including providers, projects, role-based access control, and marketplace publishing.

By the end of this lesson, you will be familiar with how to publish blueprints to the marketplace for customer self-service, on-demand application workloads. You will also understand how to complete a deployment, audit, and deprovision for VM IaaS.

## 2. A Growing Need for Simplification
Managing applications in an enterprise environment has grown increasingly challenging over the years.

The sheer number of applications has resulted in increased complexity. There is no single, central owner for apps – different teams own their own applications. Fragmented ownership results in knowledge silos, which in turn leads to a lack of productivity.

And finally, the growing popularity of hybrid models – with applications distributed across both private and public clouds – introduces management challenges as well.

To address the problem of increasingly complex application management, Nutanix offers Calm.

## 3. Intro to Application Management
The success of the public cloud is generally due to rapid provisioning of facilities in an on-demand fashion under a "pay as you go" Operational Expenditure model. In order to replicate the cloud experience on-premise, a private cloud must offer self-service of automated facilities. There is a maturity in progression from IaaS to PaaS to SaaS to provide these experiences in a private cloud, and later you’ll learn to do this for a public, then hybrid cloud.

[YouTube Link](https://youtu.be/nWmR7MZjn3o)

### The Importance of Blueprints in Nutanix Calm

Blueprints are the heart of Calm - they model a business process for infrastructure, operations, and governance together. This unifies the different IT and application silos that normally fragment and slow the business. Blueprints can be exported as a JSON file and shared between people and unfederated Calm instances. It is a typical practice for blueprints to be placed under revision control, there are many Calm blueprints freely available in public Git repositories. In other words, Calm blueprints are software artifacts and they can encompass advanced software engineering practices, but do not be alarmed: we will progressively build up your familiarity with Calm capabilities over the remaining lessons through the easy-to-use Prism Central web console.

## 4. What is Nutanix Calm?
Calm provides advanced application-level orchestration that transforms how IT teams manage applications and support the business. Fully integrated into the Nutanix platform, Calm delivers a powerful, common management framework that can be simultaneously leveraged by multiple IT teams to rapidly create and deliver applications.

By approaching applications as complete entities, not just virtual machines (VMs), Calm automates how applications are created, consumed and governed. Calm delivers simple, repeatable and automated management of applications across a variety of environments, including private and public clouds.

### Automate, Empower, and Relax
Calm builds on the foundation laid by the Nutanix Enterprise Cloud. That foundation, as we discussed in the previous course consists of AOS, AHV, and Prism – providing an abstraction of hardware resources, native virtualization, and one-click operations.

On top of this, Calm provides two key capabilities: application automation and multi-cloud management.

Calm, whose name arose historically as an acronym for Cloud Application Lifecycle Management, has the ability to manage applications on and off of Nutanix infrastructure, giving hybrid cloud engineers the power to meet diverse business requirements across multiple providers and lifecycle operations from the birth to death of an application across hybrid cloud scenarios. As its name suggests, you should be able to automate, empower, and have a relaxing experience with Calm!

Application automation consists of three capabilities: app-centric automation and lifecycle management, policy-based governance, self-service provisioning.

Of these, self-service and governance themselves have three major components:

* Publishing blueprints to different groups using a policy-driven model
* Reducing miscommunication between teams
* Providing an alternative to roll-your-own cloud services while maintaining complete control and visibility over operations

Multi-cloud management involves abstracting applications from cloud infrastructure; deploying and managing applications on any cloud; and visibility and control of resource consumption.

### Accessing Calm
Calm is accessed from Prism Central. Click the menu icon at the top right of the screen, select Services, and then click Calm. [YouTube Link](https://youtu.be/2bp3cA_6qVY)

Calm opens within the Prism Central window of your browser and you will see a new sidebar to the left of the page that gives you access to Calm’s capabilities. By default, when Calm opens, the Applications page will be displayed.

The sidebar options, in order from top to bottom, are Marketplace, Blueprints, Applications, Library, Settings, Marketplace Manager, and Projects. As we progress through this course, we will discuss these options in more detail.

## 8. Generate an SSH Key Pair

### Linux OS, CentOS for a fast, license free base OS
For simplicity in operating system (OS) licensing and speed to provision a virtual machine (VM), we will focus on using Linux for our courses. Calm works equally well with Windows and nearly every facility we’ll learn with Linux has a compatible or analogous Windows feature.

Linux belongs to the family of Unix-like operating systems. It was written by Linus Torvalds and has the features that are typical of a modern Unix OS, including multitasking, virtual memory, shared libraries, demand loading, shared copy-on-write executables, proper memory management, and multistack networking including IPv4 and IPv6.

To use Linux, you need to download a distribution, which is a complete Linux system including the kernel and applications. Multiple distributions are available for download and one popular choice is CentOS.

The Community Enterprise Operating System (or CentOS) is a Linux distribution that provides a free, community-supported computing platform functionally compatible with its upstream source, Red Hat Enterprise Linux (RHEL) and uses open source licensing.

### SSH key pairs for secure access to Linux VMs
Public key authentication is preferred over the use of passwords, because it provides stronger cryptographic strength that even very long passwords cannot offer. Each SSH key pair includes two keys, a public key and a private key.

A public key is copied to a user account on the operating system, which is then used to encrypt data and allow secure access. This secured access requires using the corresponding private key to make the connection and unlock the OS user account on the VM.

A private key remains with a user and acts as proof of that user’s identity. A user will only be able to authenticate successfully with a server if they have a private key that corresponds to the public key used for encryption. Private keys can be password protected for further security if desired.

### Cloud-init for basic, dynamic, secure configuration
Cloud-init is the industry standard method across multiple Linux distributions for OS initialization. It is supported across all major public cloud providers, provisioning systems for private cloud infrastructure, and bare-metal installations. Linux distributions sometimes distinguish their variants between desktop, server, and cloud editions with only the latter having cloud-init facilities. Increasingly server and cloud editions have combined to offer cloud-init everywhere.

Cloud-init can identify the host infrastructure provider it is running on during boot, read any provided metadata, and initialize the system accordingly. This may involve setting up the network, adding storage devices, provisioning SSH access keys, and configuring many other aspects of the OS. Cloud-init will also parse and process any optional user or vendor data that was passed to the instance.

### 10. Generate an SSH Key Pair
[Exercise Solution](https://youtu.be/CKDBjZn7zQU)

1. Start your lab session by clicking “Access Lab,” and then, after a moment, “Start Streaming.”

2. Click the Start menu on your Frame desktop and select Cygwin64 Terminal.

3. Type the following commands in the Cygwin64 Terminal. After creating the .ssh folder, use the cd command to make .ssh your working directory:

```
 cd /cygdrive/c/cygwin64/workspace

 mkdir .ssh

 cd .ssh
 ```
4. Create a new SSH key pair with the RSA algorithm. To do this, type:

```
 ssh-keygen -t rsa
 ```
5. When prompted to enter the file where the key will be saved, enter the file path:

```
 ./id_rsa 
```

6. Press Enter. Leave the Enter passphrase (empty for no passphrase): prompt empty and press Enter to use no passphrase.

7. Leave the prompt blank and press Enter again to confirm using an empty passphrase.

A key fingerprint and randomart image will populate the screen, confirming you have successfully changed the SSH key pair. Press Enter.

8. View the keys.

```
    ls -a
```
9. On the following new command prompt, type:

```
    ssh-keygen -t rsa -p -N "" -m pem -f /cygdrive/c/cygwin64/workspace/.ssh/id_rsa
```
This modifies the private key to ensure that the public key may be extracted from it and that the key pair can be used for password-less SSH authentication.

10. Close the Cygwin64 Terminal window.

## 12. Components of Calm Governance
Calm allows you to empower different groups in the organization to provision and manage their own applications, giving application owners and developers on-demand workloads while elevating infrastructure managers to cloud operators.

Calm provides powerful, application-centric self-service capabilities, while maintaining control with role-based governance that limits user operations based on role, such as IT operator, developer, or manager. Calm allows administrators to safely delegate different levels of operational management, reducing administrative staff work while simultaneously accelerating end-users.

Additionally, Calm logs all critical activities and changes for end-to-end traceability, aiding security teams with key compliance initiatives. For example, you can enable the development team to create, scale, and destroy test and development environments without filing IT ticket requests.

Development teams benefit from rapid provisioning times, while IT maintains control, traceability of user operations, and visibility into resource consumption.

So, in the context of Calm Governance, there are four major capabilities that we need to discuss:

### Providers
Providers are public and private cloud service providers to deploy and govern your workloads and applications. Essentially, configuring a provider provides the required authorization for Calm to manage your applications using the provider’s resources.

### Projects
A project defines a set of users and groups with a common set of requirements or a common structure and function, such as a team of engineers collaborating on a product. The project also specifies the roles to associate with its members, networks that they can use, infrastructure to deploy onto, and (optionally) usage limits on infrastructure resources. You can also define the environment associated with a project, in case you want to publish the applications into the Marketplace.

### Role-Based Access Control
Role-Based Access Control (RBAC) lets you define different roles in an organization and assign permissions accordingly. Within Calm, RBAC enables organizations to control who can perform specific actions, including:

* Marketplace (publish, clone, provision)
* Blueprint (create, update, clone, delete, launch)
* Applications (manage, edit, create)
* Projects (add, update, assign resources)
* User (add, change, remove, roles)

### Marketplace Publishing
Before we discuss the Marketplace, it is necessary to talk about Blueprints. A Blueprint is the framework for every application that you model with Nutanix Calm. Blueprints are templates that describe all the steps that are required to provision, configure, and execute tasks on the services and applications that are created.

The Marketplace provides a set of pre-seeded application Blueprints that are available for you to use. The Marketplace is a common platform for both the publisher and the consumer, and provides you with the ability to provision an application instantly.

The Marketplace provides a one-click deployment experience for requesting applications or services. It presents a user with all the applications or services their projects and roles have the rights to access. The user can then select an application and deploy it, enjoying fully automated provisioning and scaling for both traditional multitiered applications and modern distributed services.

And finally, the Marketplace empowers organizations to consume services in a fully self-service manner at their own speed and includes built-in versioning to allow access to multiple revisions of blueprints.

## 14. Calm: Providers
As discussed earlier, Providers are public and private clouds that you can use to deploy, monitor, and govern your applications.

[Nutanix Calm: Providers - YouTube](https://youtu.be/rUum_ORNppY)

### Supported Providers
Nutanix Calm supports the following hypervisors and cloud providers as of version 3.0, with additional support options planned for future releases:

* AHV (the native Nutanix hypervisor)
* VMware vSphere (ESXi) on any infrastructure (Nutanix and non-Nutanix)
* Amazon Web Services (AWS) and AWS GovCloud
* Google Cloud Platform (GCP)
* Microsoft Azure and Azure GovCloud
* Nutanix Xi (public cloud)
* Kubernetes (Nutanix Karbon and GKE)

In general, you can configure one or more of these platforms as service providers if you want to create and use a blueprint to consume them. You can optionally specify costs for CPU, Memory, and Disk and these “show back” costs will be displayed during blueprint design and launch.

When using Nutanix as a Provider, note that all AHV clusters that are registered to the Prism Central instance from which you are running Calm are automatically added as providers. If you want to add a remote Prism Central instance as a provider, you must add that remote Prism Central instance as an account in Calm.

All other providers need to be configured manually, depending on the clouds that you intend to use.

### Configuring New Service Providers
At a very high level, to add a new service provider, you need to:

1. Navigate to the Settings page in Calm.
2. Click Providers at the top of the screen. By default, the Settings page opens on the General tab.
3. Click + Add Provider.
4. Name your provider and select the Type from the drop down menu.

You will then be required to provide configuration information specific to the type of provider you have selected.

For example, if you select Nutanix with the intention of using a remote Prism Central cluster, you will need to provide the Prism Central IP and port, as well as administrative credentials (username and password) for Calm to use.

On the other hand, if you select AWS, you will need to specify the Access Key ID, the Secret Access Key, and regions that you want included.

## 16. Calm: Projects
[YouTube Video](https://youtu.be/ilWKce3NffY)

A Project is a set of users and groups with a common set of requirements or a common structure and function, such as a team of engineers collaborating on an engineering project. A Project also specifies the roles to associate with its members, networks that they can use, infrastructure to deploy onto, and (optionally) usage limits on infrastructure resources.

By using different projects assigned to different clusters and users, administrators can ensure that workloads are deployed the right way each time. For example, a developer can be a Project Admin for a dev/test project, so they have full control to deploy to their development clusters or to a cloud, while having Read Only access to production projects, allowing them access to logs but no ability to alter production workloads.

### Infrastructure
Infrastructure defines the type of Providers for a Project, and a Project can involve multiple types of infrastructure. As we discussed earlier, the Providers that Nutanix supports are Nutanix AHV, Nutanix Xi, VMware, AWS, Azure, GCP, and Kubernetes.

### Environment
The Project’s Environment allows you to add multiple credentials and the default infrastructure configuration for each selected Provider, these are typically your organization’s VM standards. You must configure the Environment before launching a pre-seeded blueprint from the Marketplace: the blueprint will use the environment settings to provision workloads.

An additional benefit to creating a project Environment, you can clone that configuration for the VM while configuring a Blueprint, saving design time while increasing adoption for a standard configuration.

### Credentials
Credentials help in abstracting identity settings while connecting to an external system. You can configure multiple types of credentials (either SSH key or password) and define them as part of the Environment configuration. You can use these configured project environment credentials when launching a pre-seeded application Blueprint.

### Creating a Project
To create a project, you need to click Projects on the Calm sidebar, and click + Create Project. On the page that is displayed, you need to provide information in four major sections: General Settings; Users, Groups, and Roles; Infrastructure; and Quotas. Of these, Quotas is optional.

A quota specifies a usage limit on an infrastructure resource (compute, memory, or storage) for the project. Project members cannot use more than the specified limit.

A quota does not guarantee the project a certain amount of infrastructure resources. Instead, it ensures that a single project or a few projects do not overrun the infrastructure.

If a Nutanix cluster runs out of a resource, project members cannot use the resource even if the project has not reached its specified limit. However, if a project requires more resources, you can increase its quota.

If you do not specify a quota, you cannot apply usage limits because the project has unlimited consumption. However, project usage statistics are collected on AHV workloads even if you do not specify a quota.

On the Create Project page:

1. In the General Settings section, name the project and provide a description.
2. In the Users, Groups, and Roles section, add users or user groups and specify the level of permissions they will have in Calm. User roles supported in Calm are:

* Project Admin
* Developer
* Consumer
* Operator

3. In the Infrastructure section, select a Provider for use with your Project. Providers are configured separately, from the Settings page, as we discussed in the previous section.

4. Optionally, in the Quotas section, specify usage limits for vCPUs, storage, and memory.

5. After you complete the required sections for the Project, click Save & Configure Environment. The next step in creating a project is setting up the Environment.

### Configuring the Environment
The Environment specifies the default VM infrastructure configuration used when launching a pre-seeded Marketplace blueprint for each provider.

Environment configuration depends on the provider(s) used in the project. For simplicity’s sake, we will describe the Environment configuration process for AHV.

After clicking the Environment tab, you will need to:

1. Add credentials
2. Select the Nutanix provider under VM Configuration
3. Select an operating system (either Windows or Linux).
4. Specify VM details, including name, images to be used, vCPUs and cores per vCPU, memory, disk size, vGPUs, network adapters, and so on.
5. Confirm whether or not to check log on status after the VM is created, and specify the connection type and port.
6. Once you have provided all the required information, click Save to complete the process.

### Modifying a Project
Modifying a Project gives you access to all of the same fields as creating one. To modify a Project, you need to:

1. Navigate to the Projects page.
2. Open the Project you want to modify.
3. Update the sections as needed.
4. Save your changes.

### Deleting a Project
Deleting a Project removes it entirely from Calm, with no way to recover it. For you to delete a Project, it must not be associated with an application or a blueprint. Calm will verify this when you attempt to delete a project and, if an association is found, it will prevent you from proceeding.

To delete a Project:

1. Navigate to the Projects page.
2. Select the checkbox next to the Project you want to delete.
3. Select Delete from the Actions drop down menu.
4. Click Delete when prompted for confirmation.

## 18. Calm: Role-Based Access Control (RBAC)
[YouTube Video](https://youtu.be/X_eh2qCsx7o)

As we briefly discussed in the previous section, Calm supports four different user roles:

* Project Admin
* Developer
* Consumer
* Operator

Each role provides a different level of access to various Calm capabilities related to the Marketplace, Blueprints, Applications, Settings, the Task Library, Projects, and Users.

For example, in the Marketplace, a user with the Developer role can clone and edit app blueprints, make a publishing request for an application. A Project Admin, can do both those things, and send the app publishing request to an administrator. On the other hand, Consumers can only launch blueprints while Operators can only choose operations on existing, deployed workloads in their project. In other words, lower roles are subsets of higher roles.

It’s important to note here that the four roles listed here are also roles in Prism Central, and this speaks to how tightly integrated Prism Central and Calm are. By design, Calm inherits the RBAC configuration that you define in Prism. If you assign someone the role of Project Admin in Prism Central, for example, they will have access to Project Admin permissions in Calm as well.

For details about the permissions associated with each role, see the [Roles and Responsibilities](https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Calm-Admin-Operations-Guide-v271:nuc-roles-responsibility-matrix-c.html) table of the Calm Admin Guide.

## 21. The Nutanix Marketplace
At the beginning of this lesson, we briefly talked about blueprints and the Marketplace. Let’s take a moment to discuss blueprints in a little more detail.

A blueprint is the framework for every application that you model with Nutanix Calm. Blueprints are templates that describe all the steps that are required to provision, configure, and execute tasks on the services and applications that are created.

Blueprints are essentially recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a blueprint is executed it results in an application deployment, these workloads can be managed from the Applications menu.

A blueprint turns an application into a single unit that can be managed by an infrastructure team. This makes application lifecycle management and deployment both automated and repeatable, freeing up the time that infrastructure teams are presently devoting to deploying and managing infrastructure and applications.

The Marketplace provides a set of pre-seeded application blueprints that are available for you to use. The Marketplace is a common platform for both the publisher and the consumer, and provides you with the ability to provision an application instantly.

Generally, the Marketplace displays a collection of blueprints available to the user’s projects. You can view application details, filter and search for custom or pre-seeded blueprints, clone a blueprint, or launch a blueprint from the Marketplace.
[Nutanix Marketplace - YouTube Video](https://youtu.be/NgEPwGe6aBk)

### Filtering Blueprints
Creating a blueprint allows you to package automation steps into one centralized package that can be reused in any locale, updated as a whole bundle, and versioned to show the full lifecycle of an application or set of applications. Blueprints in the Marketplace are sorted into categories. You can use the category drop down menu to filter blueprints and find applications in specific categories. These categories are helpful in determining the purpose of the blueprint, and narrowing down your search - making it even easier to quickly deliver value to the business.

### Searching for Blueprints
The Marketplace also includes a search bar that allows you to search for a specific set of keywords appropriate to the type of blueprint you would like to use. Unlike Categories, where you are browsing a subset of a specific type of blueprint, searching can provide a more targeted list of results that can narrow the resulting scope to exactly what you are looking for.

### Cloning a Blueprint
If you need to duplicate a blueprint and make customizations, the Marketplace allows you to clone a blueprint. All you need to do is:

1. Select the Blueprint.
2. Click Clone.
3. Name the Blueprint.
4. Assign it to a Project.

### Launching a Marketplace Item
Finally, you can also launch a Marketplace item to deploy the blueprint. We will cover this in more detail in a later lesson, but the basic process is quite straightforward.

On the Marketplace page, you need to:

1. Click the application you want to launch and then click Launch.
2. Name the application.
3. Select an application profile.
4. Verify the VM Configuration and Credentials.
5. Click Create.

You can see a walkthrough video of these steps in the solution for the upcoming exercise.

## 23. Create a Calm Project

### Series of Four Exercises
In this series of exercises on this and the upcoming pages, you will:

1. Create a Calm project
2. Use the project you created to publish a default blueprint to the Calm Marketplace.
3. Launch the blueprint from the marketplace, name the application and audit the deployment process.
4. Delete the application.
In each exercise, we will walk you through the steps to perform these tasks. There is also a video walkthrough on each of the following “Solution” pages.

### Creating a Calm Project
[YouTube Video](https://youtu.be/stqznywSDd0)

1. From the Prism Central browser tab, select the Entities menu (the three-lined hamburger icon, upper left) and go to Services and click Calm. If the Welcome to Calm pop-up window appears, close it.

2. Hover your mouse cursor over the icons at the far left of the Calm page to see each name. Click the Projects icon.

3. Click the + Create Project button and use the values below to complete the General Settings section.

* Project Name: Test-Project
* Description: Test workload

4. To the right of Infrastructure, click Select Provider and select Nutanix:

* The pre-selected account should be: NTNX_LOCAL_AZ
* Click Select Clusters & Subnets.
* In the Select Subnets dialog box, select your cluster.
* Click the check box next to default-net and click Confirm.

5. Use the values below to set Quotas:

* vCPUs: 20
* Storage: 1000
* Memory: 48

6. Click Save & Configure Environment.

A message showing Project data successfully accepted by server briefly appears. You will be switched to the Environment page. The Environment page allows you to define the components necessary to deploy a VM.

7. On the Environment page, the Linux configuration should already be expanded. Use the values below to configure the VM:

* vCPUs: 1
* Cores per vCPU: 1
* Memory (GiB): 2

8. Click the check box next to Guest Customization. In the Script field, hover your mouse cursor over the up-arrow icon in the upper right corner to reveal Upload script. Click Upload script and navigate to C:\Scripts)). Select the cloud-init.txt file and click Open**. This will upload the script to the script field:

```
 #cloud-config
     users:
      - name: centos
     ssh-authorized-keys:
 - @@{superuser.public_key}@@
 sudo: ['ALL=(ALL) NOPASSWD:ALL']

```

9. Scroll down and expand the DISK (1) section to see the disk configuration. Use the information below to configure the disk:

```
Type: Disk
Bus Type: SCSI
Operation: Clone from Image
Image: Select the CentOS8 image
Bootable: Select the check box
```

10. Scroll down to NETWORK ADAPTERS (NICS) and click the plus button to the right to add a NIC. Use the table below to configure the NIC:
```
NIC 1: default-net
Private IP: Select Dynamic
```

11. Scroll down to Connection. Click the Credential drop-down menu and select Add New Credential. Use the following information to configure the new credential:

* Credential Name: superuser
* Username: centos
* Secret Type: SSH Private Key
* SSH Private Key: In the upper right corner of the key field, click the box with the arrow, navigate to: C:\cygwin64\workspace.ssh\id_rsa and select Open. Ensure the inserted key text has -----BEGIN RSA PRIVATE KEY----- shown at the top. Click Done.

Note: Adding new credentials can also be done from the top of the page by clicking the + next to Credentials.

12. Ensure the box next to Check Log-in upon create is selected.

13. Scroll to the bottom of the page and click Save.

14. Click the Projects icon in the left column to see Test-Project in the Projects list.

Note: The HybridCloudEngineer project shown in the Projects list has the same configuration as your Test-Project.

## 25. Exercise - Publishing a Blueprint to the Marketplace
[YouTube Video](Exercise - Publishing a Blueprint to the Marketplace)

1. Select the Entities menu (the three-lined hamburger icon) > Services and click Calm.

2. Hover your mouse cursor over the icons to the far left of the browser. Click the icon named Marketplace Manager. On the Marketplace Manager page, under the Marketplace Blueprint tab, you will find a default blueprint called ExpressLaunch.

3. Click the check box next to ExpressLaunch (default blueprint) in the Marketplace Blueprints view.

4. In the ExpressLaunch panel at the far right of your browser, remove the default project in the Projects Shared With drop-down menu. Select Test-Project and click Apply.

5. In the ExpressLaunch panel, click Publish and verify that the Status column for the blueprint shows Published.

6. Hover your mouse cursor over the icons to the far left of the browser. Click the Marketplace icon. You should see ExpressLaunch listed.

## 27. Exercise: Launching a Blueprint from the Marketplace
[YouTube Video](https://youtu.be/4rxk4fdZFEM)

1. Select the Entities menu > Services and click Calm.

2. Click the Marketplace icon in the left column.

3. Click the ExpressLaunch blueprint and click Launch.

4. Select Test-Project.

5. In the Name of the Application field, type Test-App and click Create.

6. When the view changes and you see PROVISIONING, click Audit. Expand the provisioning view. Continue to expand each new component as it appears to follow the provisioning progress to completion.

## 29. Exercise: Deleting an Application
[YouTube Video](https://youtu.be/u6A-1rpDFNE)


1. Select the Entities menu > Services and click Calm.

2. Hover your mouse cursor over the icons at the far left of the browser. Click the Applications icon.

3. Select the checkbox next to Test-App.

4. Select Delete from the Action drop-down menu.

5. Click Confirm in the Delete Application dialog box.

6. Click Audit to monitor the Delete process.

NOTE: Make sure to delete applications when directed to do so. If left running, you will run out of cluster resources and will be unable to launch applications in future exercises.

## 32. Lesson Conclusion - Calm Automation for Application Lifecycle Management
[YouTube Video](https://youtu.be/tB8U2xm5P3s)

In this lesson, we described a number of key features in Calm – Providers, Projects, RBAC, and the Marketplace.

To quickly recap what we discussed:

* Providers are cloud service providers, bare-metals, or existing machines that you can use to deploy, monitor, and govern your applications.
* Projects specify the roles to associate with their members, networks that project members can use, infrastructure to deploy onto, and (optionally) usage limits on infrastructure resources.
* Role-Based Access Control (RBAC) lets you define different roles in an organization and assign permissions accordingly.
* And finally, the Marketplace is a common platform for both the publisher and the consumer, and provides you with the ability to provision an application instantly.

In later lessons, we’ll walk through how these capabilities come together to allow you to automate application deployments in Calm, so your users can deploy applications with just a few clicks.

## Lesson 3 Overview - Creating and Publishing a Single VM Blueprint
In this lesson and the next, we’re going to focus on blueprints. Blueprints are recipes for applications and infrastructure combined with their operations and governance. Enterprises derive a number of benefits from the one-click simplicity that they provide.

We’ll talk about this in more detail shortly, but the ability to turn an application into a repeatable, automated blueprint offers enterprises a number of benefits:

* Greater agility while minimizing human error
* Broader self-service capabilities while allowing IT to retain centralized control
* The ability to modernize app development by pairing Calm with a certified Kubernetes solution
* The ability to automate provisioning across multi-cloud architectures from a single management interface.

That’s why we’re going to spend the next two lessons on a deep dive into blueprints. In the previous lesson, you used one of the pre-seeded blueprints to deploy an application from the Marketplace. Now, we’re going to talk about how to turn an application into a marketplace blueprint that can be launched with a couple of clicks.

You can create two different types of blueprints based on the complexity of the application that you need to automate, and we will be teaching you how to use both in succession. In this lesson, we will walk through the creation of a single VM blueprint to help you familiarize yourself with blueprints themselves, the components of a blueprint, and the steps involved in creating and publishing one.

Then, with this foundation well-established, in the next lesson we’ll focus on multi-VM blueprints.

So, before we move on, let’s summarize what you will learn in this lesson. We will discuss how you can create, manage, and publish your own application blueprints. We will start with a single-VM blueprint and discuss the various concepts you need to be familiar with.

We will walk through:

* The different elements of a Calm blueprint
* Single-VM and multi-VM blueprints
* The various tasks involved in managing blueprints such as uploading, downloading, editing, and deleting
* How to use the Marketplace Manager to publish, unpublish, and delete blueprints.

## 2. The Importance of Calm Blueprints and Marketplace Publishing
While we have very briefly discussed both blueprints and the Marketplace in the previous lesson, we will now explore both subjects in more detail. [YouTube Video](https://youtu.be/ZhJCtS-KMcY)

Nutanix Calm, as we learned previously, is a multi-cloud application management framework. And, as we will see in this lesson, it transforms the way that enterprises work with applications.

In Calm, applications are defined via simple blueprints that can be easily created using industry standard skills and control all aspects of the application’s lifecycle, such as provisioning, scaling, and cleanup. These blueprints can be created through the UI, or via code with a Python-based DSL, including seamless conversion.

Once created, a blueprint can be easily published to end users through the Nutanix Marketplace, instantly transforming a complex provisioning ticket into a simple one-click request.

The ability to turn applications into automated blueprints brings a number of benefits to any enterprise that uses Nutanix Calm.

### Better Agility, Fewer Errors
A blueprint incorporates relevant VMs, configurations, related binaries, and other elements of each app into a single unit that can be managed by the infrastructure team. This makes application lifecycle management and deployment both automated and repeatable, freeing up the time that infrastructure teams are presently devoting to managing their applications.

### Self-service, Central Control
As we’ve seen in the previous lessons, self-service and RBAC allow IT teams to empower different groups to provision and manage their own applications. Activities and changes are logged with end-to-end traceability, helping security teams with compliance initiatives.

### Modernized App Development
When paired with a certified Kubernetes solution, Calm allows you to modernize app development without losing policy control. In addition, Calm natively integrates with Jenkins to empower Continuous Integration and Continuous Delivery (CI/CD) pipelines with automatic infrastructure provisioning or upgrades for all applications.

### Unified Multi-Cloud Orchestration
Calm unifies the management of all your clouds into a single pane of glass, removing the need to move back and forth between multiple management interfaces. Calm automates the provisioning of multi-cloud architectures, scaling both multi-tiered and distributed applications across different cloud environments.

## 4. Understanding the Full Potential of Blueprints
[YouTube Video](https://youtu.be/SzFsCLdbp7o)

The reason it’s so important to understand blueprints - so important that we’re spending two lessons in this course on the subject - is because of how Calm contributes to fully realising the potential of a hybrid cloud IT environment.

The Nutanix Enterprise Cloud OS provides a single operating system across multiple cloud environments, while Nutanix Calm delivers application automation and lifecycle management with self-service capabilities.

So, an IT organization can quickly embrace the various clouds that the business wants to consume and satisfy a broader range of needs, while providing the same end-user and administrative experience across clouds. Since Nutanix Prism and Calm provide native capabilities for application automation, application lifecycle management, and self-service, your IT consumers can leverage the Nutanix marketplace to deploy infrastructure services or applications.

When deploying applications from the Marketplace, your customers not only get a simple, one-click experience, but you also get to ensure governance requirements are followed.

You can work with teams in your organization to define specific application policies that must be enforced. Nutanix Calm enables you to optimize the application lifecycle by tailoring application blueprints for each of your end-user groups and making them accessible in a customised service catalog. Nutanix Calm acts as a front-end portal to deploy services.

In addition to Calm, you can also leverage the IaaS self-service capabilities built into the Nutanix Prism management interface. You can work with each customer to define the necessary projects, quotas, and role assignments. For example, DB administrators might be allowed to deploy and manage DB instances but restricted from accessing other application services.

Ultimately, Calm stands to vastly expand on the service and self-service capabilities that IT can deliver to their end users, but as you may have noticed everything begins with blueprints. So, now, let’s talk about them.

## 5. Publishing Your Own Application Blueprints
[YouTube Video](https://youtu.be/ioY3RYzI_vI)

Blueprints are essentially recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a Blueprint is executed it results in an application.

Calm uses Services, Packages, Substrates, Deployments, and Application Profiles as building blocks for a blueprint. Together they fully define applications. By encoding these into a blueprint, Calm can understand the application as a whole and properly automate its lifecycle.

And as we discussed in the previous topic, being able to turn application deployment into an automated, repeatable activity can have a significant impact on an IT team’s productivity and efficiency.

This is why this lesson and the one after it are focused entirely on the centerpiece of Calm – application blueprints. In this lesson, we will lay the foundation for everything you need to know about blueprints: key concepts, process overviews, different elements of the Calm interface, and so on. At the end of this lesson, we will bring those concepts together into an exercise to create a single-VM blueprint.

Then, in the next lesson, we will recap some old concepts, introduce some advanced concepts, and tie them all together with a more complex blueprint – a multi-VM blueprint for a web server using a Linux VM.

So, since everything ties together to form the complete picture of application automation, before we move on, let’s quickly recap the Marketplace.

## 7. Recap: The Nutanix Marketplace
[YouTube Video](https://youtu.be/8AjFAcCb6u8)

As we discussed in the previous lesson, the Marketplace allows you to:

* View details of an application
* Publish applications for use by specific users and/or groups
* Control application state e.g. “Approved” or “Pending Approval”
* Carry out test deployments that ensure an applications functions as expected before publication

### Enabling Nutanix Marketplace Applications
To help you get started with one-click app deployment, Calm offers a collection of pre-seeded blueprints – these are essentially ready-to-use applications that address a number of common use cases.

However, by default, you will not see these applications in the Marketplace. To enable them, navigate to the Settings page in Calm, and click the Nutanix Marketplace Apps toggle.

## 9. Calm Blueprints: Overview
As we briefly discussed earlier, Blueprints are recipes for applications. Now let’s take a little time to explore what those recipes typically contain.

The eleven main components of a Calm Blueprint are:

1. Application Profiles
2. Services
3. Substrates
4. Application Profile Actions
5. System Defined Profile Actions
6. Custom Profile Actions
7. Service Actions
8. System Defined Service Actions
9. Custom Service Actions
10 Package Install/Uninstall
11. VM Pre-create/Post-create

Let’s go over each of these in a little more detail.

### Calm Blueprint Canvas

Application Profiles (number 1 in the image above) expose simple choices to your end users. These choices are often about where an application should run (AHV or AWS), but they can also be used for ‘t-shirt’ sizing (small or large), or a combination of the two (small AHV or large AHV or small AWS). You, as an IT operator or developer, should have a good grasp of the underlying differences of these choices, while abstracting that complexity from your end users.

Services (number 2 in the image) are logical entities exposed by an IP, which span all application profiles, and are managed by Calm. End users and services communicate amongst each other over a network via their exposed IPs and ports. Services are typically deployed based on a disk image that is managed by Prism Central. Take a moment to think back to previous lessons, and to the Image Management topic that we discussed. Services in Calm are one reason why it’s important to understand how to work with images in Prism Central.

Substrates (number 3 in the image) are a combination of the underlying cloud and the virtual machine instance. When the desired cloud is selected in the Calm UI, all of the fields required for creating a virtual machine instance on that particular cloud are displayed — the combination of all these fields make up a substrate. Substrates do not span application profiles, so it’s considered a best practice to name substrates as a combination of the service name and app profile name (DB_AHV or DB_AWS or DB_Small or DB_Large).

### Calm Application Profiles and Actions

Application Profile Actions (or Profile Actions for short, number 4 in the image above) are a set of operations that you can run on your application. For example, when launching a blueprint, the ‘Create’ action is run. If your application is not needed for a period of time, you could then run the ‘Stop’ action to gracefully stop your application. When you’re ready to resume work, running the ‘Start’ action will bring the app back up. There are two different types of profile actions, system defined profile actions and custom profile actions.

System Defined Profile Actions (5 in the image) are automatically created by Calm in every blueprint and underlying application. Since these are created for you, you cannot directly edit the tasks or the order of tasks within the canvas. However there are ways to control the order of operations, called Dependencies.

Custom Profile Actions (6 in the image) are created by the blueprint developer, and should be added whenever you need to expose a set of operations to the end user. Common custom profile actions are ‘Upgrade’, ‘Scale In’, and ‘Scale Out’. Since the actions are custom, individual tasks can be manually added in any order desired by the developer.

### Calm Service Actions

Service Actions (7 in the image above) are a set of operations to be run on an individual service. As we discussed earlier, services span application profiles, so their actions (and the operations underlying those actions) do as well. If you create a service action in the ‘AHV’ profile, the same service action will be available in the ‘AWS’ profile. As with profile actions, there are also two different types of service actions: system-defined service actions and custom service actions.

System Defined Service Actions (8 in the image) are automatically created by Calm in every blueprint and underlying application. While these actions cannot be individually invoked, they are called when the corresponding profile action is run. For instance, any operations placed under the ‘Stop’ service action will be run when an end user invokes the ‘Stop’ profile action.

Custom Service Actions (9 in the image) are created by the blueprint developer, and should be added for any repeatable operations within the blueprint, like a function definition in a programming language. For instance, during both the ‘Create’ and ‘Upgrade’ profile actions, the ‘App’ service should pull new code from a source code control repository. Rather than maintaining two separate tasks that perform the same set of operations, you could create a single custom service action which is then referenced in both the ‘Create’ and ‘Upgrade’ actions.

Package Install/Uninstall (10 in the image) are operations which are run during the ‘Create’ or ‘Delete’ profile actions. In other words, they are operations that run when a user first launches a blueprint, or finally deletes the entire application. Package Install and Uninstall are unique to each application profile, which means your tasks or the task contents can vary depending upon the underlying cloud or the app’s ‘t-shirt’ size.

VM Pre-create/Post-delete (11 in the image) are operations which are run before the substrate is created, or after it is deleted. A common use case for this is to make an API call into an IP Address Management (IPAM) system to get an IP for a to-be-created VM. Since other operations described so far are run after the substrate has already been created, VM pre-create is necessary if a property of your substrate relies on a 3rd party system.

## 11. Working with Calm Blueprints
[YouTube Video](https://youtu.be/JkJebVRaPEY)

Now we’re going to focus on creating blueprints themselves. Whenever you need to work with Blueprints, you’ll need to navigate to the Blueprints page of Calm

### Blueprints Page of Calm
As you can see, the options available to you are very similar to those that you’ll see on other pages in Calm. You can create, upload, filter, launch, download, delete, and clone blueprints from this page.

You’ll also see a table in the middle of the page that lists every available blueprint, as well as some basic information: the type, a description, the project it’s associated with, and so on. You can click the name of a blueprint to open the Blueprint Canvas screen, pictured below

The Blueprint Canvas screen is a complete view of your blueprint, consisting of all of the elements that we talked about earlier. Here, you can modify the configuration of a blueprint, publish, download, or launch it.

### Creating a Blueprint
Based on the type of application you intend to deploy, you will find yourself creating one of two different types of blueprints: single VM or multi-VM. And to create a blueprint, you simply need to click + Create Blueprint on the Blueprints page. There, you will see two options:

* Single VM Blueprint
* Multi-VM/Pod Blueprint

In this lesson, we will spend some time on single VM blueprints and follow up with an exercise that will allow you to create one. In the next lesson, we will look at multi-VM blueprints in detail.

## 14. Single VM Blueprints
[YouTube Video](https://youtu.be/Sq4qanmUTNc)
Like the name suggests, a single VM blueprint is a framework that you can use to create an instance, provision, and launch applications that require only a single VM. You can define the underlying infrastructure of the VM, application details, and actions that are carried out on a blueprint until the termination of the application.

### Types of Single VM Blueprints
The choices that you have when setting up your Providers extend to creating blueprints as well. You can create a single VM blueprint for Nutanix, VMware, AWS, Azure, and GCP.

### Demo: UI for Single VM Blueprints
Let’s walk you through the user interface for some of the creation steps.
[YouTube Walkthrough](https://youtu.be/gcToVM6H9ms)

In general, the process of setting up a single VM blueprint is similar irrespective of the infrastructure you choose to use. While details may vary, as we saw when creating Providers, there are four broad tasks involved in creating a single VM blueprint:

1. Updating blueprint settings
2. Providing VM details
3. Specifying VM configuration
4. (Optional) Configuring advanced options

### Blueprint Settings
Here, you’ll provide a name and a description for the project, and specify the project that it needs to be associated with.

### VM Details
On the VM Details page, you need to provide a name for the VM, choose the infrastructure it will run on, and specify an operating system. If you have already configured an environment as described in the previous lesson, you can simply click the Clone from environment link to duplicate your settings. That allows you to skip this step entirely, and proceed directly to the VM configuration page.

### VM Configuration
On the VM Configuration page, you will need to provide details about the VM itself, such as the number of vCPUs, cores per vCPU, memory, disks, network details, vGPUs, and so on. As you can see on the right of the screen, you will need to provide information in 7 different categories:

* General configuration
* Guest configuration
* Disks
* vGPUs
* Categories
* NICs
* Serial ports

Take note of the Categories step in this process and think back to earlier lessons where we discussed Categories in Prism Central — this is one example where you would apply any categories you may have set up at that time.

### (Optional) Configure Advanced Options
Finally, the last major task is to configure advanced options. This page allows you specify four additional areas for M provisioning:

* Provide credentials: SSH keys and Passwords
* Check the log on status of the VM after provisioning the blueprint
* Add pre-create and post-delete tasks in the blueprint
* Add packages and actions in the blueprint

Once you have provided all of the necessary information, review your settings and click Save. You will see your blueprint listed on the Blueprints page, and can then use it to model your application.
This is entirely optional and can be skipped if you do not have a need to update any of these settings.

## 16. Exercise - Create Single VM Blueprint
In this exercise, you will create a single VM blueprint and then download and launch the blueprint.

### Creating a Single VM Blueprint
[YouTube Video](https://youtu.be/qrOpxr4MgV4)

1. From the Prism Central tab in your browser, select the Entities menu > Services and click Calm.

2. Hover your mouse cursor over the icons at the far left of the browser to reveal the icon names. Click the Blueprints icon.

3. Click the + Create Blueprint drop-down menu and select Single VM Blueprint.

4. On the Create Single VM Blueprint page, use the following information to complete the fields:

* Name: Single-VM-BP
* Description: Single VM test for Calm
* Project: HybridCloudEngineer

5. Click VM Details >. Verify the following fields are set as defined below:

* Name: VM1
* Cloud: Nutanix
* Operating System: Linux

6. Directly below the Operating System field showing Linux, locate Clone from environment. Clicking this will clone/copy the VM configuration from the Environments section of the HybridCloudEngineer project to your VM configuration in this blueprint. The HybridCloudEngineer project VM configuration is the same as the Test-Project project you built in a previous exercise. Click Clone from environment.

7. The HybridCloudEngineer project environment VM configuration has now been copied to this blueprint. Click VM Configuration > and verify the VM settings using the following information:

* vCPUs: 1
* Cores per vCPU: 1
* Memory (GiB): 2

Guest Customization Script field:

#cloud-config users:

* name: @@{superuser.username}@@ ssh-authorized-keys:
* @@{superuser.public_key}@@ sudo: ['ALL=(ALL) NOPASSWD:ALL']
* Type: Disk
* Bus Type: SCSI
* Operation: Clone from Image Service
* Image: CentOS-8-GenericCloud-8.2.2004-20200611.2.x86_64.qcow2
* Bootable: Check box selected
* NIC 1: default-net

8. Some settings are left to the administrators discretion as the settings may be unique to the deployment environment. Click the radio button next to Dynamic in the NIC 1 section for default-net.

9. Click Advanced Options at the bottom of the page. Scroll to the top of the display, click Add/Edit Credentials.

10. In the Credentials dialog box, click + Add Credentials. Use the following information to configure the new credential:

* Credential Name: superuser
* Username: centos
* Secret Type: SSH Private Key
* SSH Private Key: Click the arrow coming out of the box, navigate to C:\cygwin64\workspace.ssh\id_rsa and select Open. Ensure the inserted key text has the private key, -----BEGIN RSA PRIVATE KEY----- shown at the top.

11. Click Done.

12. Under CONNECTIONS, click the check box next to, Check log-in upon create and choose superuser from the Credentials pull-down menu.

13. Scroll to the bottom of the page and click Save.

### Downloading and Launching the Blueprint
[YouTube Video](https://youtu.be/fu10nUn0yzI)

1. Select the Entities menu > Services and click Calm.

2. Hover your mouse cursor over the icons at the far left of the browser. Click the Blueprints icon, second from the top.

3. Click your Single-VM-BP blueprint then click Download at the upper right.

4. In the Download Blueprint dialog box, click the check box for Do you want to include credentials and secrets in the blueprint.

5. Type nutanix/4u in the Enter Passphrase box and click Continue to save the file.

6. Open Windows Explorer / File Manager on your Desktop task bar and open the Downloads folder. Copy the Single-VM-BP JSON file to the Workspace folder on the Windows Desktop to make it persistent.

7. Download all the files in your Workspace folder to your personal computer by right-clicking each file and choosing Download with Frame. This will save your files to your local systems default downloads folder. Be sure to get your SSH Keys in the .ssh folder.

8. From the Calm blueprint page, click Launch at the upper right. In the new view, you will see three tabs, with the Profile Configuration automatically selected. Type Single-VM-App in the Name of the Application field.

9. Click Create.

10. When the view changes and you see PROVISIONING, click Audit. Expand the provisioning view by clicking the turndown arrow to the left of Create. Continue to expand each new component as it appears, to follow the provisioning progress to completion.

11. Verify that Calm was able to log into the VM during the post-provisioning steps by confirming a Green circle around the Service1 - Check Login step, under the Service1 - Substrate Create tree.

12. Once the application is in a RUNNING state, click the Entities menu and go to Infrastructure > VMs. You will see your **Single-VM-BP” blueprint VM running.

13. Return to Entities > Services > Calm > Applications > Single-VM-App. Select the Manage tab.

14. Hover your cursor over the Stop row and click the arrow.

15. In the Run Action: Stop dialog box, click Run to confirm stopping the VM.

16. The Application page should now show STOPPING at the top.

17. When STOPPING changes to STOPPED, go back to Entities > Infrastructure > VMs and you should see the Single-VM-BP blueprint VM in a powered off state.

## 18. Multi-VM Blueprints
[YouTube Video](https://youtu.be/cWqGfTL4tz0)

A multi-VM blueprint is a framework that you can use to create an instance, provision, and launch applications that require multiple VMs. Just like single VM blueprints, you can define the underlying infrastructure of the VMs, application details, and actions that are carried out on a blueprint until the termination of the application.

And, once again, you can choose which infrastructure to leverage when creating a multi-VM blueprint, with Nutanix, VMware, AWS, Azure, and GCP available as options.

### Creating a Multi-VM Blueprint
Creating a multi-VM blueprint is a little more involved than a single VM blueprint. The process involves 6 major tasks, which are:

1. Adding a service
2. Configuring the VM, package, and service for your provider
3. Setting up service dependencies
4. Adding and configuring an application profile
5. (Optional) Adding and configuring scale out and scale in
6. Creating an action

Multi-VM blueprints are discussed in much more detail in the next lesson, but it’s helpful for you to have an overview of them now.

## 19. Managing Blueprints
[YouTube Video](https://youtu.be/I2WrDc4mVRE)

There are a number of tasks that you can perform after you have a blueprint set up and saved. In no particular order, there are 10 tasks that you should be aware of in the context of managing blueprints:

* Publishing blueprints
* Launching blueprints
* Uploading blueprints
* Downloading blueprints
* Configuring blueprints
* Viewing blueprints
* Editing blueprints
* Deleting blueprints
* Viewing blueprint errors
* Recovering deleted blueprints

While most of these are self-explanatory, there are a few details worth noting here. Configuring a blueprint, like most things in Calm, involves filling out a form that requires a name, a description, downloadable image configuration, and so on.

### Configuring a Blueprint

Viewing blueprint errors is relevant only if a blueprint has been configured incorrectly, or if an unforeseen issue occurred during development. If you receive an error when saving or publishing a blueprint, look for an exclamation mark icon in the UI, beside the undo and redo buttons. You can click the icon to view details of each error and take corrective action as needed.

### Warnings shown during blueprint deployment

After you configure a blueprint, you can publish, unpublish, launch, or delete it.

Publishing a blueprint allows you to make the blueprint available in the Marketplace, so that other users can use it. This requires administrator approval. Unpublishing a blueprint allows you to remove the blueprint from the Marketplace.

And finally, launching a blueprint allows you to deploy the application associated with the blueprint and start using it.

[Blueprint Management](https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Calm-Admin-Operations-Guide-v3_0_0:nuc-nucalm-blueprint-management-c.html)

## Working with Marketplace Manager
[YouTube Video](https://youtu.be/YQ-1RjGyBvE)

The last major topic that we’re going to discuss in this lesson is working with the Marketplace Manager. Like the Marketplace itself, the Marketplace Manager has its own page in Calm.

It allows you to manage the list of custom blueprints and the marketplace application blueprints. You can view the list of published blueprints under the Marketplace Blueprints tab and the list of blueprints that are pending for approval under the Approval Pending tab. The Marketplace Manager page provides the following details about a blueprint:

* Name of the blueprint
* Name of the entity who created the blueprint
* The number of projects for which the blueprint is available
* The category of the blueprint
* Status of the blueprint

After you select a blueprint, the inspector panel displays the operations you can perform on the selected blueprint. The inspector panel also displays a brief overview of the blueprint and allows you to select the category and projects for the available blueprint.

Broadly, there are three operations that you are likely to perform on the Marketplace Manager page: publishing a blueprint, unpublishing a blueprint, and deleting an unpublished blueprint.

### Publishing a Blueprint
It’s worth noting that, if your blueprint is properly set up, publishing, unpublishing and deleting don’t involve more than one or two clicks. To publish a blueprint, for example, you simply need to:

Navigate to the Approval Pending tab
1. Select an unpublished blueprint from the list
2. Click Approve
3. Assign the blueprint to a Category
4. Click Publish

### Unpublishing a Blueprint
Unpublishing a blueprint removes it from the Marketplace, but does not delete the blueprint itself. It can also be republished if there is a need.

To unpublish a blueprint:

1. On the Marketplace Blueprints tab, select a blueprint from the list
2. Click Unpublish

### Deleting a Blueprint
Deleting a blueprint removes the blueprint itself, and the operation can only be performed on an unpublished blueprint. As you can see in the previous figure, you can only unpublish or launch a published blueprint.

However, with an unpublished blueprint, as shown in the figure below, you will see options to either publish the blueprint or delete it. Simply click the Delete button to remove the blueprint.

## 24. Exercise: Publish Blueprint to Marketplace
In this exercise, you will:

* Publish your single VM blueprint to the marketplace. [YouTube Video](https://youtu.be/_7rl8c0Us4A)
* Launch your blueprint from the marketplace. [YouTube Video](https://youtu.be/Vz4PzWdZQ_A)
* Unpublish and delete your blueprint. [YouTube Video](https://youtu.be/PjIUOcXHwfI)

We’ll walk through the steps together.

### Publishing a Single VM Blueprint to the Marketplace
1. On the Prism Central tab in your browser, select the Entities menu, then Services and click Calm.

2. Select the Blueprints icon.

3. If Single-VM-BP is present, click on the blueprint and skip to step 8. If the blueprint is not present, this means you received a new cluster deployment and will need to upload your saved blueprint. Continue with the following steps.

4. Click Upload Blueprint and browse to the Workspace folder on your desktop and select your saved Single-VM-BP JSON file. Click Open.

5. In the Upload Blueprint dialog box, select HybridCloudEngineer in the Project pull-down menu and type nutanix/4u in the Passphrase field. Click Upload. This will place you into the Single-VM-BP blueprint you created and saved in a previous exercise.

6. Click VM Details and in the VM Details page, click VM Configuration.

7. From the VM Configuration page, locate the NICs section and under NIC1, Private IP, click the Dynamic radio button. Click Save.

8. On your Single-VM-BP blueprint page, click Publish in the upper right corner of the browser window.

9. In the Publish Blueprint dialog box, verify Publish as a, is set to New Marketplace Blueprint and type 1.0.0 in the Initial Version field.

The name should default to Single-VM-BPand the Description should default to Single VM test for Calm.

10. Click Submit for Approval.

11. Hover your cursor over the icons to the far left of the browser. Click Marketplace Manager icon (second icon from the bottom).

12. At the top, click the Approval Pending tab and click Single-VM-BP. A panel will appear on the right-side of the browser window.

13. Select HybridCloudEngineer in the Project Shared With drop-down menu.

14. Click the Approve button (box with a checkmark). The blueprint will be removed from the Approval Pending tab and placed in the Marketplace Blueprints tab.

15. At the top, click the Marketplace Blueprints tab. If you do not see your Single-VM-BP blueprint in the list, enter *single in the search field and press Enter. Select the checkbox next to the Single-VM-BP blueprint. Observe the current status of your blueprint, which should be Accepted**.

16. On the right-side of the browser window, verify HybridCloudEngineer is selected in the Projects Shared With drop-down menu and click Publish.

17. The blueprint Status column should now read Published.

### Launching a Blueprint from the Marketplace
1. Select the Entities menu, then Services and click Calm.

2. Click the Marketplace icon in the left column.

3. Click Single-VM-BP blueprint and click Launch.

4. In the Launch dialog box, select the HybridCloudEngineer project if needed and click Launch if needed.

5. Type Single-MP-App (MP=Marketplace) in the Name of the Application field and click Create.

6. When the view changes and you see PROVISIONING, click Audit. Expand the provisioning view. Continue to expand each new component as it appears, to follow the provisioning progress to completion.

7. Verify that Calm can login to the VM during the post-provisioning steps by confirming a Green circle around the Check Login step, under the Service1 - Substrate Create tree.

8. Go to Entities > Infrastructure > VMs and verify your VMs. You should see the VM from the Single-VM-App application launched in an earlier exercise, in a powered off state and the VM launched with the Single-MP-App application, in a powered on state.

### Deleting and Unpublishing a Blueprint
1. Go to Entities > Infrastructure > VMs and review the current VMs.

2. Return to Entities > Services and click Calm.

3. You should be on the Application page (default) and you should see the Single-VM-App and Single-MP-App applications listed.

4. Select the Single-MP-App check box.

5. Select Delete from the Action drop-down menu.

6. Click Confirm in the Delete Application dialog box.

7. You will be automatically switched to the Audit page. Monitor the delete process.

8. In the left column, click the Applications icon. Repeat steps 3-6 for Single-VM-App.

9. Click the Marketplace Manager icon on the left-side of your browser window (second from bottom) and enter single in the search field. Press Enter. Select the Single-VM-BP blueprint and in the right side panel, click Unpublish.

The Status of the Single-VM-BP will change to Accepted.

10. Click the trash can icon and click Delete in the Confirm Delete dialog box.

11. Click the Blueprints icon on the far left of the browser and click the check box next to Single-VM-BP blueprint.

12. Select Delete from the Action drop-down menu and click Delete in the Confirm Delete dialog box.

## 27. Lesson 3 Conclusion

[YouTube Video](https://youtu.be/pQmnAEU36vs)

Now we come to the end of this lesson. Before we move on, let’s quickly recap some of the highlights of this lesson.

Blueprints are essentially recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a Blueprint is executed it results in an application.

Calm uses Services, Packages, Substrates, Deployments, and Application Profiles as building blocks for a blueprint. Together they fully define applications. By encoding these into a blueprint, Calm can understand the application as a whole and properly automate its lifecycle.

Blueprints are also incredibly important. The ability to turn an application into a repeatable, automated blueprint offer enterprises a number of benefits: greater agility while minimizing human error; broader self-service capabilities while allowing IT to retain centralized control; the ability to modernize app development by pairing Calm with a certified Kubernetes solution; and the ability to automate provisioning across multi-cloud architectures from a single management interface.

You can create two types of blueprints: single-VM and multi-VM. A single-VM blueprint is a framework that you can use to create an instance, provision, and launch applications that require a single VM. A multi-VM blueprint is a framework for applications that require multiple VMs.

Blueprints can be downloaded, uploaded, viewed, configured, edited, deleted, published, unpublished, and launched. Publishing, unpublishing, and deleting blueprints involves using the Marketplace Manager, which is what determines whether or not your blueprints are available to users of the Nutanix Marketplace.

If you’re comfortable with these concepts, you’ll find yourself in a good position to delve deeper into Calm. So, in the next lesson, we’ll explore blueprints even further, by discussing multi-VM blueprints and how you can use them for more complex, sophisticated automation tasks
