## Commands Used: 
ssh -i <key-path> <user>@<IP> : to connect ec2 server to local
sudo yum install nginx : to install nginx service 
systemctl status nginx : to see the status of nginx
sudo systemctl start nginx : if status inactive ,start it with this command
journalctl -u nginx -n 50 : to view logs of nginx
ls -l nginx-log.txt : to view the information about nginx-log.txt file 
scp -i <key-path> <user>@<IP> : <source> <destination>: to copy nginx-log.txt file from server to local 
cat nginx-log.txt: to view the content of nginx-log.txt

## Challenges Faced:
- Realized my server not working on apt package installer ,it uses yum installer package 
- websites isn't loading even after installing nginx then found :
   - its inactive
   - its port 80 didn't open
  After it , website works

## What I Learned
- How to launch and connect to a cloud instance
- How to install and manage Nginx
- Importance of security groups
- How to read and extract logs
- Basic cloud troubleshooting flow
   
