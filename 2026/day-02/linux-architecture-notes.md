## Core Components of Linux
1) kernel: - heart(core of linux)
           - acts as bridge between hardware and software applications
           - manages system resources(CPU, disk, memory and processes)
2) user-space: - place where users and software/applications runs like nginx,docker etc.
               - communicates with kernel using system calls
3) init/systemd: - first process started with boot(PID 1)
                 - starts and manages services
                 - restarts failed services
                 - handles system logs using journalctl
   
## How process created and managed 
"Everything in linux is process" 
-Every process is created by another process
-fork()->used by parent process
-child process gets a new PID
-exec() loads the actual program
-ps,top->show processes , kill->stop processes , ctrl+z->pause process

## Process States 
-running(R):process uses or ready to use CPU
-sleeping(S):process waits for input or event e.g., user input
-uninterruptable sleep(D): process waiting for disk operation
-stopped(T): process terminated 
-zombie(Z): finished execution but not cleaned by parent

## Useful Command I'd use daily
-cd: change directory 
-ps aux: show running processes
-cat : display,create,combile file contents 
-top: live CPU and memory usage 
-pwd: print working directory 
