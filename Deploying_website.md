Start an EC2 Instance and install the 'nginx' Web Server (for more detailed steps, you can access EC2 instance and 'nginx' Steps). Recap of commands: (can find on previous document)


`cd .ssh`

`chmod 400 tech254.pem`

` ssh -i "tech254.pem" ubuntu@ec2-34-242-218-109.eu-west-1.compute.amazonaws.com`

`sudo apt update`

`sudo apt upgrade -y`

`sudo apt install nginx -y`

`sudo systemctl start nginx`

1) Download 'app' file and unzip file 

2)Upload the 'app' file to EC2 (Theres two ways this can be done)

1:) 