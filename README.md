# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## FILE SERVER PROGRAM
```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```
## FILE CLIENT PROGRAM
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close()
```
## OUPUT
<img width="878" height="1032" alt="image" src="https://github.com/user-attachments/assets/5481867b-206e-4a8a-b54f-e00e074632dc" />
<img width="865" height="1070" alt="image" src="https://github.com/user-attachments/assets/c876e707-2bc0-4e7f-a20b-a9123b227b46" />
<img width="887" height="1027" alt="image" src="https://github.com/user-attachments/assets/8b792e12-fe5c-4c49-87b5-aa9622474f7a" />
<img width="692" height="993" alt="image" src="https://github.com/user-attachments/assets/899d1249-1bf6-40b9-a9bb-a6135238f9c5" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
