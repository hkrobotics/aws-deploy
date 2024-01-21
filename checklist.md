# Till now we have covered

- Creating EC2 instance
- Managing security groups (inbound - TCP) -> Reason for this is to allow SSH and HTTP traffic
- Hosting vite app on EC2 instance
- Creating Elastic IP -> This is to make sure that the IP address of the EC2 instance is static

# Next Challenge

The app keeps running as long as the terminal is open. We need to make sure that the app keeps running even after the terminal is closed.

# Solution

We will use PM2 to keep the app running in the background. PM2 is a process manager for Node.js applications. It allows you to keep applications alive forever, to reload them without downtime and to facilitate common system admin tasks.

# Steps

- Install PM2 on the EC2 instance `npm install pm2 -g`
- Start the app using PM2 `pm2 start npm -- start`
- Save the PM2 process list `pm2 save`
- Generate startup script `pm2 startup`
- Copy the generated command and run it on the terminal
- Check the status of the app `pm2 status`
- Check the logs of the app `pm2 logs
