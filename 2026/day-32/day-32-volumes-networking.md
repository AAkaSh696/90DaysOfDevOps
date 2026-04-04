## Day 32 – Docker Volumes & Networking
** NOTE: For practical refer to images on github or linkedin 

## Task 1: The Problem
(Practical) 
- In this case , after removing the container all data get lost from container because data are in container(isolation)

## Task 2: Named Volumes
(Practical) 
- Yes, the data in still there because we adds local storage to it

## Task 3: Bind Mounts
(Practical)
- Volume is managed by Docker but  Bind mount is specific folder on your computer that you directly link to the container

## Task 4: Docker Networking Basics
(Practical)
- Nope they cant ping by name but can by ip

## Task 5: Custom Networks
(Practical)
- Yes , now they can ping each other by name because we add common network to both
- The default bridge is built for basic safety and isolaton, so it only lets containers talk via IP addresses, but custom networks have a built-in "phonebook" (DNS) that automatically links container names to their IPs.

## Task 6: Put It Together
(Practical)
