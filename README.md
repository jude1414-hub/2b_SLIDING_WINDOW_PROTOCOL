# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Developed by : JUDE CLEMENT JOSE G

Reg no : 212224230109


Client.py

```
import socket 
s=socket.socket() 
s.bind(('localhost',9999)) 
s.listen(5) 
c,addr=s.accept() 
size=int(input("Enter number of frames to send : ")) 
l=list(range(size)) 
s=int(input("Enter Window Size : ")) 
st=0 
i=0 
while True: 
    while(i<len(l)): 
            st+=s 
            c.send(str(l[i:st]).encode()) 
            ack=c.recv(1024).decode() 
            if ack: 
                print(ack) 
                i+=s
```


Server.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',9999))
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT

![Screenshot 2025-04-12 105945](https://github.com/user-attachments/assets/8b83008a-0327-4cc1-8e5f-ef3d65f00db3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
