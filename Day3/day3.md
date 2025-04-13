# Terraform

![428281089-64c93d88-8a0a-49ad-8590-e9d0689e0428](https://github.com/user-attachments/assets/2711376a-3f7f-4d73-99cf-2cd08d057c7b)

tereform script --> to avoid doing the same job again and again whenever we want to create cloud resources like EC2, subnet, internet gateway,loadbalancer, database servers, or any resources u want to create by using automation or script, we use teraform teraform --> widely used in companies

- Step 1: -install teraform on ur windows machine
- Step 2:
* set terraform path on Windows machine
  
  ![428281081-c09d2a33-0893-4bf7-9018-239da2b23085](https://github.com/user-attachments/assets/3ae333b4-4b38-46d3-ba69-1a3035ebd8f6)

* install terraform from https://developer.hashicorp.com/terraform/install

* Create a terraform folder in program files in c drive

* extract the zip file downloaded(teraform) ---> browse it to the new folder created(terraform)

* add path to environmental variable
- Step 3:
* Configure AWS credentials from CLI (command line interface)
* install AWS CLI
* https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
  ![428282081-e260f4ab-7091-49b1-97e7-50005cc3bdf6](https://github.com/user-attachments/assets/247574ef-7f99-4063-9b95-ed07438aeac1)
  
![428282321-5ab5dcd7-560d-423a-aa02-bd7e7fa5adee](https://github.com/user-attachments/assets/8048ecf0-9086-4519-a117-f9aa390d3031)

in AWS,

![428283223-6fad3de2-9bd9-4ce8-af4c-bae2a9df0237](https://github.com/user-attachments/assets/c4552c4b-4d01-4568-856d-0e791f7f6cb2)

When ur writing terraform files, we need to write blocks

mention provider - provider blocks defines in which we are doing automatio(aws)
resource block - what kind of resource that u want to create on the cloud (vpc,loadbalancers, subnets)
define variable blocks - u want to pass any parameter as variables
output files - if u want to print output in console like public/private ip address,vpc id
When u create an instance using terraform scripts, make sure to pass these 5 parameters

amazon id
instance type
key-pair name
storage
instance name
https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance
# commands:
* terraform init --> will initialize terraform backend configuration with the 
  cloud api. It is going to generate a license key to authenticate cloud provider 
  API as well as it is going to create. terraform folder, which contains -> 
  license and neccesary files
* terraform validate
* terraform plan -tells what u plan to do in the cloud
* terraform apply Now ur server is ready!!!!
* terraform destroy - will automatically delete all the resources When u execute the command terraform plan --> it will automatically create terraform .tf state file, which contains the current state of the infrastructure
whenever u create vpc - vpc should contain name and ip address range & tennancy -
