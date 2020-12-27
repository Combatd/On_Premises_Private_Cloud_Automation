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

### The Big Picture
In your previous studies about modern private cloud infrastructure, you learned how to operate VM workloads on a single Nutanix cluster with the AHV hypervisor. When you have more than one Nutanix cluster, management can become split and uncoordinated between each cluster. You must reproduce your work in each cluster to have a consistent configuration, governance policy, and resources. The on-premise management problem compounds quickly when you have multiple Nutanix clusters with different hypervisors, as many of our customers do! Furthermore, the public cloud typically represents even further fragmentation as a separate silo for IT governance, operations, and security, so we will address hybrid cloud management in a later course.

In this first lesson of this course, we'll introduce you to the advanced version of the Prism control plane, which manages multiple clusters and provides additional facilities across those clusters, allowing management at scale. Nutanix Prism Central unites management across all different types of Nutanix clusters and their workloads, from a single pane of glass preventing the need for multiple consoles. Rather than learn about all of the capabilities and features of Prism Central, we will focus on governance with projects and roles, AHV VM image management, and Calm automation.
