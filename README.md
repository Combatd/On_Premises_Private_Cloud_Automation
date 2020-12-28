# On_Premises_Private_Cloud_Automation
Nutanix Private Cloud Training for SaaS 3 Tier Web Architecture - Software as a Service

## Project - Private Cloud SaaS: Three-Tier Web Application
In the project at the end of the On Premises Private Cloud Automation course, I will:

* Create a three-tier web application blueprint that satisfies the IaaS business requirements for self-service private cloud deployment and security scenarios.
* Enhance the blueprint to provide PaaS by configuring the web application and creating web-tier scaling. Test the web application works by confirming scale-out load balancing across the web tier and database write updates.
* Enhance the blueprint to provide an action to update the database password and update the web application to use the new password, achieving a SaaS-like experience for developers with delegated, post deployment operations. Test the web application works with the new password.

## Lesson 1 Overview - Managing Multiple Clusters and Workspaces
In this course, we will cover various tools and features that Nutanix provides to eliminate the tedious, time-consuming process of manually operating parts of the cloud. We will walk you through how Nutanix Prism and Nutanix Calm increase visibility and eliminate IT intervention in performing repetitive, laborious tasks.

We will discuss how Nutanix Prism helps you manage multiple clusters and workloads. We will also illustrate how Nutanix Calm delivers simple, repeatable, and automated management of application creation, consumption, and governance. We have also included demo videos explaining these features and processes in the Nutanix environment.

## Glossary of Key Terms in this Lesson

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
