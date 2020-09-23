<div align="center">

## Basics of Sockets and Java


</div>

### Description

This is used to show a developer how to use and build Client / Server app's by using Sockets. This is very basic, and doesn't go over using UDP. Just TCP. (UDP = Datagrams.) *VOTE*
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[hamsters at xssi\.net](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/hamsters-at-xssi-net.md)
**Level**          |Beginner
**User Rating**    |4.2 (38 globes from 9 users)
**Compatibility**  |Java \(JDK 1\.1\), Java \(JDK 1\.2\)
**Category**       |[Classes](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/classes__2-83.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/hamsters-at-xssi-net-basics-of-sockets-and-java__2-2970/archive/master.zip)





### Source Code

```
****************************************************
Java Code for a Client Server - w/ Sockets
****************************************************
the following code will get you started using sockets and Java:
3 steps here:
1 - A server
2 - A client
3 - Data transfer
to initialize a client socket, the code would look something like this:
Socket clientSocket = null;
clientSocket = new Socket(10.1.1.1,5050)
This says that this socket is connecting to a computer with the ip: 10.1.1.1 on port 5050. Now ip could be used or a computer name. But before a client connects to a server socket, there has to be a server socket:
Socket serverSocket = null
serverSocket = new Socket(5050);
//Notice no host name or ip here
serverSocket.accept();
//Now accepting clients!
From the socket you must send and recieve data. (I/O)For this to happen you need to declare a PrintWriter for output and a BufferedReader for input.
(Client side here:)
PrintWriter out = null;
BufferedReader in = null;
Socket cleintSocket = null;
clientSocket = new Socket(10.1.1.1,5050);
out = new PrintWriter(clientSocket.getOutputStream(), true);
in = new BufferedReader( new inputStreamReader
( clientSocket.getInputStream()));
The PrintWriter out will be the front door for the socket's output. Calling out.printin("Hello") would send the string Hello to the server.
To finish, here how to use a loop to receive information:
PrintWriter out = null;
BufferedReader in = null;
Socket clientSocket = null;
String fromServer;
clientSocket = new Socket(10.1.1.1,5050);
out = new PrintWriter(clientSocket.getOutputStream(), true);
in = new BufferedReader( new inputStreamReader ( clientSocket.getInputStream()));
while((fromServer = in.readline()) != null) {
System.out.printin("Server: " + fromServer);
}
out.close();
in.close();
clientSocket.close();
```

