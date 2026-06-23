Day 3 - Processes and Services


Today I learned processes and service commands:

What is running?
Who started it?
Why is CPU high?
Which service is listening on a port?



- ps - viewing running process
- ps aux - viewing running processes but with detailed info
- top - live monitoring system
- pgrep - find process ID by name
- kill -  stop the process
- jobs - view background jobs
- systemctl - manage services
- ss -tuln - listening to/checking open ports and connections


SCREENSHOT OF PROCESSES AND SERVICE COMMANDS:

<img width="509" height="370" alt="Screenshot 2026-06-23 at 7 25 23 PM" src="https://github.com/user-attachments/assets/4d1fe451-9fe1-4069-bda3-a84e9b5cd319" />




Mini Lab 
Performed this lab after learning the processes and service commands:

Open another terminal and run:

sleep 300

<img width="638" height="266" alt="Screenshot 2026-06-23 at 7 25 05 PM" src="https://github.com/user-attachments/assets/6976dd3b-9e59-4f7f-bac8-17b4a131c2a9" />


In your first terminal:

ps aux | grep sleep

Find its PID.

Then:

kill PID

<img width="674" height="266" alt="Screenshot 2026-06-23 at 7 24 55 PM" src="https://github.com/user-attachments/assets/5ddc6d74-d88f-4d0d-b9e7-661d29eddc2d" />


Verify it stopped.



What I Learned

A process is a running program.

Services are background programs that keep the system functioning.

Processes can be monitored and terminated when necessary.

Security Relevance

- Detect suspicious processes
- Identify unwanted services
- Investigate resource abuse
- Find open ports
