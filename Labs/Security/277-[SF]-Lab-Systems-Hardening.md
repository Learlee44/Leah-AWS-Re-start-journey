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
![ALT TEXT](relative/path/to/Screenshot 2025-12-11 151558.png) 
