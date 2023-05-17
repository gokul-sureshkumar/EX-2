# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:

AIM :
To write a python program to perform stop and wait protocol



ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6.Stop the program
```

PROGRAM :
Client.py:
```python 
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    i = input("Enter data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
 ```
Server.py:
``` python
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
OUTPUT :
```
Client output:
```
![2c](https://github.com/gokul-sureshkumar/EX-2/assets/121148715/d1f687a4-9694-4537-9ec6-e39b33d27388)
```
Server output:
```
![2s](https://github.com/gokul-sureshkumar/EX-2/assets/121148715/b2e38c30-4862-4fe3-8094-b682c26e0e34)
```


RESULT :
Thus, python program to perform stop and wait protocol was successfully executed


