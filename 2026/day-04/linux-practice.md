## When i use Process Checks commands:
- ps: gives running processes with PID(process id) ,cmd(command name) and time(CPU time takes by that process) of current terminal only
- ps -aux: detailed running processes with user,PID,CPU%,Mem%,stat,time and cmd.
- top: dynamic view of running processes that changes continuously

## When i use Service commands:
- systemctl status <servive>: checks status of service
- systemctl list-units --type=service: shows every services present on the system with their load,active,description and sub-state

## When i use Log commands:
- journalctl -u <service>: shows logs of service
- journalctl -f: gives logs in real time
- tail -n 5 <filepath/filename> : gives last five logs of file

## Inspect of one service(nginx) on system (Troubleshooting flow):
- systemctl list-units --type=service | grep nginx: checks nginx is present or not 
- systemctl status nginx:gives status of nginx
- journalctl -u nginx -n 5 : gives last 5 logs of nginx

