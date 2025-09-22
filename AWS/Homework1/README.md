
Create an EC2 Tab Section

From your AWS Zconsole, perform a search for EC2. This will bring you to this service.

Close all open selections on the left side of the screen. We simply want to select them as needed.

From the drop down text Select Security Group.

Create a security group
Provide a name example: sshandhomeoage
Copy and paste the name in the description field
We do nothing with the VPC as there should be one present.

(I discovered that for whatever reason, when I created my Launch Instance, several fields were blank and caused an error. In that situation hit refresh on those fields, they will fill in and you will be able to continue your Launch I stance creation. Side note no. 2, my PC is old and underpowered and my tablet was able to create a Launch Instance the way it should be done.)

Create an inbound rule
Use http
Any ipv4

Ssh
Anyipv4

We use nothing else. Then 
we move the mouse completely around Outbound Rule section

After that click on Orange Button Create security group

This security group will be used when we move on to our Launch Instance

Create a Launch Instance
First create a launch instance

Give it a name
Use select a security group
Choose the group name we just made up
Ex. sshandhomeoage
Paste a description or provide a custom one describing what the template is for.


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

When it starts running, the instance will say initializing and running once it is runningclick on instances from the tab or using the link select instance. Hit the double rectangle on public DNS to grab the link to the site.
Open a new tab and type “http://” and then paste in the name of the EC2. Hit enter.
There should be a simple website on view with an image stating w3 schools.

The purpose of using an EC2 startup script is to Automate the creation of instances with an Instance Template

Once we have created the instance, we can modify it to quickly spin up new instances branching off from our original template in the same or different regions.

The last task to perform once you have completed creating your instance will be to test it down.
Select the instance and in the actions button click on terminate instance.
Once the instance is terminated, billing will halt.
