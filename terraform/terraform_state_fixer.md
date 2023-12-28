Sometimes Terraform state files need to refactor due to various legact fubars. 
One example of this is adding a count conditional to existing modules or resources already provisioned. 
This is a general best practice with automation to follow. Someday..
* Download and replicate existing `terraform.tfstate` file from S3 backend.
* Make sure versioning is enabled on bucket.
* Add count changes to `main.tf` and add locals and variables also. Follow best practices seen in community modules.
* Do a terraform plan and now notice that the resource wants to be destroyed and added.
  * Save the tfplan to a file.
* Compare old vs new terraform files and replace new resource into old `terraform.tfstate` file.
* Upload `terraform.tfstate` to s3 using cli command
* Run a `terraform plan`, get the lock id and update in dynamo db table
* rerun `terraform plan` and it should show no changes.
