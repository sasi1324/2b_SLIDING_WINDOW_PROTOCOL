# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
NAME:RAJAMANIKANDAN R
REG NO:212223220082
## AIM
To write a python program to perform sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
# CLIENT:
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
# SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT
# CLIENT:
![321075087-8df193e3-9e8c-4847-956f-cfca36dbd8d7](https://github.com/rajamanikandanravikumar/2b_SLIDING_WINDOW_PROTOCOL/assets/145742839/e66031e4-cd43-465d-aed1-49331de34287)
# SERVER:
![321075119-0970d724-a48d-4445-a48a-46f376bb308b](https://github.com/rajamanikandanravikumar/2b_SLIDING_WINDOW_PROTOCOL/assets/145742839/2a7686ed-60b0-43e6-82e1-cdc2ee87e8be)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
