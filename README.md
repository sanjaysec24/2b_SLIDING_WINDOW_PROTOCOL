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
```
sanjay kumar .B
212224230242
```
## Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
![Screenshot 2025-04-12 134814](https://github.com/user-attachments/assets/56302dcd-405d-4a00-9798-7bbb3eaada07)

![Screenshot 2025-04-12 134824](https://github.com/user-attachments/assets/b2b04390-fe58-45c7-934d-09b49373e86b)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
