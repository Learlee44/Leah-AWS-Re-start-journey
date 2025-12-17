# Introduction to Amazon EC2

## Overview

This lab provides you with a basic overview of launching, resizing, managing, and monitoring an Amazon EC2 instance.
---
# Objectives
By the end of this lab, you will be able to:
-Launch a web server with termination protection enabled
-Monitor Your EC2 instance
-Modify the security group that your web server is using to allow HTTP access
-Resize your Amazon EC2 instance to scale
-Test termination protection
-Terminate your EC2 instance
---

## Task 1: Launching your EC2 instance

1. In the AWS Management Console on the Services menu, choose EC2.

2. In the left navigation pane, choose EC2 Dashboard to ensure that you are on the dashboard page.

### Steps taken

1. Choose Launch instance, and then select Launch instance.
  - Name your instance
  - choose an Amazon Machine Image 
  - choose an instance type
  - configure a key pair 
  - configure the network settings
  - add storage 
  - Launch an EC2 instance
2. Steps 1 - 2
![image](<Naming EC2 instance.png>)
3. Steps 3 - 4
![image](<Choosing an instance type.png>)
4. Steps 5 - 7
![image](<Adding security group.png>)
5. Step 8
![image](<Launching instance.png>)
![image](<Instance successfully launched.png>)

## Task 2: Monitor your Instance.

1. Navigate to your instances.

2. Select the instance by checking the box next to the instance and navigate to the bottom of the screen to the Status checks tab.

3. Select the Monitoring tab.

4. In the [ACTIONS] menu, select Monitor and troubleshoot, then select Get instance screenshot.

![image](<Monitor instance.png>)
![image](<Monitor instance 2.png>)

Instance screenshot
![image](<Instance screenshot.png>)

5. Select [Cancel] located at the bottom of the instance screenshot.


## Task 3:  Update Your Security Group and Access the Web Server

1. Select the instance by checking the box and select the [Details] tab.

2. Copy the Public IPv4 address of your instance to your clipboard.

![image](<Update security group.png>)

3. Open a new tab in your web browser, paste the IP address you just copied, then press Enter.

![image](<Web browser not working.png>)

4. Keep the browser tab open, but return to the EC2 Management Console tab.

5. In the left navigation pane, select Security Groups located under Network & Security.

6. Select Web Server security group.

![image](<Edit security group.png>)

7. Select the Inbound rules tab.
(The security group currently has no rules.)

8. Select Edit inbound rules then select Add rule and configure the rule with the following settings:
 Type: `HTTP`
 Source: `Anywhere-IPv4`
 Select Save rules.

![image](<Edit inbound rules.png>)
![image](<Successfully added inbound rule.png>)

9. Return to the web server tab that you previously opened and refresh the page.
(You should see the message `Hello From Your Web Server!`)

![image](<Web browser working.png>)
---

## Task 4: Resize Your Instance: Instance Type and EBS Volume

1. Before resizing an instance, you must [Stop] it.

### Steps taken:

1. On the EC2 Management Console, in the left navigation pane, select [Instances].
- Web Server should already be selected.

2. Select Instance state > Stop instance.
![image](<Stop instance.png>)

3. Select [Stop].

4. Wait for the Instance State to display: [stopped]. 
![image](<Stop instance 2.png>)
![image](<Stopping instance.png>)
![image](<Instance successfully stopped.png>)
---

### Change the Instance Type

1. In the [Actions] menu, select Instance Settings, then Change Instance Type, then configure:
 - Instance Type: `t3.small`
 - Choose: Change instance type

 ![image](<Instance settings.png>)

 ### Resize the EBS Volume

 1. In the left navigation menu, select Volumes located under Elastic Block Store.

 2. Select the volume by checking the box, and navigate to the [Actions]  menu, select Modify Volume.
 (The disk volume currently has a size of 8 GiB. You will now increase the size of this disk.)

3.  Change the size to: `10`

4. Select: [Modify]

5. Select [Modify] to confirm and increase the size of the volume.

![image](<Modify volume.png>)
![image](<Resize the EBS volume.png>)
![image](<Modifying volume.png>)

### Start the Resized Instance

1. In left navigation pane, select [Instances].

2. Select the Web Server instance by checking the box, then navigate to Instance state > Start instance.


## Task 5: Test Termination Protection
(In this task, you will learn how to use termination protection.)

1. Select the Web Server instance by checking the box and navigate to the top and select Instance state  menu, select  Terminate (delete) instance.

### Note

 There is a message that says: On an EBS-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated. Storage on any local drives will be lost. It will ask if you are sure that you want to terminate the instance. You will be able to select the [Terminate] button.

 You will notice that the instance did not terminate and a red error message pops up at the top that says: Failed to terminate an instance: The instance may not be terminated. This is because it has termination protection enabled.

2.  In the [Actions]  menu, select Instance settings,then select Change termination protection.

3. Uncheck Enable box then Save the changes.
(You can now terminate the instance.)

4. In the [Actions]  menu, select Instance State, then select  Terminate instance.

5. Select [Terminate].

![image](<Terminating instance.png>)
![image](<Instance successfully terminated.png>)
---

# Lab Complete.