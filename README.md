# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM

### CLIENT
```
import socket

s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))

s.send("Hello server!".encode())

with open('received_file', 'wb') as f:
    while True:
        print('receiving data...')
        data = s.recv(1024)
        print('data=%s' % (data))
        if not data:
            break
        f.write(data)
    f.close()

print('Successfully got the file')
s.close()
print('connection closed')
```
### SERVER
```
import socket
s = socket.socket()
host = socket.gethostname() port = 60000 s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f: while True:
print('receiving data...') data = s.recv(1024) print('data=%s', (data)) if not data:
break f.write(data)
f.close()
print('Successfully get the file') s.close()
print('connection closed')
```
## OUPUT


### CLIENT
<img width="581" height="239" alt="image" src="https://github.com/user-attachments/assets/2c095405-5346-457d-95d9-c957424e9bdf" />


### SERVER
<img width="528" height="73" alt="image" src="https://github.com/user-attachments/assets/6d6c9530-d335-477e-aaf7-676451279d21" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.
