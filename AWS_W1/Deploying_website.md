Deploying Sparta Global's website


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

Option 2.1:) Using scp in your local terminal:

scp -i "<filepath to .pem file>" -r app Ubuntu@<public IP>


scp -i "C:/Users/Nadia/.ssh/tech254.pem" -r app ubuntu@ec2-3-249-92-82.eu-west-1.compute.amazonaws.com:~

Option 2.2:  On the EC2 Instance terminal, cloning files from a GitHub Repository:
git clone `https://github.com/LSF970/sparta_test_app.git`

3) To ensure all files have been added to the EC2 instance do `ls`

4) Next print the following command `curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -` This command will download the NodeJs 

5) Now you will have to download NodeJs. Print the following command `sudo apt install nodejs -y`

6) To check the version of the Nodej enter `node -v`

 7) To install your applicaion enter `sudo npm install pm2 -g` following with `npm install`

(npm is the node package manager
ps2 is the project manager for node processes)

8) Finally enter: `node app.js` to run app 

WARNING: ensure the security group has an inboud rule for port 3000

