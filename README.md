Creating AWS CI/CD Pipeline for NodeJs Project by using AWS Codecommit,CodeDeploy,CodePipeline

Create Custom VPC

Go to AWS console --> Go to VPC service --> Create VPC --> IPv4 CIDR block 10.0.0.0/24 --> Create

Create Public Subnet

Select Availability zone 
CIDR block 10.0.0.0/26

Create Private Subnet
CIDR block 10.0.0.64/26

Build CI/CD Pipeline:

Pre-requisites:

1) Download and install git on your linux or windows workstation
2) Configure Git on local workstation (Shell or windows cmd)
	a. git config --global user.email <your email id>
	b. git config --global user.name <your name>
3) Create new AWS IAM User
	a. Attach IAM Policy "AWSCodeCommitFullAccess"
	b. Attach IAM Policy "AWSCodePipelineFullAccess"
4) Create Service Role for CodeDeploy
	a. Create IAM Role for CodeDeploy Service
	b. Attach existing IAM policy "AWSCodeDeployRole"
CodeCommit:
 1. To set up the public and private keys for Git and CodeCommit
             Open Bash Emulator.
 		From the emulator, run the ssh-keygen command, and follow the directions to save the file to the .ssh directory for your profile.
This generates:
•	The id_rsa file, which is the private key file.
•	The id_rsa.pub file, which is the public key file.
	
2. Copy your public key to IAM user. 
•	Go to IAM Console , Select  IAM user Go to Security Credentials.

•	Go to Upload SSH Public key then upload your public key.
3. Go to CodeCommit Service ( Use any one region for all services here I take N.Virginia)
	a. Create New Code repository with name “nodejs-project”
	b. Copy the clone URL  Clone SSH
c. In the Bash emulator, run the git clone command with the SSH URL you copied to clone the repository. This command creates the local repo in a subdirectory of the directory where you run the command.
•	git clone ssh://git-codecommit.us-east-2.amazonaws.com/v1/repos/nodejs-project nodejs-project
d. Add your files to codecommit repository.
4. Browse the contents of your repository




