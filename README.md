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
## Client Program
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
## Server Program
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
![output 1](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/147473131/6268f456-bf03-4e0c-83d9-dfac31a4f416)
![output 2](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/147473131/8bd2f33b-ff83-4819-a98e-09a0ad1cd4dc)
![output 3](https://github.com/NaliniG007/2a_Stop_and_Wait_Protocol/assets/147473131/e44744f0-ac79-4600-9067-d737c8849df0)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
