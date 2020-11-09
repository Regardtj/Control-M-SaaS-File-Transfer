# Control-M SaaS: Managed File Transfer job templates

# Introduction:

The intention of this repository is to provide job templates relevant to the Control-M Managed File transfer solution specifically running on the Control-M SaaS platform.
By providing these templates, it will make it easier for the Solution Engineers to use these templates in building Solution Demo’s for their customers.

![Screenshot 2020-11-06 at 15 04 44](https://user-images.githubusercontent.com/51226604/98387167-fbd97a00-2048-11eb-8e26-ef7e877ac161.png)

# Disclaimer
This application is not linked to or based on any particular business at all. The contents are all fictional and have been fabricated to be used for demonstration purposes only. 

# Control-M Managed File Transfer:

Every modern business depends on the movement of files. Whether it be between internal applications, systems of record, mainframes, external business partners, or cloud platforms, this is a mission-critical requirement that practically every single business process depends on to succeed.  
Nonetheless, despite how important this is, many businesses still manage file transfers independently from their business workflows and depend on custom integrations, scripting and manual interventions to synchronise them. 
Control-M Managed File Transfer puts you in control of file transfers with an intuitive graphical user interface to guide you through job definitions and ensure transfers are associated with comprehensive automated workflows. 
You get instant visibility into the status of internal and external file transfers with a dashboard view, enhanced security with encryption options, and reduced risk of downtime with automated monitoring and recovery features. 

# Environment:

For this environment the templates is intended to be run on the Control-M SaaS platform with an agent that needs to be created with a working Control-M Managed File Transfer CM installed and working connection profiles.
Control-M SaaS will be the is the key in orchestrating the File Transfer applications and providing business critical information around the transfer status and insight to business users on the overall file transfers

# Requirements:

1. Access to Control-M SaaS platform
2. Access to an Control-M Agent on OS of choice
3. Control-M for Managed File Transfer CM installed on this agent
4. At least one working connection profile for the relevant template that will be used

<img width="1674" alt="Screenshot 2020-11-06 at 16 18 02" src="https://user-images.githubusercontent.com/51226604/98389235-ae124100-204b-11eb-81a4-25617f319f39.png">

# Plugin for Managed File Transfer:

# Overview
Managed File Transfer (MFT) plugin is an FTP/SFTP client and server solution that enables you to watch files and transfer files in your organisation. It supports accessing a local file system, Amazon or compatible S3 and SFTP or FTP/S protocols. It also provides an easy file search capability.

<img width="974" alt="Screenshot 2020-11-06 at 16 20 16" src="https://user-images.githubusercontent.com/51226604/98389452-fdf10800-204b-11eb-983c-5d71a41b2330.png"> 

# Prerequisites

* Before installing the MFT plug-in, make sure that Agent version 9.0.20.080 is installed.
* Verify that all jobs running on the Agent have ended.

# Workflow layout:

1. The workflow starts with a normal OS job ( **zzz-begin-flow**) to begin the workflow. This job will be waiting for confirmation.

This is to ensure that your are ready when you need to start demonstrating.

<img width="511" alt="Screenshot 2020-11-06 at 16 05 54" src="https://user-images.githubusercontent.com/51226604/98388011-106a4200-204a-11eb-8dcf-18a88cca121a.png"> 

2. The first transfer in the workflow will be from a single connection profile to profiles part of a group.

Template: zzz-mft-local-group

<img width="249" alt="Screenshot 2020-11-06 at 16 27 49" src="https://user-images.githubusercontent.com/51226604/98390287-0eee4900-204d-11eb-9fdc-5e834aedf1c7.png">
   
This job will use the Multi-Cast feature to transfer a file from one source to two other endpoints  but also to different locations on each of the        destinations.

<img width="1116" alt="Screenshot 2020-11-06 at 16 23 40" src="https://user-images.githubusercontent.com/51226604/98390018-c20a7280-204c-11eb-9f84-81f92d11cdb6.png">
   
   <img width="484" alt="Screenshot 2020-11-06 at 16 13 53" src="https://user-images.githubusercontent.com/51226604/98388800-1d3b6580-204b-11eb-947d-44db6145fdd8.png"> 


4. **Template: zzz-mft-transfer-small ; zzz-mft-transfer-medium ; zzz-mft-transfer-big

The next three jobs will each be responsible for transferring different size files to populate the Managed File Transfer Search dashboard with different size files for analysis. 

These jobs are making use of normal FTP connection profiles to an S3 bucket capabale for handling the file sizes

<img width="597" alt="Screenshot 2020-11-09 at 18 23 37" src="https://user-images.githubusercontent.com/51226604/98580970-b622e880-22b8-11eb-897d-8ba44ddd581c.png">

These jobs can be manipulated to fail if needed to show the different statusses in the dashboard and to navigate on the righthand pane for analysis into the problem transfers.
Change the file being transferred to something irrelevant and rerun the job from the Monitoring domain to deliberatly fail the job so that you are able to view the flow within the Managed File Transfer domain on the Control-M Web.

<img width="1677" alt="Screenshot 2020-11-09 at 18 28 53" src="https://user-images.githubusercontent.com/51226604/98581582-9f30c600-22b9-11eb-86ac-c7001783f7ee.png">

Also, now you will be able to interact with the failure in respect of showing the Summary, Job Output and navigating to the Transfer Workflow from here to show the functionality

5. Template: zzz-middle-flow --> zzz-mft-local-local ; zzz-mft-local-s3 ; zzz-mft-s3-s3

The next few jobs will start with a checkpoint job again (zzz-middle-flow) to give you some time to navigate between the domains. The time can be changed depending on what is required and your talk track. It is currently set at 10 seconds.

<img width="608" alt="Screenshot 2020-11-09 at 18 42 32" src="https://user-images.githubusercontent.com/51226604/98582801-5aa62a00-22bb-11eb-92b1-c1b72df8be00.png">

Once the time has elapsed, the next three jobs will run simutaneously responsible for connection profiles:

a) Local to Local transfer - Making use of a normal File System connection profile to and from a local host

