# Terraform Docker Task 4

**Submitted by:** Arshad Khan

## Objective
Provision a local Docker container using Terraform.

## Tools Used
- Terraform
- Docker

## Steps Followed
1. Initialized Terraform with `terraform init`.
2. Planned infrastructure changes with `terraform plan`.
3. Applied changes to create the Nginx container with `terraform apply`.
4. Destroyed the infrastructure with `terraform destroy`.

## Execution Logs

### `terraform init`



### `terraform apply`
Initializing the backend...
Initializing provider plugins...

Reusing previous version of kreuzwerker/docker from the dependency lock file

Using previously-installed kreuzwerker/docker v3.0.2

Terraform has been successfully initialized!



### `terraform plan`
Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
following symbols:

create

Terraform will perform the following actions:

docker_container.nginx_container will be created

resource "docker_container" "nginx_container" {

attach = false

container_read_refresh_timeout_milliseconds = 15000

name = "terraform-nginx"

must_run = true

remove_volumes = true

restart = "no"

start = true

ports {

internal = 80

external = 8080

ip = "0.0.0.0"

protocol = "tcp"
}
}

docker_image.nginx_image will be created

resource "docker_image" "nginx_image" {

name = "nginx:latest"

keep_locally = false
}

Plan: 2 to add, 0 to change, 0 to destroy.


### `terraform apply`


Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the symbols:

create

Do you want to perform these actions? Enter a value: yes

docker_image.nginx_image: Creating...
docker_image.nginx_image: Creation complete after 6s
docker_container.nginx_container: Creating...
docker_container.nginx_container: Creation complete after 1s



### `terraform destroy`
docker_image.nginx_image: Refreshing state...
docker_container.nginx_container: Refreshing state...

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
following symbols:

destroy

Do you really want to destroy all resources? Enter a value: yes

docker_container.nginx_container: Destroying...
docker_container.nginx_container: Destruction complete
docker_image.nginx_image: Destroying...
docker_image.nginx_image: Destruction complete

Destroy complete! Resources: 2 destroyed.