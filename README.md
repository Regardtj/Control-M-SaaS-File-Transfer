Control-M SaaS: Managed File Transfer job templates

Introduction:

The intention of this repository is to provide job templates relevant to the Control-M Managed File transfer solution specifically running on the Control-M SaaS platform.
By providing these templates, it will make it easier for the Solution Engineers to use these templates in building Solution Demo’s for their customers.

![Screenshot 2020-11-06 at 15 04 44](https://user-images.githubusercontent.com/51226604/98387167-fbd97a00-2048-11eb-8e26-ef7e877ac161.png)

Disclaimer
This application is not linked to or based on any particular business at all. The contents are all fictional and have been fabricated to be used for demonstration purposes only. 

Control-M Managed File Transfer:

Every modern business depends on the movement of files. Whether it be between internal applications, systems of record, mainframes, external business partners, or cloud platforms, this is a mission-critical requirement that practically every single business process depends on to succeed.  
Nonetheless, despite how important this is, many businesses still manage file transfers independently from their business workflows and depend on custom integrations, scripting and manual interventions to synchronise them. 
Control-M Managed File Transfer puts you in control of file transfers with an intuitive graphical user interface to guide you through job definitions and ensure transfers are associated with comprehensive automated workflows. 
You get instant visibility into the status of internal and external file transfers with a dashboard view, enhanced security with encryption options, and reduced risk of downtime with automated monitoring and recovery features. 

Environment:

For this environment the templates is intended to be run on the Control-M SaaS platform with an agent that needs to be created with a working Control-M Managed File Transfer CM installed and working connection profiles.
Control-M SaaS will be the is the key in orchestrating the File Transfer applications and providing business critical information around the transfer status and insight to business users on the overall file transfers

Requirements:

1. Access to Control-M SaaS platform
2. Access to an Control-M Agent on OS of choice
3. Control-M for Managed File Transfer CM installed on this agent
4. At least one working connection profile for the relevant template that will be used


Plugin for Managed File Transfer

Overview
Managed File Transfer (MFT) plugin is an FTP/SFTP client and server solution that enables you to watch files and transfer files in your organisation. It supports accessing a local file system, Amazon or compatible S3 and SFTP or FTP/S protocols. It also provides an easy file search capability.

Prerequisites
* Before installing the MFT plug-in, make sure that Agent version 9.0.20.080 is installed.
* Verify that all jobs running on the Agent have ended.
