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
# client:
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
# server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
# client:
![Screenshot 2024-02-29 220426](https://github.com/Gokztechz/2a_Stop_and_Wait_Protocol/assets/117667038/cf31ae83-8012-416b-aa21-6c9d417e723e)
# server:
![Screenshot 2024-02-29 220442](https://github.com/Gokztechz/2a_Stop_and_Wait_Protocol/assets/117667038/ea289238-d282-4d12-9c4f-fc9ea8697ccd)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
