# 4.Execution_of_NetworkCommands
## Name:Vedagiri Indu Sree
## Reg No:212223230236
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 

All commands related to Network configuration which includes how to switch to privilege mode

and normal mode and how to configure router interface and how to save this configuration 

flash memory or permanent memory.

This commands includes

• Configuring the Router commands

• General Commands to configure network

• Privileged Mode commands of a router 

• Router Processes & Statistics

• IP Commands

• Other IP Commands e.g. show ip route etc.

## Program:

## Ping Command:

## Client:

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
## Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
## TraceRoute Command:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output:
## Ping Command:
## Client:

![image](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/d1b600aa-03b5-472b-87d0-051ac81eaf8a)
## Server:

![image](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/215790b0-ac3b-4e90-9556-bb6d31eb2821)

## TraceRoute Command:

![image](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/b91ffc13-60ea-4e8b-8672-2ed82eb9e0a6)

## Result:
Thus Execution of Network commands Performed.
