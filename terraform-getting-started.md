# Getting Started with Terraform

Terraform is the most popular tool for defining and provisioning infrastructure as code (IaC).

To install Terraform, visit [Terraform.io](https://www.terraform.io/downloads.html) and download the appropriate package for your operating system and architecture.

With Terraform installed, let's dive in and start creating some infrastructure.

Most developers prefer to create a new directory on their local machine and create Terraform configuration code inside it.

```shell
$ mkdir terraform-aws-compute
$ cd terraform-aws-compute
```

Next, create a file for your Terraform configuration code.

```shell
$ touch main.tf
```

Paste the following lines into the file:

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

Initialize Terraform with the `init` command. Terraform will install the AWS provider.

```shell
$ terraform init
```

Check for any errors. If Terraform initialized successfully, provision the resource with the `apply` command.

```shell
$ terraform apply
```

The command will take up to a few minutes to run and then display a message indicating that the resource was created.

Finally, destroy the infrastructure.

```shell
$ terraform destroy
```

Look for a message at the bottom of the output asking for confirmation. Type `yes` and hit ENTER. Terraform will destroy the resources it created.
