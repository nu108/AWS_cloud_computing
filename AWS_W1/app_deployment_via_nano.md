# Automation Script:

1) Create and open a script file 
Enter following command: `nano provision_app.sh`

2)Write the bash script 

`#!/bin/bash`

`# cloning the app files to the instance`
`git clone https://github.com/LSF970/sparta_test_app.git `

`# tell the os what version of nodejs you want`
`curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash`

`# install nodejs`
`sudo apt install nodejs -y`

`# install process manager`
`sudo npm install pm2 -g`

`# go to the app folder`
`cd /sparta_test_app/app`

`# install your app`
`npm install`

`# run the app`
`node app.js`

3) After entering script press ctrl + x to exit 
Y to save file 
Enter to confirm file name 

4) Add permission for this script to run 
`sudo chmod +x provision_app.sh`

5) Name the script 
`./ provision_app.sh`