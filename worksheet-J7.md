	1.	What is inside a packet?
    - Header, payload and a trailer.

	2.	What is the purpose of the internet layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?
	•	The Internet layer handles routing packets across networks and translates IP addresses to MAC addresses. It ensures that packets reach the correct destination by using the IP address. You need to specify the destination IP address to route the packet correctly and ensure it reaches the correct server or recipient.
	
    3.	What is the purpose of the transport layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?
	•	The Transport layer manages data flow control, error-checking, and reassembly of packets. You need to specify the destination port number to direct the packet to the appropriate application or service on the receiving device.
	
    4.	What is the difference between SMTP and HTTP?
	•	SMTP (Simple Mail Transfer Protocol) is used for sending emails between servers, typically operating over TCP on port 25.
	•	HTTP (Hypertext Transfer Protocol) is used for transmitting hypertext, such as web pages, over the web, typically over port 80 (or 443 for HTTPS).
	
    5.	What is the difference between an IP address and a domain name?
	•	An IP address is a numerical label assigned to devices on a network, allowing communication across networks.
	•	A domain name is a human-readable name that maps to an IP address.

	6.	How does the operating system use ports?
	•	Ports are virtual endpoints in an operating system used to differentiate between various network services and applications.

	7.	Write code that creates a socket connection to IP address 123.45.678.900 at port 4040. Then, print a color to that socket’s output.

import socket

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect(('123.45.678.900', 4040))

    color = 'Red'
    s.sendall(color.encode('utf-8'))
    print(f"Sent color '{color}' to the server.")

	8.	What is the difference between a socket’s input stream and its output stream?
	•	A socket’s input stream is used to receive data from the other device, while the output stream is used to send data to the other device. 

	9.	What is the difference between a Socket and a SocketServer?
	•	A Socket represents a single endpoint in a network communication link, allowing connection and data exchange between a client and a server.
	•	A SocketServer listens for incoming connection requests on a specified port.

	10.	How are threads useful with servers? How does a server manage to always be listening for sockets trying to connect?
	•	Threads allow servers to handle multiple client connections simultaneously. Each client connection is handled by a separate thread, so the server can respond to multiple clients without blocking other connections.
	•	A server typically listens for incoming connections on a specific port using a main thread. When a client attempts to connect, the server accepts the connection, starts a new thread to handle communication with that client.