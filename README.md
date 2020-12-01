# devopsassignment2020

# Steps for provisioning Infrastructure in AWS using terraform

  Install below binary and dependencies.
  
        - terraform
	      - aws cli
	  
  Provide required parameter in terraform.tfvars, like aws_access_key, aws_secret_key, billing_code_tag, ssh_remote_allow_list

  Run below commands to provision the resources in AWS.

      `terraform init`
      `terraform plan`
     `terraform apply`

  If you want to destroy all config just need to run below command.
     
      `terraform destroy`
	 
	 
# Question:


Q) How would you make this deployment fault tolerant and highly available?
A) We can provision same number of replicas in different availablity zone along with autoscaling group. We canc reate different subnet and autoscaling group in different availblity zone and provision application load balancer for acheiving high avalablity

Q) How would you make this deployment more secure?
A)We can make it more secure by restricting the inbound and outbound security rules , and making web tier and app tier sitting in private subnet and doesnt have internet gateway. Also, we can use encryption on application laod balacner or on the webserver level to do ssl encryption. VOlumes can be encrypted and we can provision WAF.

Q)How would you make this deployment cloud agnostic?
A)Terraform is a cloud agnostic tool, If you did need to do this you would need to build a bunch of modules on top of things that abstracts the cloud layer from the module users and just allow them to specify the cloud provider as a variable which can be controlled from outside script.
