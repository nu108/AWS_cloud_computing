# Task: Research how to setup nginx so that by default, the default website will be http://localhost:3000/ (from the perspective of nginx) so you will just need to go to the app VM’s public IP address (no port 3000 in the URL) and the Sparta test app will be visible.

1) Install nginx use the following commands:

`sudo apt-get update`
`sudo apt-get install nginx`

2) Create a Nginx Server Block Configuration:
Create a new server block (virtual host) configuration file for your application in the /etc/nginx/sites-available/ directory. You can use a command like `sudo nano /etc/nginx/sites-available/app` to create and edit the file. App is the name of where the files where saved. 

3) Configure the server Block:
`server {
    listen 80;
    server_name your-server-ip;  # Replace with your server's public IP or domain name

    location / {
        proxy_pass http://localhost:3000;  # Forward requests to port 3000
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }

    # Additional Nginx configuration can go here if needed
}`


4) Enable server block
`sudo ln -s /etc/nginx/sites-available/app /etc/nginx/sites-enabled/`

5)Test and reload Nginx:
`sudo nginx -t`

6) If there are no errors print 
`sudo systemctl reload nginx`

We have now successfully set up a reverse proxy, and all searches for our public IP will now route us to the port 3000 so we can access our app.

# What are ports?

Ports are virtual endpoints in a network.Ports are used to route incoming network requests to the appropriate applications or processes running on a device. 

# What is a reverse proxy? How is it different to a proxy?

Proxy stands between you and the internet. When you request a web page, the proxy forwards your request to the internet and sends back the response to your computer. It can be used for privacy, security and catching.

Reverse proxy stands between users on the internet and web servers. When someone requests a web page from a server, the reverse proxy decides which server should handle the request and sends the response back to the user. Its used for load balancing, security and directing traffic to the right place.

Overall, the regular proxy forwards your request to the internet.Whereas reverse proxy forwards requests from the internet to the appropriate web server. 

What is Nginx's default configuration?

Nginx's default configuration is located in the `/etc/nginx/sites-available` directory. This directory contains configuration files for many websites or applications hosted on the Nginx server. These configuration files can be enabled by creating symbolic links to them in the `/etc/nginx/sites-enabled` directory.

# How to set up Nginx Reverse Proxy?

Above I have added the steps to set up a Nginx reverse proxy. It involves creating or modifying a server block configuration in the sites-available directory, configuring Nginx to listen on a specific port, and using the proxy_pass function to forward requests to the backend server or application. This allows Nginx to act as a reverse proxy, forwarding requests to the specified backend server based on the URL path.