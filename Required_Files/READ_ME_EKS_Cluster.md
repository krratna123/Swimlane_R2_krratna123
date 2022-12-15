SETUP KUBERNETES CLUSTER - AWS EKS USING TERRAFORM


Prerequisites:
An AWS account, IAM USER, ACCESS_IP, ACCESS_KEY, SECRET_KEY
Terraform INSTALLED to RUN

Terraform Files:
> eks-
	- main.tf
	- outputs.tf
	- variables.tf
> networking-
	- main.tf
	- outputs.tf
	- variables.tf
> security-
	- main.tf
	- outputs.tf
	- variables.tf
> data.tf
> locals.tf
> main.tf
> outputs.tf
> providers.tf
> variables.tf


Command to run:
1. terraform init
2. terraform plan
	Provide values for ACCESS_IP, ACCESS_KEY, SECRET_KEY when prompting
3. terraform apply
	Provide values for ACCESS_IP, ACCESS_KEY, SECRET_KEY when prompting

To Destroy Created EKS CLUSTER
1. terraform destroy
	Provide values for ACCESS_IP, ACCESS_KEY, SECRET_KEY when prompting
