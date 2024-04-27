# Creating-and-launching-an-Amazon-EC2-Elastic-Compute-Cloud and also Connecting to an Amazon EC2 instance
Creating and launching an Amazon EC2 (Elastic Compute Cloud) and how to connect to amazon EC2 instance
### Step 1: Sign in to the AWS Management Console 
Go to the AWS Management Console at [https://console.aws.amazon.com/](https://console.aws.amazon.com/).
Sign in using your AWS account credentials.
### Step 2: Navigate to EC2
 Once signed in, navigate to the EC2 dashboard. You can find EC2 under the "Compute" section or by searching for "EC2" in the AWS services search bar.
### Step 3: Launch Instance
 On the EC2 dashboard, click on the "Launch Instance" button.
### Step 4: Choose an Amazon Machine Image (AMI)
 Select an AMI that suits your requirements. AMIs are templates that contain the software configuration (such as operating system, application server, and applications) required to launch your instance.
### Step 5: Choose an Instance Type
 Select the instance type that meets your needs in terms of CPU, memory, storage, and networking capacity. You can choose from various instance types depending on your workload.
### Step 6: Configure Instance Details
 Configure additional settings such as the number of instances, network settings, IAM role, monitoring, etc. Adjust these settings based on your requirements.
### Step 7: Add Storage
 Specify the size and type of the root volume (boot volume) for your instance. You can also add additional volumes if needed.
### Step 8: Add Tags (Optional)
 You can add tags to your instance to help you identify it easily. Tags are key-value pairs that you can assign to your resources.
### Step 9: Configure Security Group
 Configure security groups to control the traffic to your instance. You can create a new security group or select an existing one. Make sure to allow access only to the necessary ports and protocols.
### Step 10: Review and Launch
 Review all the configurations you have made for your instance. Once you are satisfied, click on the "Launch" button.
### Step 11: Create a Key Pair
 If you don't have an existing key pair, you will be prompted to create a new one. This key pair will be used to securely connect to your instance using SSH.
### Step 12: Launch Instances
 After creating the key pair, click on the "Launch Instances" button. AWS will now provision your EC2 instances based on the configurations you provided.
### Step 13: Access Your Instance
 Once the instance is launched, you can access it using SSH for Linux instances or Remote Desktop Protocol (RDP) for Windows instances. Use the key pair you created to authenticate.
### Step 14: Terminate Instances (When Finished)
 Remember to terminate your instances when you're finished using them to avoid unnecessary charges. You can do this from the EC2 dashboard by selecting the instance and clicking on the "Actions" dropdown menu, then choosing "Instance State" > "Terminate".
That's it! You've successfully created and launched an Amazon EC2 instance. You can now start using your instance for your computing needs.


# Connecting to an Amazon EC2 instance
Connecting to an Amazon EC2 instance typically involves using SSH (Secure Shell) for Linux instances or RDP (Remote Desktop Protocol) for Windows instances. Here's a step-by-step guide on how to connect to an EC2 instance:

## For Linux Instances (Using SSH):
### Step 1: Retrieve Public DNS/IP and Key Pair
Log in to the AWS Management Console.
Navigate to the EC2 dashboard.
Locate the instance you want to connect to and note down its Public DNS (IPv4) or Public IP address.
Ensure you have the key pair (.pem file) that was used when launching the instance.

### Step 2: Set Permissions for Key Pair
 Ensure that the permissions on your key pair file are restricted. Run the following command in your terminal:
  ```
  chmod 400 /path/to/your-key-pair.pem
  ```
### Step 3: Connect Using SSH
Open your terminal or SSH client.
Use the following command to connect to your instance:
  ```
  ssh -i /path/to/your-key-pair.pem ec2-user@public-dns-or-ip
  ```
Replace `/path/to/your-key-pair.pem` with the path to your key pair file and `public-dns-or-ip` with the Public DNS or Public IP address of your instance.
If prompted, type 'yes' to confirm the connection.
You should now be logged in to your EC2 instance via SSH.
 
## For Windows Instances (Using RDP):
### Step 1: Retrieve Public DNS/IP and Administrator Password
Log in to the AWS Management Console.
Navigate to the EC2 dashboard.
Locate the Windows instance you want to connect to and note down its Public DNS (IPv4) or Public IP address.
Retrieve the administrator password by right-clicking on the instance, selecting "Get Windows Password," and following the prompts.

### Step 2: Connect Using Remote Desktop
Open the Remote Desktop Client on your local machine (Windows Remote Desktop Connection or equivalent).
Enter the Public DNS or Public IP address of your instance in the "Computer" field.
Click on "Connect."
Enter the administrator username (default is "Administrator") and paste the password you retrieved in Step 1.
Click "OK" or "Connect" to establish the connection.
You should now be logged in to your Windows EC2 instance via RDP.
 
### Note:
Ensure that your security groups allow SSH (port 22) for Linux instances or RDP (port 3389) for Windows instances from your IP address.
Always keep your key pairs and passwords secure.
Terminate your EC2 instances when you're done to avoid unnecessary charges.
Now we are connected to Amazon EC2 instance and can start working on it as needed.

### THANK YOU
