# 2a_Stop_and_Wait_Protocol
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
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  i=input("Enter a data: ")
  c.send(i.encode())
  ack=c.recv(1024).decode()
  if ack:
     print(ack)
     continue
  else:
     c.close()
     break
```
```
server:

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT:
![Screenshot 2024-03-06 201135](https://github.com/Harshhinii/2a_Stop_and_Wait_Protocol/assets/148633023/73fb233b-6e3f-4b6a-905f-ca1764437151)

SERVER:
![Screenshot 2024-03-06 201148](https://github.com/Harshhinii/2a_Stop_and_Wait_Protocol/assets/148633023/706dd463-5282-4dd0-aebc-090df0346fab)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
