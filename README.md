# 4.Execution_of_NetworkCommands
## Name:Vedagiri Indu Sree
## Reg No:212223230236
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
## Program:
## Ping Command:
## Client:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
while True:
    c,addr=s.accept()
    print("Connecting from ",addr)
    try:
        hostname=c.recv(1024).decode().strip()
        if hostname:
            try:
                response=str(ping(hostname,verbose=True))
                c.send(response.encode())
            except Exception as e:
                c.send("ping failed  {}".format(e).encode())
        else:
            c.send("Hostname not provided".encode())
    except Exception as e:
        print("Error: ",e)
    finally:
        c.close()
        ```
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
try:
    while True:
        ip= input("Enter Website u want to ping :")
        s.send(ip.encode())
        response=s.recv(1024).decode()
        if response:
            print ("Ping result :",response)
        else:
            print ("No response from server")
except Exception as e:
    print ("Error:", e)
finally:
    s.close()
```
## Output
## Client:
![image](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/5aae724c-4c5d-43a2-b3cc-1f7765b89402)
## Server:
![Screenshot 2024-05-06 214344](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/c123376e-cb67-469c-b4c9-0acbb76325f4)
## TraceRoute Command:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output:
## TraceRoute Command:
![Screenshot 2024-05-06 220129](https://github.com/vedagiriindusree/4.Execution_of_NetworkCommends/assets/149366776/0c0098eb-6d8d-4be2-bd5f-8cbd21fb99a7)
## Result
Thus Execution of Network commands Performed 
