provide "aws"{
  region = "ap-south-1"
}
module "prod_vpc"{
  source = "../modules/vpc"
  vpc_cidr = "198.162.0.0/16"
  tenancy = "default"
  vpc_id = "${module.prod_vpc.vpc_id}"
  subnet_cidr = "198.162.1.0/16"
}

module "prod_ec2_instance"{
  source = "../modules/ec2"
  ec2_count = 1
  ami_id = "ami-0ad42f4f66f6c1cc9"
  instance_type = "t2.micro"
  subnet_id = "${module.prod_vpc.subnet_id}"
}
