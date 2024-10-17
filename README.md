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
### DEVELOPED BY:HARISH S
### REG NO:212223230071
## CLIENT
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

## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("acknowledgement received from the server".encode())
```
## OUPUT:
## CLIENT
![Screenshot (324)](https://github.com/user-attachments/assets/5f76115a-92b8-472f-b89c-b8b0e9d8528b)

## SERVER
![Screenshot (323)](https://github.com/user-attachments/assets/553a771b-191c-407a-8d80-d6b0bf80e466)
Thus, python program to perform stop and wait protocol was successfully executed
