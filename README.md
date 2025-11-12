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

## program
client

```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('mytext.txt', 'wb') as f:
 while True:
    print('receiving data...')
    data = s.recv(1024)
    print('data=%s', (data))
    if not data:
        break
    f.write(data)
f.close()
print('Successfully get the file')
s.close()
print('connection closed')
```
server

```
import socket
port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)
while True:
    conn, addr = s.accept()
    data = conn.recv(1024)
    print('Server received', repr(data))
    filename='mytext.txt'
    f = open(filename,'rb')
    l = f.read(1024)
    while (l):
        conn.send(l)
        print('Sent ',repr(l))
        l = f.read(1024)
    f.close()
    print('Done sending')
    conn.send('Thank you for connecting'.encode())
    conn.close()
```
## Output

client

<img width="569" height="263" alt="Screenshot 2025-11-03 105126" src="https://github.com/user-attachments/assets/40503c75-b8ef-45db-bb9c-37941c20ce52" />

server

<img width="666" height="208" alt="Screenshot 2025-11-03 105147" src="https://github.com/user-attachments/assets/e0913400-4d47-46cd-b744-8c798e1d1424" />
 
 netstat
<img width="950" height="1072" alt="Screenshot 2025-11-12 102525" src="https://github.com/user-attachments/assets/548574fa-708b-499e-bc57-ba2a6cbd23b7" />

ipconfig

<img width="1058" height="978" alt="Screenshot 2025-11-12 102640" src="https://github.com/user-attachments/assets/8a74c117-7c00-40fc-ade0-6db459ffd69c" />


ping

<img width="835" height="380" alt="Screenshot 2025-11-12 102723" src="https://github.com/user-attachments/assets/7455cb6e-4d40-4575-a2fd-eb795d872f4d" />

tracert

<img width="931" height="489" alt="Screenshot 2025-11-12 102948" src="https://github.com/user-attachments/assets/a1d39f7e-050b-462f-8b9e-66d5d1282243" />

nslookup

<img width="821" height="676" alt="Screenshot 2025-11-12 103056" src="https://github.com/user-attachments/assets/a14d61cb-65dd-40d9-ac4a-4b38565b8ce9" />

getmac

<img width="935" height="308" alt="Screenshot 2025-11-12 103138" src="https://github.com/user-attachments/assets/e68fbde8-8de6-4610-960f-2d56683dc333" />

hoatname

<img width="732" height="385" alt="Screenshot 2025-11-12 103157" src="https://github.com/user-attachments/assets/b2451db5-9a03-45b4-aea4-1a06cdf190a8" />

nbtstat

<img width="938" height="784" alt="Screenshot 2025-11-12 103235" src="https://github.com/user-attachments/assets/3d5cf16c-bd46-4c54-81ab-d2462f1fcf85" />

arp

<img width="949" height="906" alt="Screenshot 2025-11-12 103300" src="https://github.com/user-attachments/assets/cead0615-b19b-474f-83e3-2ca5ecb8bfd0" />

systeminfo

<img width="1517" height="1085" alt="Screenshot 2025-11-12 103403" src="https://github.com/user-attachments/assets/d7fcf990-b595-4d62-bd04-e45ede5d4f69" />


## Result
Thus Execution of Network commands Performed 
