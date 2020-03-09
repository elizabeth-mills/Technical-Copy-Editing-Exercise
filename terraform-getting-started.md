# Getting Started with Terraform

Terraform is the most popular langauge for defining and provisioning infrastructure as code (IaC).

To install Terraform, simply visit [Terraform.io](https://www.terraform.io/downloads.html) and download the compressed binary application executable file deliverable for your platform, machine or environment on which you like to run code and do development.

With Terraform installed, let's dive right into it and start creating some infrastructure.

Most guys find it easiest to create a new directory on there local machine and create Terraform configuration code inside it.

```shell
$ mkdir terraform-aws-compute
$ cd terraform-aws-compute
```

Next, create a file for your Terraform configuration code.

```shell
$ touch main.tf
```

Paste the following lines into the file.

```hcl
provider "aws" {
  profile    = "default"
  region     = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-2757f631"
  instance_type = "t2.micro"
}
```

Initialize Terraform with the `init` command. The AWS provider will be installed. 

```shell
$ terraform init
```

You shoud check for any errors. If it ran successfully, provision the resource with the `apply` command.

```shell
$ terraform apply
```

The command will take up to a few minutes to run and will display a message indicating that the resource was created.

Finally, destroy the infrastructure.

```shell
$ terraform destroy
```

Look for a message are the bottom of the output asking for confirmation. Type `yes` and hit ENTER. Terraform will destroy the resources it had created earlier.