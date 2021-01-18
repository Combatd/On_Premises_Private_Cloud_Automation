# Lesson 5: Calm Automation for a 3-tier Web Application

## 1. Lesson Overview
[YouTube Video](https://youtu.be/hCh1TyRNIKg)

In this lesson, the final lesson of this course, we’re going to bring everything together. So far, we have focused on deepening your understanding of the various components of Calm.

We began by discussing Prism Central, and how some Prism Central capabilities tie directly into Calm. Examples of these interrelated features are:

* How Prism Central Role Based Access Control (RBAC) feeds into Calm roles
* How image management in Prism supports service definitions in Calm

Then we moved on to Calm itself. We explored several major Calm features and took a close look at their UI elements, as well as the ways in which you would typically interact with these features. So far, we’ve gone into detail about:

* Providers: Providers are cloud service providers, bare-metals, or existing machines that you can use to deploy, monitor, and govern your applications. Essentially, configuring a provider provides the required authorization for Calm to manage your applications using the provider’s virtualization resources.
* Projects: A project defines a set of Active Directory groups with a common set of requirements or a common structure and function, such as a team of engineers collaborating on a product. The project also specifies the roles to associate with its members, networks that they can use, infrastructure to deploy onto, and (optionally) usage limits on infrastructure resources. You can also define the environment associated with a project, in case you want to publish the applications into the Marketplace.
* Role-Based Access Control (RBAC): RBAC lets you define different roles in an organization and assign permissions accordingly. Within Calm, RBAC enables organizations to control who can perform specific actions.
* Blueprints: Blueprints are recipes for applications. These recipes encompass application architecture and Infrastructure choices, provisioning and deployment steps, application binaries, command steps, monitoring endpoints, remediation steps, licensing and monetization, and policies. Every time a Blueprint is executed it results in an application deployment, these workloads can be managed from the Applications menu.
* The Marketplace: The Marketplace is a common platform for both the publisher and the consumer, and provides you with the ability to provision an application instantly. It provides a set of pre-seeded application Blueprints that are available for you to use.
* Application Profiles: Application Profiles expose simple choices to your end users. These choices are often about where an application should run (AHV or AWS). They can also be used for ‘t-shirt’ sizing (small or large), or a combination of location and sizing (small AHV or large AHV or small AWS).
* Services: Services are logical entities exposed by an IP that span all application profiles and are managed by Calm. End users and services communicate with each other over a network using their exposed IPs and ports.
* Substrates: Substrates are combinations of the underlying cloud and the VM instance. When you select the desired cloud in the Calm UI, all the fields required to create a VM instance on that particular cloud are displayed. The combination of these fields is a substrate.
* Service Actions: Services Actions are a set of operations that you can run on your application. For example, when launching a blueprint, the ‘Create’ action is run. If your application is not needed for a period of time, you could then run the ‘Stop’ action to gracefully stop your application.
* Variables: The properties such as IP addresses, DNS names, and instance IDs that are associated with the services provisioned in blueprints are called variables. They can be static, provided at run time, or generated during blueprint or action runs.
* Macros: Macros enable you to access the value of variables and properties set on entities, and help you make generic scripts and create reusable workflows.

Each of these features represents an essential element of Calm’s development workflow and overall application lifecycle.

And in this lesson, we are going to bring all of this knowledge together. We are going to use Calm’s various capabilities to create a web server application and understand — from a real-world development perspective — what Calm is really capable of.

To achieve a three tier web application, we will be discussing:

* Databases
* Calm Orchestration for order of operations across dependent services
* Advanced Calm Actions, in a little more detail than we have in previous lessons