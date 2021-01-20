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

## 2. Big Picture
[YouTube Video](https://youtu.be/e5hiljP9fjw)

Before we move on with this lesson, which is the culmination of everything you have learned so far, let’s take a moment to circle back to the beginning and see how everything ties together.

As you may remember, we spoke about how businesses constantly seek to improve overall IT agility and responsiveness to enable more rapid innovation. However, application development and delivery is growing in complexity, making it challenging for teams to keep up with increasing expectations to move faster.

As a result, when thinking about the applications that drive and support a business, there are a number of important factors to consider about the applications themselves, as well as their deployment and maintenance:

* Today’s mission critical and complex business processes need a plethora of applications to work in harmony
* The growing number of interdependent components, and reliance on manual processes, lead to frequent unplanned downtime due to errors
* Knowledge silos force everyone to work in a partial state of isolation, leading to a lack of productivity in the business
* Hybrid clouds introduce inoperable and disparate platforms, adding significant management challenges

Hyperconverged solutions provide a much simpler infrastructure that scales linearly and radically reduces the complexity inherent to traditional data center architectures. But to truly transform how IT teams can support the business, a new approach that automates all aspects of how applications are created, consumed and governed is needed.

Melding advanced application-level orchestration with a full cloud-driven infrastructure stack can achieve repeatable, simple and automated management of applications – across a variety of environments including private and public clouds.

And as we’ve seen in this course, that advanced application-level orchestration is provided by Nutanix Calm.

Calm provides a single pane for application automation and lifecycle management for Nutanix, VMWare, and public clouds, as part of the Nutanix Enterprise Cloud Platform.

Calm orchestrates the provisioning, scaling and management of applications across multiple environments to make the entire IT infrastructure more agile and application centric.

And this lesson illustrates how the various components of Calm come together to address the needs of enterprise applications. Using a three-tier web application as our example, you will explore how Calm delivers app-centric automation and lifecycle management, policy-based governance, self-service provisioning to any enterprise in need of these capabilities.

## 3. Quiz: Big Picture
Common Challenges when working with enterprises applications
* Mission critical and complex business processes need a plethora of applications to work in harmony
* Knowledge silos lead to a lack of productivity in the business

## 5. When and When Not to Use Calm Automation
After everything we’ve seen, a good question to be asking yourself is ‘When am I likely to use Calm?’. Helpfully, the answer is remarkably straightforward.

Much of Calm’s power lies in its universality: whenever you need to work with an application, whether you’re deploying it in a single cloud or multiple clouds, if there’s a need for automation and orchestration Calm will be useful to you.

When you’re considering whether or not to use Calm for an application deployment, there are three key factors that you need to consider.

### How the application will be deployed
* Will it be on-prem?
* Will it be on the cloud?
* Will it be both on-prem and on the cloud?
* Will part of the application be on-prem and part of it on the cloud?

### The users of the application
* Is it beneficial for users to be able to deploy the application without intervention from IT?
* Will this application be deployed frequently?
* Is the application likely to be deployed multiple times?

### The application itself
* Is there value in automating deployment?
* Is there value in automating management?
* Is there value in making application deployment consistent and repeatable?

If the answer to a good number of these questions is yes, then you have a good use case for Calm on your hands. And, as we’ve learned so far — and will see in this lesson as well — irrespective of the nature and the complexity of the application itself, Calm brings simplicity and ease of use to both your experience, as IT, and to your users’ experience as well.


## 6. MySQL Database Server Administration
[YouTube Video](https://youtu.be/cWy8Zlinvpw)

The MySQL database upholds the standard install and maintenance command tools:

* ```sudo yum install -y mysqld```
* ```sudo systemctl {enable,start,status,stop,restart} mysqld```

The {1,2,3} list is shorthand for all of the standard operations you can choose to perform on most services with systemctl.

For Firewall and security group access, mysqld listens on TCP port 3306.

The configuration file is /etc/my.cnf

For troubleshooting database logs:

* ```sudo journalctl -f -u mysqld```
* ```sudo tail /var/log/mysqld.log```

The configuration of data, users, and operations inside the database requires the database to be started, then administered via the mysql client. Databases contain their own users, credentials, and role permissions. Everything inside the database is independent of operating system user credentials, so the database user root is not the same as Linux user root. mysqldump is included in the MySQL package for creating a database backup.

Accessing MySQL from the command line requires database user credentials, e.g.:

* ```mysql --user=root --password=example```
* ```mysqldump --all-databases --user=root --password=example```

After authenticating with database credentials, commands can be issued. The standard for database commands is SQL: Structured Query Language. While MySQL can deviate from the standard and vary between different MySQL major releases, the majority of SQL is compatible across most different database and versions.

You will see the automation scripts leverage mysql command to authenticate as database user root and then perform SQL operations. Those operations will include creating users, granting roles to users, and creating database structures.

Database structures are organized as: databases and tables, which are addressed by database_name.table_name. You can think of a database as a spreadsheet and a database table as a tab or layer in that spreadsheet. So a database is a collection of tables.

Any application not on the database VM can authenticate with a database user over the network and issue SQL commands to interact with a specific database and database table. The web application will need these pieces of information: a database server address, database user and password, and a database name and table. The PHP language database MySQL driver will use the default MySQL TCP port, so it is omitted unless there is a need for custom configuration.

A database structure, called a database schema, defines the types of data it will store. Building on the spreadsheet example, think of a database table as the different columns with data formats in a spreadsheet. Finally, the data is populated into the table via SQL statements such as INSERT, UPDATE, and DELETE. This can be thought of as editing the data cells in spreadsheet rows.

## 7. Exercise - Add a Database Service
[YouTube Video](https://youtu.be/jOLJ0MB56pU)

In this exercise, you will add a Database service to your WebApplication Multi-VM blueprint, becoming a “three-tier” web application by performing these steps:

1. Add application profile variables for database configuration to be used by installation shell tasks and the WebServer application.

2. Add a MySQL VM and configure CentOS with cloud-init and shell tasks.

3. Install MySQL and then configure a database, change the database root user password, and set up a web application table, user, and permissions.

Let’s walk through the steps together. Again, a video walkthrough is offered on the next page.

### Configure the Blueprint
1. Select the Entities menu, then Services and click Calm.

2. Select the Blueprints icon in the left column.

3. If WebApplication is present, click on the blueprint and skip to step 8. If the blueprint is not present, this means you received a new cluster deployment and will need to upload your saved blueprint.

4. Click Upload Blueprint and browse to the Workspace folder on your desktop and select your saved WebApplication blueprint JSON file. Click Open.

5. Select HybridCloudEngineer in the Project pull-down menu and type nutanix/4u in the Passphrase field. Click Upload. This will place you into the WebApplication blueprint you created and saved in the previous exercise.

6. On the blueprint canvas, click WebServer in the WebServerAHV service and then the VM tab in the right configuration panel, scroll down to NETWORK ADAPTERS (NICS) and click + to add a NIC:

* Under NIC 1 click the dropdown and select default-net.
* Select Dynamic next to Private IP.
* Click Save.

7. On the blueprint canvas, click HAProxy in the HAProxyAHV service and then the VM tab in the right configuration panel, scroll down to NETWORK ADAPTERS (NICS) and click + to add a NIC:

* Under NIC 1 click the drop-down and select default-net.
* Select Dynamic next to Private IP.
* Click Save.

### Configure MySQL Database
8. If needed, expand the left hand Application Overview palette to full canvas height by clicking on the top bar expand icon. Choose the Nutanix application profile, then on the left side configuration panel, add the following four variables, click + to add each instance:

Note: if you make a mistake, sometimes it is easier to select the triple dot menu next to each variable, choose delete, and start over. You can reveal and hide the variable details by clicking the turn-down arrow as well as reorder the variables by clicking and dragging the handle to the left of the variable name.
```
Variable Name	Data Type	Value	Secret	Runtime
MYSQL_APP_USER	String	webuser	Unchecked	Skip (grey icon)
MYSQL_PASSWORD	String	nutanix/4u	Yes, click the check box	Click (blue icon)
DATABASE_NAME	String	webapp	Unchecked	Skip (grey icon)
DATABASE_TABLE	String	visitors	Unchecked	Skip (grey icon)
```

9. Edit the MYSQL_PASSWORD variable to add additional validation, click the MYSQL_PASSWORD variable turn down arrow to reveal the properties. Click “Show Additional Options” and add:

* Description: “MySQL low password security requirements are 8 or more characters with at least 1 uppercase character.”
* Mark this variable mandatory: Checkbox

10. Select + next to Service in the Application Overview window on the bottom left. A new service will be added to the blueprint canvas. You can drag and drop the new service to a clear area of the canvas.

11. The right configuration pane will populate information for the new Service3 service. Select the VM tab and enter in the following information:

* Service Name: MySQL
* Name: MySQLAHV
* Cloud: Nutanix
* Operating System: Linux

12. Click Clone from environment to populate the VM configuration from the project. Verify the settings using the following table:

* VM Name: MYSQL-@@{calm_time}@@
* vCPUs: 1
* Cores per vCPU: 1
* Memory (GiB): 2
* Guest Customization: Check box selected
* Type: Cloud-init
* Script: CloudInit script shown
* Device Type: Disk
* Device Bus: SCSI
* Operation: Clone from Image Service
* Image: CentOS_8_Cloud
* Bootable: Select check box
* NETWORK ADAPTERS (NICS): NIC 1 has default-net selected.

13. Under NETWORK ADAPTERS (NICS), next to Private IP, click the radio button next to Dynamic.

14. Under CONNECTION, ensure the check box next to Check log-in upon create is selected. For the Credentials menu, select superuser.

15. Click Save at the top of the page. If any errors or warnings exist, hover your cursor over the red exclamation mark to see what remediation steps are required. Warnings about variables will be resolved in a later step.

16. Select Download to save your blueprint to your workstation. Check the box for Downloading credentials and type the passphrase nutanix/4u.

17. Click Continue and save the file. Go to the Downloads folder and copy the file to your Workspace folder. Only keep the latest copy. Your WebApplication blueprint is now saved up to this point for this exercise.

18. On the left side, for the MySQL service, click on the turn-down arrow to reveal the service actions.

19. Choose the Restart service action. Note that the service on the blueprint canvas changes to display the Restart action, which is empty.

20. On your blueprint canvas, select + Task to add a task in the MySQL service Restart service action and fill out the following fields in the configuration panel:

* Task Name: MySQL_Restart
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the MySQL_ServiceAction_Restart.txt file and click Open. This will upload the script to the Script box.

21. On the left side, for the MySQL service, choose the Start service action.

22. On your blueprint canvas, select + Action to add a Start service action in the MySQL service and fill out the following fields in the configuration panel:

* Task Name: Leave blank; this will be automatically populated.
* Service Actions: Choose the Restart action.

Note: This reuses the existing Restart service action, because for the MySQL database, these service actions are effectively the same operation.

23. On the left side, for the MySQL service, choose the Stop service action.

24. On your blueprint canvas, select + Task to add a Stop service action in the WebServer service and fill out the following fields in the configuration panel:

* Task Name: MySQL_Stop
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the MySQL_ServiceAction_Stop.txt file and click Open. This will upload the script to the Script box.

25. On the blueprint canvas, click on the “MySQL” service white box to display the VM Service Configuration panel on the right and select the Package tab next to VM.

26. Type MySQL_Package under Package Name and click Configure Install.

27. In the blueprint canvas, you will see Package Install appear within the MySQL service you have created.

Click + Task and configure the following in the right-hand Configuration panel.

If you previously saved this task to the library, provide just the Task Name and Type as specified below, then click the Browse Library button to source the Linux_OS_Update task and save a few steps. If not found, provide all of the task configuration:

* Task Name: Linux_OS_Update
* Type: Execute
* Script Type: Shell -
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. 

Navigate to C:\Scripts. Select the Linux_OS_Update.txt file and click Open. This will upload the script to the Script box.

28. Select + Task to add a second task and configure the following in the right-hand Configuration panel:

* Task Name: MySQL_Install
* Type: Execute
* Script Type: Shell
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the MySQL_Install.txt file and click Open. This will upload the script to the Script box.

29. Scroll to the top of the Configuration panel on the right and select Package next to VM.

30. Select MySQL in the MySQLAHV service in the blueprint canvas and select the Package tab in the Configuration Panel.

31. Click Configure uninstall.

32. Select + Task in the MySQLAHV service and fill out the following fields in the Configuration Panel:

* Task Name: MySQL_Uninstall
* Type: Execute
* Script Type: Shell
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the MySQL_Uninstall.txt file and click Open. This will upload the script to the Script box.

33. On the blueprint canvas, click the WebServerAHV service, find the 2Tier_Webapp task (Packages on Left Pane), update the task to reflect the new name and upload the new WebServer_3Tier_Webapp.txt script.

* Task Name: 3Tier_Webapp
* Type: Execute
* Script Type: Shell
* Endpoint (Optional): Skip; leave blank
* Credential: superuser
* Script: In the upper right corner of the Script box, hover your mouse over the icons and click Upload script. Navigate to C:\Scripts. Select the WebServer_3Tier_Webapp.txt file and click Open. This will upload the script to the Script box.

34. Select Save.

35. Select Download to save your blueprint to your workstation. Check the box for Downloading credentials and type the passphrase nutanix/4u. Click Continue and save the file. Go to the Downloads folder and copy the file to your Workspace folder. Only keep the latest copy. Your WebApplication blueprint is now saved up to this point for this exercise. Also download to your local computer into the Udacity-Class folder.
