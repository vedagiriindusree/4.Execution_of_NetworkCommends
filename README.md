# 4.Execution_of_NetworkCommands
# NAME : Vedagiri Indu Sree
# REG NO : 212223230236
## AIM :
Use of Network commands in Real Time environment
## Software :
Command Prompt And Network Protocol Analyzer
## Procedure:To do this EXPERIMENT- follows these steps:
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

## PROGRAM:
### PING COMMAND:

# CLIENT:
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
# SERVER:
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

### TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output:

# CLIENT:

![image](https://github.com/DHIRAVIYASUNDARAM/4.Execution_of_NetworkCommends/assets/165143880/1fb9eae4-22c1-436e-a964-973c622852df)

# SERVER:

![4-2](https://github.com/VPOOJAASREE/4.Execution_of_NetworkCommends/assets/155145525/ee38335b-f844-4f1a-94fd-aec00c83371b)

# TRACEROUTE COMMAND:
<img width="740" alt="Traceroute cmd" src="https://github.com/Ganesh23013987/4.Execution_of_NetworkCommends/assets/147473768/d689bf3e-8c86-4991-b7dd-258e6329d92b">

## Result:
Thus Execution of Network commands Performed 
