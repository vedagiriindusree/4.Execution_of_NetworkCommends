# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>


DEVELOPED BY:Vedagiri Indu Sree    
REG.NO:212223230236         

## PROGRAM
## PING COMMAND

## CLIENT
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
## SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

## Output
## CLIENT

![image](https://github.com/23004513/4.Execution_of_NetworkCommends/assets/138973069/b53ac2f5-24c7-481c-bc98-cf5db18d2510)

## SERVER

![image](https://github.com/23004513/4.Execution_of_NetworkCommends/assets/138973069/c09a7fe7-d19b-425f-bcd0-db6570c949a2)


## TRANCEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## OUTPUT
## TRANCEROUTE COMMAND

![image](https://github.com/23004513/4.Execution_of_NetworkCommends/assets/138973069/2c9ce9c5-56bf-496f-b39c-86176db284ae)

## Result
Thus Execution of Network commands Performed 
