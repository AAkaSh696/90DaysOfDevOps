## Target Service 
nginx

## Environment Basics
- uname -a: confirms linux kernel version and system architecture
- cat /etc/os-release: Detected linux version (Amazon Linux)
  
## File System Sanity
- mkdir /tmp/runbook-demo/ : file created , writable and not read only
- cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo: file copied and correctly exists , no space and permission issue 

## Snapshot: CPU & Memory
- top: CPU usage normal ,no abnormal spikes
- free -h: sufficient memory available
- ps aux | grep nginx: nginx processes running with stable memory usage

## Snapshot: Disk & IO
- df -h: no disk full condition
- du -sh /var/log: disk usage of log directory is normal

## Snapshot: Network
- ss tulnp: firstly, didnt find nginx port 80 ,found out its inactive (systemctl status nginx) later made active(systemctl start nginx) 
- ping google.com: Network connectivity properly working

## Logs reviewed
- journalctl -u nginx -n 20: no recent error found
- journalctl -xe: no critical system level issue

## Quick findings
- nginx is running on port 80
- CPU and Memory usage is normal
- Disk space is healthy
- No errors in logs

## If this worsens (next steps)
- restart service: systemctl restart nginx 
- increase log review range to know better
- Check firewall or port blocking issue 
