# System Design Concepts

Building scalable, production-ready applications is both art and science. Science, in that it requires knowledge of many topics in computer engineering; art, in that it demands an eye for making smart design choices and piecing together the right technologies.

This page covers some fundamentals and concepts learnt from AlgoExpert for System Design. (source: Algoexper.io)

##### Table of Contents  
[Client-Server Model](#Client—Server-Model)  
[Network Protocols](#Network-Protocols)   


<a name="Client—Server-Model"/>

## Client-Server Model

A client is a thing that talks to servers. A server is a thing that talks to clients. The client—server model is a thing made up of a bunch of clients and servers talking to one another. 

And that, kids, is how the Internet works!

#### Client 

A machine or process that requests data or service from a server.  Note that a single machine or piece of software can be both a client and a server at the same time. For instance, a single machine could act as a server for end users and as a client for a database.    

#### Server

A machine or process that provides data or service for a client, usually by listening for incoming network calls.  Note that a single machine or piece of software can be both a client and a server at the same time. For instance, a single machine could act as a server for end users and as a client for a database. 

#### Client—Server Model

The paradigm by which modern systems are designed, which consists of clients requesting data or service from servers and servers providing data or service to clients. 

#### IP Address

An address given to each machine connected to the public internet. IPv4 addresses consist of four numbers separated by dots: a.b.c.d where all four numbers are between 0 and 255. Special values include: 
<pre>
    - 127.0.0.1: Your own local machine. Also referred to as localhost. 
    - 192.168.x.y: Your private network. For instance, your machine and all machines on your private wifi network will usually have the 192.168 prefix. 
</pre>   

#### Port

In order for multiple programs to listen for new network connections on the same machine without colliding, they pick a port to listen on. A port is an integer between 0 and 65,535 (216 ports total).  Typically, ports 0-1023 are reserved for system ports (also called well-known ports) and shouldn't be used by user-level processes. Certain ports have pre-defined uses, and although you usually won't be required to have them memorized, they can sometimes come in handy. Below are some examples: 
 
<pre> 
    - 22: Secure Shell
    - 53: DNS lookup
    - 80: HTTP
    - 443: HTTPS
</pre>    
		
#### DNS

Short for Domain Name System, it describes the entities and protocols involved in the translation from domain names to IP Addresses. Typically, machines make a DNS query to a well known entity which is responsible for returning the IP address (or multiple ones) of the requested domain name in the response. 


<a name="Network-Protocols"/>

## Network Protocols

#### IP

IP Stands for Internet Protocol. This network protocol outlines how almost all machine-to-machine communications should happen in the world. Other protocols like TCP, UDP and HTTP are built on top of IP. 

#### TCP

TCP Network protocol built on top of the Internet Protocol (IP). Allows for ordered, reliable data delivery between machines over the public internet by creating a connection. TCP is usually implemented in the kernel, which exposes sockets to applications that they can use to stream data through an open connection.

#### HTTP

HTTP The HyperText Transfer Protocol is a very common network protocol implemented on top of TCP. Clients make HTTP requests, and servers respond with a response. 

Requests typically have the following schema: 

- host: string (example: amazon.com)
- port: integer (example: 80 or 443)
-	method: string (example: GET, PUT, POST, DELETE, OPTIONS or PATCH)
-	headers:  pair list (example: "Content-Type" => "application/json")
-	body: opaque sequence of bytes
	
Responses typically have the following schema: 
- status code: integer (example: 200, 401)
-	headers:  pair list (example: "Content-Length" => 1238)
-	body: opaque sequence of bytes

#### IP Packet
Sometimes more broadly referred to as just a (network) packet, an IP packet is effectively the smallest unit used to describe data being sent over IP, aside from bytes. An IP packet consists of: 

-	an IP header, which contains the source and destination IP addresses as well as other information related to the network 
-	a payload, which is just the data being sent over the network
