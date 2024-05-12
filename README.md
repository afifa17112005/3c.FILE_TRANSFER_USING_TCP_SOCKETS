# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
   Name:A.Afifa Reg.no:212223040008
## PROGRAM:
## CLIENT:
```import socket 
s = socket.socket() 
host = socket.gethostname() 
port = 60000 
s.connect((host, port)) 
s.send("Hello server!".encode()) 
with open('received_file', 'wb') as f: 
    while True: 
        print('receiving data...') 
        data = s.recv(1024) 
        print('data=%s', (data)) 
        if not data: 
            break 
        f.write(data) 
f.close() 
print('Successfully get the file') 
s.close() 
print('connection closed')
```
## SERVER:
```import socket                    
port = 60000                    
s = socket.socket()              
host = socket.gethostname()      
s.bind((host, port))
s.listen(5)                      
while True: 
    conn, addr = s.accept()      
    data = conn.recv(1024) 
    print('Server received', repr(data)) 
    filename='mytext.txt' 
    f = open(filename,'rb') 
    l = f.read(1024) 
    while (l): 
       conn.send(l) 
       print('Sent ',repr(l)) 
       l = f.read(1024) 
    f.close() 
    print('Done sending') 
    conn.send('Thank you for connecting'.encode()) 
    conn.close()
```
## OUPUT:
## CLIENT:
![310606572-e8c557db-4b64-4e1d-981a-4bfbcb76189f](https://github.com/afifa17112005/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/147080931/93335e6d-ea35-4e52-99c1-3339ccbb18a5)

## SERVER:
![310606714-ce13c14c-68b8-4036-b914-39cf5517c271](https://github.com/afifa17112005/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/147080931/3f7375b2-dfa5-477d-b61b-85bc640a9cc0)

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
