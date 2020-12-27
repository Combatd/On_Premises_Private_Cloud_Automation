# On_Premises_Private_Cloud_Automation
Nutanix Private Cloud Training for SaaS 3 Tier Web Architecture - Software as a Service

## Project - Private Cloud SaaS: Three-Tier Web Application
In the project at the end of the On Premises Private Cloud Automation course, I will:

* Create a three-tier web application blueprint that satisfies the IaaS business requirements for self-service private cloud deployment and security scenarios.
* Enhance the blueprint to provide PaaS by configuring the web application and creating web-tier scaling. Test the web application works by confirming scale-out load balancing across the web tier and database write updates.
* Enhance the blueprint to provide an action to update the database password and update the web application to use the new password, achieving a SaaS-like experience for developers with delegated, post deployment operations. Test the web application works with the new password.

## Course Overview
In this course, we will cover various tools and features that Nutanix provides to eliminate the tedious, time-consuming process of manually operating parts of the cloud. We will walk you through how Nutanix Prism and Nutanix Calm increase visibility and eliminate IT intervention in performing repetitive, laborious tasks.

We will discuss how Nutanix Prism helps you manage multiple clusters and workloads. We will also illustrate how Nutanix Calm delivers simple, repeatable, and automated management of application creation, consumption, and governance. We have also included demo videos explaining these features and processes in the Nutanix environment.

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
