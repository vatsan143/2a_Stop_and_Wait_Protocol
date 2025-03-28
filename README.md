# Ex2a_Stop_and_Wait_Protocol
### SRIVATSAN G
### 212223230216

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM
### Client:
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
    print(ack)
c.close()

```
### Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
~~~

## OUTPUT
### Client:
![Screenshot 2025-03-28 140245](https://github.com/user-attachments/assets/b00a4be6-5c72-43af-b0cd-fd9b0433ba71)

### Server:
![Screenshot 2025-03-28 140302](https://github.com/user-attachments/assets/456ae4d0-f48a-4094-bea4-e08811734135)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
