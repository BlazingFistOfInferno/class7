
Create an EC2 Tab Section

From your AWS Console, perform a search for EC2. Clicking on the link will bring you to this service dashboard.

Close all open drop down menu selections on the left side of the screen. We simply want to select them as needed.

From the drop down in Network & Security, select Security Group.

Create a security group
Provide a name example: sshandhomeoage
Copy and paste the name in the description field
We do nothing with the VPC as there should be one present.

Create an inbound rule
First select HTTP from the drop down. Port and protocol will be greyed out.
Then select Anyipv4

Your first invound rule is created.

Select SSH from the drop down. Port and protocol will be greyed out.
Then select Anyipv4
There will be a dropdown ip path of 0.0.0.0 
Use this value for both http and ssh.

Now we have created our invound rules, one for normal IPv4 web traffic and SSH for secure connection to our instance.

At this point it must be soecified that we completely disregard Outbound Rule. We do not touch it. 

Move your cursor to the far right of the browser window as we move the mouse completely around Outbound Rule section

Once completed, click on the orange button Create Security group.

This security group will be used when we continue on to create our Launch Template.

Create a Launch Template
First create a launch instance

Give it a name
Use select a security group
Choose the group name we just made up
Ex. lizzo-free-zone
Copy the name and paste it into the description field.

Advanced section
Run to github and from the listed repository, open up the file named EC2 script. Use the double rectangle to copy the text in its entirety.
Paste it in the box at the bottom of the advanced section. Do not click on the box that says use base16. Ignore it.
Once the script is in place, move your cursor to the Orange Button named Create Launch Template and select it.

If you have properly created it, the resulting box will show a blue bar as it creates, turning to a green success indicator showing you that the Launch Template was created.

Starting a Launch Template
Once we have the Launch Instance created, click on the link to go to the launch instance page.
Click on the box next to the launch instance you just created. There are two different ways to launch an instance, either click on the Connect button above your selection criteria, or go to the Actions drop down and the first menu item says Launch Instance from a Template.
Select that option

Then after a few seconds to roughly 10 seconds, move your mouse to the right to click on the orange button labeled Launch Instance.

Pay attention to the unique i-xxxxxxx value specified as the instance because you will want to verify that your script properly ran creating your EC2.

Once it starts running, the instance will say initializing while starting up. This changes to running once all conditions for booting have been met. click on instances from the tab or using the link select instance. Click on the double rectangle on public DNS to copy the public  link to your EC2 Instance.
Open a new tab and type “http://” and then paste in the name of the EC2. Hit enter.
There should be a simple website on view with an image stating w3 schools.

The purpose of using an EC2 startup script is to automate the creation of instances with an Instance Template

Once we have created the instance, we can modify it to quickly spin up new instances branching off from our original template in the same or different regions.

The last task to perform once you have completed creating your instance will be to tear it down.
Select the instance and from the actions button click on terminate instance.
Once the instance is terminated, billing will halt.


Additional information to be conscious of 

A budget will need to be created just so that one does not get billed unnecessarily due to the fact it could become quite expensive. Create one after the instance party has been completed. It is suggested that you set a $20 limit.
