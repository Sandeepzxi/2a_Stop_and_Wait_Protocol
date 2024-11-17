# 2a Stop and Wait Protocol
## Name: Sandeep S
## Reg.NO: 212223220092
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
### CLIENT
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
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### CLIENT
![image](https://github.com/user-attachments/assets/e924fd2e-47f2-41e2-b796-4b9ceee507c6)


### SERVER
![image](https://github.com/user-attachments/assets/844e2f87-825e-4093-9056-60a5f04e2c6e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
