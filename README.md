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

```
NAME : Jude Clement Jose G

REGISTER NUMBER : 212224230109
```
## CLIENT:
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recieved".encode())
```
## OUTPUT

## CLIENT:
<img width="960" alt="2ac" src="https://github.com/user-attachments/assets/a0f38acc-b070-4b96-b40f-c05d55b7446a">

## SERVER:
<img width="960" alt="2as" src="https://github.com/user-attachments/assets/1b3fd4e3-f3f5-4a25-93fb-e6f240eee6ee">

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
