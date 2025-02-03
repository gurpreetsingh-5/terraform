provider "aws" {
    access_key = "********************"
    secret_key = "*****************"
    region = "us-east-1" 
}
# resource "aws_instance" "gur_test" {
#     ami = "ami-04b4f1a9cf54c11d0"
#     instance_type = "t2.micro"
#     key_name = "nv_key"
#     security_groups = ["all-traffic"]
#     tags = {
#       "Name" = "demoterraform"
#     }
  
# }
resource "aws_key_pair" "mykey" {
  key_name   = "mykey"  # public_key = "ssh-rsa ***************************"
  public_key = file("/home/gur/.ssh/id_rsa.pub")
# OR
  # public_key = "ssh-rsa ************************************************"
}

resource "aws_instance" "gur_test" {
    ami = "ami-04b4f1a9cf54c11d0"
    instance_type = "t2.micro"
    key_name = aws_key_pair.mykey.key_name
    security_groups = ["all-traffic"]
    tags = {
      "Name" = "demoterraform"
    }
  
}
