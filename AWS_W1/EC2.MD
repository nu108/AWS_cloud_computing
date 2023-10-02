
# EC2- dashboard 

1) Name instance: `tech254_nadia_nginx`
2) Choose image 
3) Instance Type: t2.micro
4) Key pair: tech254

![key_pair.PNG](..%2F..%2F..%2F..%2FDownloads%2Fkey_pair.PNG)

5) Create security group: re-name to tech254_nadia_nginx


![security.PNG](..%2F..%2F..%2F..%2FDownloads%2Fsecurity.PNG)

6) ADD security rules 
7) Storage should remain as default 
8) Create instance 

9) Go on to gitbash 
10) Locate pem file : `cd .ssh`
11) `chmod 400 tech254.pem`
13) enter: `sudo apt update` 
14) enter: `sudo apt ugrade -y` 
15) enter `sudo apt install nginx -y`
16) enter: `sudo systemctl start nginx`
17) you can locate website from instances 
![ipweb.PNG](..%2F..%2F..%2F..%2FDownloads%2Fipweb.PNG)