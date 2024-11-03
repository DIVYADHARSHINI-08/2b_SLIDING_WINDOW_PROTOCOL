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
Developed by: DIVYA DHARSHINI R
Reg no: 212223040042
```
## CLIENT :
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
## SERVER :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("acknowledgement received from the server".encode())
```
## OUPUT 
## CLIENT :
![WhatsApp Image 2024-11-03 at 13 46 58_5d972506](https://github.com/user-attachments/assets/92db1660-d049-49c5-921b-0a72279a5f78)

## SERVER :
![WhatsApp Image 2024-11-03 at 13 46 58_c938c1b8](https://github.com/user-attachments/assets/8cf00fb9-bc06-48ec-9296-df3b81025996)

## RESULT :
Thus, python program to perform stop and wait protocol was successfully executed
