## Attempting to create an AWS-EC2 Instance and install LAMP server on it
------------------

### Requirements
* A working laptop
* A good internet connection


### Signing up for EC2
**We will be using the free Tier Option**
  * This is a free Trial
  * AWS Free Tier includes 750 hours of Linux and Windows t2.micro instances each month for one year.
  * To stay within the Free Tier, use only EC2 Micro instances.

* Click on [Amazon-EC2](https://aws.amazon.com/ec2/) to go to the page.
* * Choose _Try Amazon EC2 for free_
* Create an account if you don't have one
* Click on [Launch a virtual machine](https://us-east-2.console.aws.amazon.com/ec2/v2/home?#LaunchInstanceWizard:)
* Click the _Free tier only_ to show only free tier offers
* Select the _Amazon Linux 2 AMI (HVM), SSD Volume Type..._
* Select General purpose, t2.micro type - see image
![Choose Instance Type](/img/instance-type.png)
* Click on **Next: Configure Instance Details**
* Leave **default settings** except you want to make changes
* Click on **Review and Launch**
* **Review Instance Launch** to make sure the settings are correct
* Click on **Launch**
* Create a private key for ssh purposes
* Click on Create a new key pair
* Choose a name for your key pair
* Click on **Download Key Pair**
  * Make sure you save the downloaded key pair in a folder on your laptop, you'll need it to log in later
* Click on **Launch Instance**

#### You've successfully created an Instance

* Click on **View Instance**
* Click on **launch-wizard-2** to change your Security Group settings
  * Click on **edit**
  * Add HTTP and HTTPS

### Configure ssh for ec2
* For complete instruction about installing an SSH client on Linux or macOS X, see [http://www.openssh.org.](https://www.openssh.com/)

* For information about installing an SSH client on Windows 10, see [OpenSSH in Windows](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_overview).

* For complete instruction on ec2 SSH and SCP file transfer, see [SSH and SCP on AWSEC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html#AccessingInstancesLinuxSCP) or follow the quick guide below
1. Open your command line shell and change the directory to the location of the private key file that you created when you launched the instance.
  * Use the chmod command to make sure your private key file isn't publicly viewable. For example, if the name of your private key file is my-key-pair.pem, use the following command:

  ```
  chmod 400 my-key-pair.pem
  ```

2. Use the following SSH command to connect to the instance:
```
ssh -i /path/my-key-pair.pem ec2-user@public_dns_name
```
**Note:** _For this quick start, you used the Amazon Linux AMI for your instance, so the user name is ec2-user._

### Prepare the LAMP Server

#### Prerequisites
* Already launched a new instance using the Amazon Linux AMI
* Public DNS name that is reachable from the internet
* You must also have configured your security group to allow SSH (port 22), HTTP (port 80), and HTTPS (port 443) connections

#### installation

* Follow the instruction on this Link to complete the installation [ec2-lamoServer](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html)
