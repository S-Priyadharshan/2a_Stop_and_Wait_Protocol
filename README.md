## 2a_Stop_and_Wait_Protocol
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
## client:
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
## server:
```
   import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

## OUTPUT
## client:
![Screenshot 2024-02-28 142234](https://github.com/Bhagath118/2a_Stop_and_Wait_Protocol/assets/147473779/574edc48-8425-4b30-a1cb-75b24d1d3ad9)


## server:

![Screenshot 2024-02-28 142311](https://github.com/Bhagath118/2a_Stop_and_Wait_Protocol/assets/147473779/76ba0102-7d22-4426-ae5f-1cf506472bdd)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
