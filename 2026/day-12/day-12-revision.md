## Day-12 Revision & Reflection 

## Mindset & Plan
- Reviewed day-01 learning plan and its going great
- just have to improve speed and accuracy in command usage
- Next Tweak : to improve troubleshooting confidence

## Processes & Services (Re-ran Commands)
- ps aux
- systemctl status ssh
- journalctl -u ssh -n 20
  
Observation: Processes ,service and logs looks normal 

## File Skills Practice
- echo "Test line" >> notes.txt
- vi script.sh  --> (in editor ) echo "Hello dosto!"
- chmod +x script.sh
- ./script.sh
- sudo chown tokyo:heist-team devops-file.txt
- ls -l

## Cheat Sheet Refresh
Top 5 Commands I’d Use in Incident:
- ls -l 
- ps aux --sort=-%cpu
- systemctl status
- journalctl -u service -n 50
- df -h

## User/Group Sanity check 
- sudo useradd squirtle
- sudo groupadd water-pokemon
- touch battle.txt
- sudo chown squirtle:water-pokemon battle.txt
- id squirtle
- ls -l battle.txt

## Mini Self-Check
1. Three Commands That Save Me most of time:

- systemctl status → to know state of service quickly
- journalctl -u → for log debugging
- ls -l → Permission and ownership check

2. How to Check Service Health?
- systemctl status <service>
- ps aux | grep <service>
- journalctl -u <service>

3. How to Safely Change Ownership & Permissions?
- Command: sudo chown user:group <file-name>
- Verify using: ls -l <file-name>

4. Focus for Next 3 Days
- Improve speed with troubleshooting
- Practice real scenarios again
- Get comfortable with log reading

## Key Takeaways
- Got Familiar with terminal .
- Consistency over perfection.
- Practice builds confidence
