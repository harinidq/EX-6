# EX-6 IMPLEMENTATION OF PING COMMAND
DATE :12-04-2023

# AIM :
To write the python program for simulating ping command.

# ALGORITHM :
```
1.start the program.
2.Include necessary package in java.
3.To create a process object p to implement the ping command.
4.declare one Buffered Reader stream class object.
5.Get the details of the server
6.length of the IP address.
7.time required to get the details.
8.send packets, receive packets and lost packets.
9.minimum, maximum and average times.
10.print the results.
11.Stop the program.
```
# PROGRAM :
## CLIENT :
```
# Developed by : M.D.HARINI
# Register Number : 212222230043
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
 ```
## SERVER :
```
# Developed by : M.D.HARINI
# Register Number : 212222230043
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
# OUTPUT :
## CLIENT :
![image](https://github.com/harinidq/EX-6/assets/113497680/5817e96c-7c99-4f01-9256-15461947d10e)

## SERVER :
![image](https://github.com/harinidq/EX-6/assets/113497680/8e662942-e217-4124-805d-ade4605954c8)

# RESULT :
Thus, the python program for simulating ping command was successfully executed.
