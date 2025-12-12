# Systems Hardening with Patch Manager via AWS Systems Manager

In this lab:
1. I used Patch Manager, a capability of AWS Systems Manager, to create a patch baseline.
2. Used the patch baseline that i created to scan the Amazon Elastic Compute Cloud (Amazon EC2) instances for Windows that were pre-created for this lab. 
3. Used default patch baseline to patch EC2 Linux instances.
---
 
 ## Steps taken in Task 1: Patch Linux EC2 instances using default baselines
 1. Open the AWS Management Console, search Systems Manager and select it.
 2. In the left navigation pane, under Node tools, choose Fleet Manager.
 3. Select the check box next to Linux-1. Then choose the Node actions      dropdown list, and choose View details to view details about the specific instance.
 4. Go back to Systems Manager homepage.
 5. In the left navigation pane, under Node Management, choose Patch Manager.
 6. Choose Patch now to patch the Linux instances with AWS-AmazonLinux2DefaultPatchBaseline.
 7. Configure as follows:
 -Patching operation:  Scan and install

-Reboot option: Reboot if needed

-Instances to patch: Patch only the target instances I specify

-Target selection: Specify instance tags

-Tag key:  Patch Group

-Tag value: LinuxProd

-Choose Add

8. Choose Patch now.
9. Observe the status of the patching.
![alt text](<Screenshot 2025-12-11 151558.png>)
![alt text](<Screenshot 2025-12-11 145822.png>)
---

## Task 2: Create a custom patch baseline for Windows instances
1. Return to Systems Manager,In the left navigation pane, under Node Management, choose Patch Manager.
2. Choose the Patch baselines tab.
3. Choose the Create patch baseline button.
4. Configure as follows:
 -For Name, enter WindowsServerSecurityUpdates.

-For Description - optional, enter Windows security baseline patch.

-For Operating system, choose Windows.

-Leave the check box for Default patch baseline unselected.

5. Add rule and create patch baseline
![alt text](<Screenshot 2025-12-11 151053.png>)
---

## Task 3: Patching the Windows instances
1. After configuration tag Windows instances
 -In the AWS Management Console, in the search  bar, enter EC2 and select it.
 -Choose Instances, select the check box next to the Windows-1 instance, and then choose the Tags tab.
 -Choose the Manage tags button, choose Add new tag, and configure the following options:

  -Key: Enter Patch Group.

  -Value: Enter WindowsProd.
2. Choose save.
![alt text](<Screenshot 2025-12-11 152233.png>)

3. Return to the Systems Manager console. In the search bar at the top, enter Systems Manager and then select it.
4. Patching the Windows instances:
  -Choose Patch Manager. 

  -Choose Start with an overview (Proceed to next step if this option does not appear).

  -Choose Patch now.

  -Patching operation:  Scan and install

  -Reboot option: Reboot if needed

  -Instances to patch: Patch only the target instances I specify

  -Target selection: Specify instance tags

   -Tag key:  Patch Group

   -Tag value: WindowsProd

  -Choose Add

  -Choose Patch now.

  A new page displays. When it becomes available, choose the link to the Execution ID.-A page in the State Manager part of Systems Manager opens.-Choose the Output link for one of the managed instances that shows a status of InProgress.-A page in the Run Command part of Systems Manager opens.-Expand the Output panel to observe the details.

  ![alt text](<Screenshot 2025-12-11 150258.png>)
  ---


  ## Task 4: Verifying compliance
1. In the left navigation pane, under Node Management, choose Patch Manager.
2. Choose the Dashboard tab. Under Compliance summary, you should now see Compliant: 6, which verifies that all Windows and Linux instances are compliant.
3. Choose the Compliance reporting tab. 
4. Choose the Node ID for one of the Windows nodes.
  -In the Node ID page that opens, choose the Patch tab.
  -Scroll down and observe what patches were applied to this instance, as well as the Installed Time.
![alt text](<Screenshot 2025-12-11 152127.png>)
