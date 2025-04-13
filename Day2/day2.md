# Create EC2 Instance on AWS & Connect via PuTTY
This guide walks you through setting up an EC2 instance on AWS and connecting to it from a Windows machine using PuTTY.

# Prerequisites
An AWS account
Installed:
PuTTY
PuTTYgen
Step 1: Launching an EC2 Instance
Go to the AWS Console
Navigate to EC2 > Instances
Click Launch Instance
Configure:
Name: MyInstance
AMI: Choose Amazon Linux 2 AMI or Ubuntu
Instance Type: t2.micro (Free tier eligible)
Key Pair:
Click “Create new key pair”
Name: my-key
Type: RSA, Format: .pem
Click “Create Key Pair” (save .pem file safely!)
Network Settings:
Allow SSH (port 22)
Click Launch Instance
Step 2: Convert .pem to .ppk using PuTTYgen
PuTTY does not support .pem, so we need to convert it to .ppk.

Open PuTTYgen
Click Load
Change file type to All Files (*.*)
Select your .pem file (e.g., my-key.pem)
Click Open, then click Save private key
Save it as my-key.ppk (you can skip the passphrase)
# Step 3: Connect via PuTTY
Open PuTTY
In Host Name, type:
Replace <Public IPv4 DNS> with your instance's public DNS or IP (found in AWS EC2 dashboard)
In the left menu:
Go to Connection > SSH > Auth
Click Browse, and select your my-key.ppk file
(Optional) Go to Session → Save your session with a name for future use
Click Open
If prompted with a security alert, click Yes
You’re now connected to your EC2 instance via PuTTY! 🎉
