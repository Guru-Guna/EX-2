# IMPLEMENTATION OF STOP AND WAIT PROTOCOL

# EXP: 2

# DATE:15-03-2023

# AIM :
## To write a python program to perform stop and wait protocol


# ALGORITHM :
 1. . Start the program.
 2. Get the frame size from the user
 3. To create the frame based on the user request.
 4. To send frames to server from the client side.
 5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
## 6. Stop the program

# CLIENT PROGRAM :
```PYTHON 3 

import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

```
# SERVER PROGRAM :
```PYTHON 3
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())

```


# SERVER OUTPUT :
![out1](https://github.com/Guru-Guna/EX-2/assets/93427255/06e0e5aa-9487-4466-b29b-3a1f8cc00498)

# CLIENT OUTPUT :
![out2](https://github.com/Guru-Guna/EX-2/assets/93427255/754c8442-ca3e-484c-9d05-f827676c4dbc)



# RESULT :
## Thus, python program to perform stop and wait protocol was successfully executed.