<img width="508" alt="Screenshot 2020-11-09 at 18 39 32" src="https://user-images.githubusercontent.com/51226604/98582474-ed929480-22ba-11eb-92cc-6c142e801d0f.png">

b) Local to S3 bucket - Making use of a transfer from a File System local host to an AWS S3 bucket in the Cloud

<img width="507" alt="Screenshot 2020-11-09 at 18 40 26" src="https://user-images.githubusercontent.com/51226604/98582576-0ef38080-22bb-11eb-8ce0-ec71e0ec27ff.png">

c) S3 bucket - S3 bucket - Making use of S3 connection profile for transfer beteen two different buckets on AWS Cloud

<img width="507" alt="Screenshot 2020-11-09 at 18 41 18" src="https://user-images.githubusercontent.com/51226604/98582675-31859980-22bb-11eb-8f60-e40ee6ef90bb.png">

6. Template: zzz-mft-file-watcher

The next job will then be a file watcher responsible for monitoring a file arrival in a specific folder. Once the file arrives, it will trigger a job to run to show the continuing of a workflow acting on a trigger.
These jobs are not dependant on the Transfer Flow but rather show the basic File Watcher triggering.

This job can be modified to trigger a specific event depending on the requirement with the existing Tranfer template flow or depending what needs to be showed to a specific customer. 

<img width="190" alt="Screenshot 2020-11-09 at 19 20 16" src="https://user-images.githubusercontent.com/51226604/98586464-a0b1bc80-22c0-11eb-9cdf-a560754639be.png">

7. Template: zzz-mft-sla

The last job within the flow will be a normal SLA Management job template to act as a service monitoring job for the transfer flow. it is connected to 10/11 jobs so that the flow can also be manipulated with regards the critical path

<img width="193" alt="Screenshot 2020-11-09 at 19 26 29" src="https://user-images.githubusercontent.com/51226604/98587024-7e6c6e80-22c1-11eb-8f6b-699e584865d1.png">

And also having conversations arounf the critical path of the workflow:

<img width="516" alt="Screenshot 2020-11-09 at 19 40 05" src="https://user-images.githubusercontent.com/51226604/98588368-7f9e9b00-22c3-11eb-94d4-7c465767a5ad.png">

The service zzz-mft-service-monitor can be changed according to what needs to be shown to a customer

<img width="504" alt="Screenshot 2020-11-09 at 19 27 27" src="https://user-images.githubusercontent.com/51226604/98587891-b88a4000-22c2-11eb-83b6-63e8d32490c1.png">

This all for a view within the service monitor to run through an explanation depending on the requirement

<img width="1675" alt="Screenshot 2020-11-09 at 19 29 42" src="https://user-images.githubusercontent.com/51226604/98588036-f12a1980-22c2-11eb-9b23-392a1044bad4.png">
