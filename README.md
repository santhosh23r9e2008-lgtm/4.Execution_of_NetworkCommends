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

## Program

Client Program
```
import socket
from pythonping import ping

s = socket.socket()

s.bind(('localhost', 55555))

s.listen(5)

c, addr = s.accept()

while True:
    hostname = c.recv(1024).decode()

    try:
        result = ping(hostname, verbose=False)

        c.send(str(result).encode())

    except:
        c.send("Not Found".encode())
```

Server Program
```
import socket

s = socket.socket()
s.connect(('localhost', 55555))

while True:
    ip = input("Enter the website you want to ping: ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```

## Output


<img width="1327" height="940" alt="image" src="https://github.com/user-attachments/assets/18ec0b1d-6c39-410d-9ec7-51560f39cc3b" />


<img width="1332" height="959" alt="image" src="https://github.com/user-attachments/assets/82f000a2-c62b-48bb-baa1-1447e7d2feed" />



## Result
Thus Execution of Network commands Performed 
