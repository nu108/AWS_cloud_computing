# Why AMI over script?

# Script 
- more flexible 
- Automation 
- Lost control 
- Dynamic 
- Version control 

# AMI 
- Consistency 
- Scaling
- Security 
- DR 
- Faster to launch

# How to create an AMI?
- create the EC2 that you would like to replicate 
- go to the EC2 page 
- click on Actions on EC2 
- keep default settings 
- click 'Tag image & snapshots together'
- Lastly click create AMI 

# What is Mongo DB

MongoDB is a versatile database system that can be used for a wide range of use cases where flexible, scalable, and high-performance data storage is required. It's particularly well-suited for applications with rapidly changing data structures or large volumes of semi-structured data.

# How to use Mongo DB 

1) Create a standard EC2 name it `tech254_nadia_app`

When creating the EC2 instance make sure you use the AMI created. Then launch the EC2 instance and connect it to the gitbash terminal 

2) Create a MongoDB EC2 name it `tech254_nadia_mongodb`

When creating the MongoDB EC2 instance add MongoDB port: 27017. Then launce EC2 instance and connect it to a seperate git bash terminal. Also, change root to 

# Warning - ensure two seperate terminals are created 

3) on both instances do `sudo apt upgrade -y`

4) on the DB terminal you need to download MongoDB 

ENTER FOLLOWING COMMANDS:
`wget -qO - https://www.mongodb.org/static/pgp/server-3.2.asc | sudo apt-key add -`

NEXT:

`echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list`

NEXT:

`sudo apt update`

NEXT:

`sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20`

NEXT:

`sudo nano /etc/mongod.conf`

In this command permission change it to 0/0/0/0. This allows everyone to view the profile.

After this follow with the following commands:

`sudo systemctl start mongod`
`sudo systemctl enable mongod`
`sudo systemctl status mongod`

Now connect the second terminal to the MongoDB instance. 

Use the following command:

`export DB_HOST=mongodb://<your_ip_here>:27017/posts`

# Note: the ip should be the MongoDB EC2 

NEXT: 

`npm install`

`sudo apt install node.js -y`

Lastly enter: `node app.js`

To view the website: copy the IP from the app EC2 and upload it to the browser.

