# Research what PM2 is, why is it useful? And what are some of the commands we can use to interact with node processes?
open-source process manager for Node.js applications. It is designed to simplify the deployment and management of Node.js applications in production environments.

# PM2 Commands:

`pm2 start <app.js>`: Starts a Node.js application specified by the <app.js> file.

`pm2 stop <app>`: Stops a running Node.js process managed by PM2. You can specify either the application name or process ID.

`pm2 restart <app>`: Restarts a running Node.js process. Like stop, you can specify either the application name or process ID.

`pm2 list`: Lists all running Node.js processes managed by PM2, showing their status, names, and other information.

`pm2 log <app>`: Displays the logs for a specific application.

`pm2 monit` Opens an interactive monitoring interface that shows real-time CPU and memory usage for all running processes.

`pm2 delete <app>`: Deletes a process from PM2's process list. You can specify either the application name or process ID.

`pm2 startup`: Generates and configures startup scripts for various platforms (e.g., systemd, init.d) to ensure that PM2 processes start automatically on system boot.

`pm2 save`: Saves the current list of running processes so that they can be automatically restarted after system reboots.

PM2 is a valuable tool for managing Node.js applications in production environments, as it simplifies deployment, improves application reliability, and provides essential monitoring and management features. It is widely used by developers and organizations hosting Node.js applications.





