Building out a customized EC2 Startup script for an EC2 Instance

Start by logging into your AWS account. It is preferable to use an IAM user instead of the Root User. Make sure that your IAM user has administrative console permissions.

 Once logged in, go to the search bar and search for EC2

Click on EC2 and it will take you to the Dashboard. Once at the dashboard, collapse every menu except EC2. We will start with creating a Security Group. Open up the Network & Security menu. Click on Security Groups. Move the mouse to the orange button that says Create Security Group and click it.
Move to the section that says Basic Details and in this example, use lizzo-free-zone as your group name. Then copy it into the description field.

The VPC will automatically populate so we can move past that to the Inbound Rules section.
Click on Add Rule, and for Type select HTTP from the dropdown. Protocol and Port range will be greyed out. For the Source dropdown, select AnyIPv4.
With this we have created our first Inbound Rule.
Press Add Rule again, because we need to add some security to our Security Group.

Select SSH from the dropdown. THe Protocol and Port Range are greyed out again. FOr HTTP, the port is 80 and for SSH the port is 22.

Repeat the above actions for Source by selecting IPv4 again.

In the greyed out section next to Source, both dropdowns should have 0.0.0.0 chosen from the dropbox. One might lready be present, but SSH needs its own entry as well.

The next step is very VERY important. DO NOT TOUCH OUTBOUND RULE!!!

Move the cursor to the farthest right you can go in the window and move around the Outbound Rule section. 

At the bottom right of the screen, locate the orange button that says Create Security Group and click it.

If you are successful a green box will appear on the next screen with the name of your security group along with a link to it.
You can check the box that will show details about yur newly created Security group, incloudig the name the system assigned it as well as the your name you assigned it. 

Most of the details can be covered later, but there are a few important things to note.
Security Group name, we will be using this next. It will have our lizzo-free-zone.
Owner will be the account number of your AWS account.
3. In the section below owner, you will see that your security group has 2 inbound rules and they are listed as the SSH and HTTP rules we specified.

Collapse Network & Security and Open up Instances

Click on Launch Template
We will need to create a Launch Template so we can create an Instance of our EC2, meaning we will create a website that is capable of accepting an inbound connection through HTTP or securely connecting through SSH.

Once again, move to the far right to click on the orange button Create Launch Template.
Use the name we created for our security group for the template name and description.
 select a free tier eligible option, for me it was t3.micro

In the INstance Type Section, for Instance Type

Create a key pair
Give it a unique name
Leave RSA selected
The private key format is .pem
Move to the orange button to Create Key Pair.

Move down to Network Settings
For availability zone select a server in the region you are in. For example, for N. Virginia, it is us-east-1. I will select an availability zone of us-east-1a to be within my region.
Use an existing security group, select the group we just created, lizzo-free-zone from te dropdown.

Move to Advanced Details
Open it up and move to the bottom of the page.

There is a text box titled user data -optional.
We will grab a provided ec2script from a repository.
We will use my repository for an example

https://github.com/BlazingFistOfInferno/class7/blob/main/AWS/Homework1/EC2StartupScript
Click on the double rectangles to copy the script in its entirety.
Paste it into the user data box.vThen move your mouse out of the user data box towards the far right to click on the orange button and Create Launch Template.


You have created the launch template. Click on the instance in the green linked box.

Click Actions -> Launch Instance from Template
Then select the orange button
Launch Instance
Choose a launch template
The first instance will take time but it will auto populate as it is the default.

Then under Application and OS IMages select Amazon Linux AWS

Orange button click Launch Instance

If the successfully completes, there will be a green box, click on the instance i-xxxx value.
Look for instance state, once it is running you can then click on the double rectangle for Public DNS Server.

Open up a new browser tab and type http://, then paste the link you copied behind it. Hit return and you should have a template named Samurai Katana with a w3 schools image.

If you see it, then your instance has successfully launched.

Once that has happened, you will need to shut down the instance to stop the charging that is taking place.

Go to instances. Click on the Actions button and  after selecting the instance that was running, click on terminate instance. This will shutdown the instance.

Once this process has completed, you can state that you have successfully created an EC2 Instance and then torn it down.


Additional information to be conscious of 

A budget will need to be created just so that one does not get billed unnecessarily due to the fact it could become quite expensive. Create one after the instance party has been completed. It is suggested that you set a $20 limit.

