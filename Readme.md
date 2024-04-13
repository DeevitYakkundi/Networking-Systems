Networking systems
---

*This page documents notes of 
**Computer Networking Full Course - OSI Model Deep Dive with Real Life Examples 
by Kunal Kushwaha***

https://www.youtube.com/watch?v=IPvYjXCsTg8&t=3648s&ab_channel=KunalKushwaha

---

**Network** is connecting between two computers.

**Internet** is collection of computer networks

**ARPA** : Advance Research Program Agency :- To keep USA #1 in world
ARPA network consisted of connection between MIT, STANFORD, UCLA, UTAH .

**Protocol:  R**ules set by the internet are protocols. Internet society created and established these rules.
                   [Internetsociety.org](http://Internetsociety.org)

---

### How it basically works?

**Client send request to server (e.g. [google.com](http://google.com/)) > server sends response to the client with the webpage**

1. **Transmission Control Protocol (TCP)** 
It ensures 100% of the data is reaching the receiver.
2. **User datagram protocol (UDP)** 
Not 100% 
e.g. video calls
3. **Hypertext transfer protocol (HTTP)**
Used by web browsers, clients and servers for communication.

**IP Address :** Unique code with location of all the computers.
To check IP of own computer `curl if[config.me](http://config.me/) -s`

Internet service provider (ISP) > Modem- Router > Devices 

- ISP and Router have **global IP address.**
- Devices will have **local IP address**
- Router gives local IP by **DHCP** Dynamic Host Configuration Protocol *is a network management protocol that automatically assigns IP addresses and other configuration information to devices connected to a network.*
- When browsing Google will get only global IP
- Router decides who is the one had a request using **Network Access Translator (NAT )**
    
    **Ports :** Determine which application has requested access, where as IP address tell location and ports tell which application.
    Port is a 16 bits number
    
    - Total possible outcomes are 2^16 = **65536** numbers
        
        All HTTP are request and response are done on port 80.
        
        SQL 1433
        
        0-1023 are reserved ports
        
        1024-49152  some applications
        
    
- **Speeds**
    
    1MBPS - 10^6
    
    1GBPS - 10^9
    
    1KBPS - 10^3
    

---

<aside>
💡 How countries are connected?
https://www.submarinecablemap.com/

</aside>

---

### Types of Computer Networks

1. **Local Area Network (LAN)** 
    - Small area network, house , office.
    - Via ethernet, WIFI
2. **Metropolitan Area Network (MAN)**  
    - Across cities
3. **Wide Area Network (WAN)** 
- Wide area network, Across countries o**ptical fiber cables**
    
    1)  SONET Synchronous optical networking :  using optic fiber network.
    
    2) Frame Relay : Local area network to wide area network.
    

---

## Modem?

- Converts digital signals to analog signals and visa versa.
- Digital data from the computer to electrical signals to transfer over a network.

## Router?

Routes the data packets based on the IP address.

Internet service provider (ISP) are connected to other services providers.

- Tiers of routes
    
    Tier 1:- TATA
    
    Tier 2 :- Airtel, Actfiber Net, BSNL.
    

---

## Topologies

### 1) Bus

![image](https://github.com/DeevitYakkundi/Networking-Systems/assets/88937605/1c363d7c-a34e-4067-ae4c-f2b1dd4d2b2a)


If one thing breaks down the whole gwad damn thing fails

### 2) Ring

![image](https://github.com/DeevitYakkundi/Networking-Systems/assets/88937605/6392314c-565e-4642-bf17-e62716bc7f6c)


- If A has to communicate with D then data has to be passed to B> C and then D.
- One cable breaks then system fails.
- Lot of unnecessary calls are made.

### 3) Star

![image](https://github.com/DeevitYakkundi/Networking-Systems/assets/88937605/a55a2353-82cc-4810-9f0a-2abb22cb902f)


- If the central device fails the system fails.
- Central hub forms a mediator

### 4) Tree

![image](https://github.com/DeevitYakkundi/Networking-Systems/assets/88937605/b66039ed-d19d-498a-9334-7cb414a3e1fd)


Combination of bus and star topology.

### 5) Mesh

![image](https://github.com/DeevitYakkundi/Networking-Systems/assets/88937605/6109cd1a-72b0-41ba-8e76-ce0a0bc42f77)


- Every single computer is connected to everyone single computer.
- Very expensive.
- Scalability issues.

---

## STRUCTURE OF THE NETWORK

### Open System Interconnection Model (OSI)

- It has 7 layers
    
    1) Application layer
    
    2) Presentation
    
    3) Session
    
    4) Transport
    
    5) Network
    
    6) Data link
    
    7) Physical
    

### 1) Application Layer

- Implemented in software
- Sent a data over app layer to presentation layer

### 2) Presentation Layer

- Accept data converts these data into **machine representable binary format.**
- Then undergoes **encoding and encryption** i.e. changing the data that is only readable to that the person is responsible.
- From **ASCII** to **EBCBIC** .This process is called **translation.**
- Also provides **abstraction**
- **Compressed**

### 3) Session Layer

Basically helps setting and managing connections and enable sending- receiving data followed by termination of the connected sessions

- Before session starts it authenticates the process (asking user name and passwords).
- Assumes the layers below (transport layer) is working properly

### 4) Transport Layer

- Transports data by following protocols to the receiver.
- It has its own protocol how data will be transferred
- We all know the data will not be transferred in bulk, will be sent in chunks called Segments.
    - Segmentation: It will be divided into small segments
    - Every segment contains source and destinations **Port** **number.**
    - Every segment will have a sequence number which will help to reassemble in the right order.
    - Flow control : it controls the amount of data that has to be transferred
    - Error control.
    - Check sum : checks if everything is received or not

### 5) Network layer

- Transmission of the received data segment from one computer to another that is located in another different network.
- Communication with other computers
- Router lives here

### **Functions of Network layer**

1. **Logical addressing** : Assigns senders and receivers IP address to every segment that forms a **IP packet.** So that every data packets will reach the correct destination.
2. Also performs routing i.e. logical addressing.
3. Load balancing happens here.

- What does a packet contain?
    
    Senders IP, Receiver IP , **Subnet mask** 
    

### 6) Data link layer

Now which application to send this data to? 

This is done by  physical addressing. Which is done in data link layer.

- What are Physical address?
    
    Mac addresses of sender and receiver are assigned to data packets. To form a frame. Frame is a data unit of a data link layer.
    
    Mac address? 12 digit alpha numeric layer of the network interface of the computer. 
    
    Its not loke computers have only one mac address. Computers Bluetooth may have different Mac , WIFI has different Mac.
    
    ### Functions of data link layer
    
    1. Accesses and then adds Mac addresses to a frame.
    2. Controls how these data are placed, received from the media k.a. media access control. (basically transports)
    
    ### 7) Physical layer
    
    Contains hardware, basically wires, cables.
    It transmits the bits in the from of electric, optical or radio signals.
    
    **Order of execution.**
  You> presentation layer > session layer > transport layer > packets > Network layer >data link layer> physical layer > physical layer Friend > data link> network> packets> transport > session> presentation> friend.

---

### TCP / IP Model

- This is more practical  also known as internet protocol suite
    1. Application
    2. Transport
    3. Network
    4. Data link
    5. Physical 

### Application layer

- Users interact with this through application
E.g. WhatsApp
- Where does it lie? On your device
- Application layer has some protocols.
- How applications are connected from end systems?
Client Server Architecture & P2P
    
    ### 1. Client Server Architecture
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/846e3a4a-63b0-4ea9-b96f-69f308e042dc/Untitled.png)
    
    **Ping :** It measures the round trip time for messages from the originating host to the destination of the computer that are echoed back, this entire time is called ping time.
    
    ### **2. P2P**
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/40841e94-9067-4883-977b-5406427d5ca8/Untitled.png)
    
    - P2P stands for Peer to Peer
    - Applications that are running on various devices they get connected with each other.
    - Every computer system acts as a client as well as server.
    e.g. BitTorrent (covered later where seeding occurs.
    
    ### 3. Hybrid systems
    
    There are systems which have both client and server as well as P2P running.
    

### Network Devices

1. **Repeater:** 
    - Operates at physical layer
    - Its job is to regenerate the signal before the signal becomes too weak or corrupted so that it can be transmitted over the same network
    - Doesn’t amplify the signal.
    When the signal becomes weak they copy the signal bit by bit and regenerate it at the original strength.
    - Its a 2 port device.
        
        
        Hub : Its a multi port repeater .
        (*it is a repeater, which regenerates the signal over the same network before it becomes too weak.)*
        It connects multiple wires coming from different branches, for e.g. in star topology.
        They cannot filter the data so data packets are sent to all connected devices.
        They *are dumb,* don’t have the intelligence to find out best path for data packets.
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/f45583af-fcdf-4a54-9ef1-cc4db8de0bab/Untitled.png)
        
    
2. **Bridge:**
    - Operates at data link layer
    - Its a type of repeater with additional functionality which can filter out content by reading MAC addresses of source and destination.
    - Used for interconnecting two LANs working on same protocol.
    - It has single i/p and single o/p thus making it a 2 port device
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/c0082047-8c98-435b-8f25-53046b9f1a8a/Untitled.png)
    
    Switch - is a multi port bridge which can boost the performance and efficiency.
    It can perform error checking before forwarding the data, which makes it very efficient.
    
3. **Routers :**
- Is a device like switch that **routes data packets** based on their IP addresses.
- Operates on Network Layer.
- Mainly connects LAN’s & WAN’s together .

1. Gateways:
- Passage to connect two networking models that may work on different networking models.
- Work as messaging agent.
- Also know as protocol converters and can operate at any network layer.

1. Brouter 
- Its a bridge and a router
- 
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/198e3108-46d7-4dcf-8eaf-85774f135f2d/Untitled.png)
    

---

## Protocols

*We are in application layer. protocol can be like TCP / IP protocol or HTTP protocol when web browsing*

- Web Protocols
    1. TCP / IP 
        1. HTTP : How data is transferred in web
        HTTPS: Hyper Text Transfer Protocol Secure , handles data that is encoded , there are standards of encoding.
        2. DHCP : Dynamic Host Control Protocol , Allocates the IPs devices that are connected to the network
        3. FTP : File Transfer Protocol 
        4. SMTP : Simple Mail Transfer Protocol , used to send the emails to receive the emails we have ..
        5. PoP3 & IMAC
        6. SSH : **Secure Shell,** if one wants to access the terminal of another computer
        7. VNC : Virtual Network Computer, Sharing Desktops
        
    2. Telnet 
    - It is a terminal emulation, that enables the user to connect to a remote host or a device using Telnet client.
    - Port 23
    - It enables users to manage a account or a device remotely.
    - Not encoded or encrypted.
    
    1. UDP (User Datagram Protocol)
    - Stateless connectionless session ,data maybe lost in the life time of the connection.
    - IS used in video calls
    
    ---
    
    Process : It does multiple job, and has multi functionality. A process can have multiple threads working simultaneously.
                   Thread : It does one job. One functionality
    e.g.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/adf64361-13bc-4d98-ad95-f3b867781833/Untitled.png)
    
    Sockets are Interfaces between process and the internet.
    IPs: Tells us which device we are working with.
    
    Ports : Ports tells us which application we are working with.
    
    ---
    
    Lets say we have many chrome windows open . The data that is request is coming from my friend knows it has to go to Google Chrome but which instance of google chrome ? Which process of chrome ?(Which tab?)
    
    We have
    
    ### Ephemeral ports
    
    Lets say we have port 18 reserved for HTTP. Application will assign random port numbers. Once the process is done it will be free.
    
    ---
    
    ### HTTP
    
    - It is a client server protocol which tells us how to receive and send data from the server and how the server will send back it.
    - Application layer protocol
    - HTTP uses TCP inside it.
    - HTTP is stateless protocol , it won’t store any data.
    To store data temporarily it uses **coolies**
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/bd5458f6-4c99-4581-8b15-f16506a7310a/Untitled.png)
        
    
    <aside>
    💡 When we get a response from a web pages we get text, images, doc, videos, objects .. etc all of them have their specific URL that is why its known as world wide web. (1:55:00)
    
    </aside>
    
    ### HTTP Methods
    
    1. GET : We are requesting something.
    2. POST : I’m giving something to the server.
    3. PUT : Puts data at a specific location.
    4. DELETE : If we want to delete.
    
    - Status Codes
        1. 1XX → Informational 
        2. 2XX → Success
        3. 3XX → Redirecting
        4. 4XX → Client error
        5. 5XX → Server error
        
- **Cookies**
*When we close the browser, sometimes the session is not closed completely, e.g. items are still in the cart. You’re still logged in you’re account.*
It is a unique string. 
Stored in the browser.
When we visit the website for the first time it will set a cookie. After which when we make a new request in that request’s header cookie will be sent.
Server will get the cookie then it will know that a person has sent me a request and it will get and send back the left out state.
    - Sometimes can be misused
    
    **Third party cookies**
    
    Cookies that are set for the URLs that you don’t visit. 
    e.g. Some website use 3rd party cookies for misguiding to some other websites.
    //Better to block them
    

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/d96d8cff-b911-4bec-9909-6981678b978d/Untitled.png)

---

### How email works?

1. STMP : Simple mail transfer protocol.
For sending a mail.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/7e6e32f0-07b6-4341-9a8e-86a3d100c8cf/Untitled.png)

If both are using same client e.g. Gmail This connection establishment will not happen will be directly sent.

To find the name server IP’s of these servers
`nslookup -type=mx gmail.com`

1. PoP3 : Post Office Protocol version 3
To receive a mail

How to download email?

Client connects to the POP server which is port 110 >> username and password > then you transact all your emails.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/c486e05e-20ed-45b7-86d2-59b0615ebacb/Untitled.png)

1. IMAP Internet Message Access Protocol
It allows to view your emails on multiple platforms. 

### Domain Name System (DNS)

- DNS are mapped to IP address.
- Its like a Databases (phonebook) of URL’s
- When we enter [google.com](http://google.com) it will use DNS to find the IP address of google.
- *When URL is typed HTTP will take that URL tries to find its IP address then it will connect to the server.*
- e.g. [mail.google.com](http://mail.google.com) 
where in mail is sub domain , 
google is second level domain, 
com is top level domain.
    - Root DNS like :  .io .org .com are Top Level Domain
    - Second level Domains are [student.io](http://student.io) , [ind.org](http://ind.org) , [google.com](http://google.com)
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/cf5c8a3d-67a4-4c29-b857-b923627a3200/Untitled.png)
        
        <aside>
        💡 To check out who is maintaining root DNS servers [root-servers.org](http://root-servers.org)
        
        </aside>
        
    
    .com for commercial organizations 
    .edu for educational 
    .org for corporate 
    .uk for country specific 
    
    When we type any URL the computer checks for cache memory then Internet service provider then root server then top level domain then IP address to ISP then connection is established
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/828601e6-0da8-4a2f-ab04-719e8f33680e/Untitled.png)
    
    ---
    

## Transport Layer

*(The transportation of part from one computer to another computer is done by network layer, Transport layer lies inside the devices)*

- The role of transport layer is to take the information that your friend is sending from the network layer to the application.
- It provides abstraction.
- Transport layers has protocols TCP and UDP.

*imagine you’re mailing your friend , sending a file on Whatsapp and video calling how our computers will determine these 3 types of data bundle to be sent to the network and how will our friends computer will determine which application to send these data to.*

**Multiplexing & Demultiplexing** 

Multiplexing will allow us to send all these data to a lot of destinations just via one medium.

Demultiplex is opposite.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/a9fd4baf-0a60-48bb-a455-1e77149d5177/Untitled.png)

The data is sent to sockets and these sockets have port numbers

Data travels in packets → Transport layer will attach these sockets port numbers.

Transport layer also takes care of congestion (traffic) control . 

- There are congestion control algorithms
    - congestion control algorithms built in TCP
- **Checksums :**  When sending data to your friend, a string value is calculated based on the data to be transmitted, and a checksum is appended to the data. Upon receiving the data, the checksum is recalculated using the same algorithm, and if it differs from the original checksum, it indicates potential data loss during transportation.
- Re Transmission Timers:
Case 1: When the data packet 1 is sent the timer is started. When the receiver  confirms that he got it the timer stops. Lets say packet 2 is gets lost on the way, the in that case timer was started but hasn’t stopped eventually it will expire sender will know packet 2 was lost on its way.

Case 2: When the data packet 1 is sent the timer is started. When the receiver  confirms that he got it the timer stops. Packet 2 is sent the confirmation message is lost on its way back, in that case timer was started but hasn’t stopped eventually it will expire sender will know packet 2 was lost on its way and sender will resend packet 2 again .
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/91348f6b-bdb5-4dd5-93aa-beb1e20605d1/Untitled.png)
    
    This problem is solved using **sequence number.** 
    It is a unique identification number that is associated with every packet that is sent by the sender. So that the receiver can identify the duplicacy of the data.
    **** 
     
    

---

### User Datagram Protocol (UDP)

- Its a transport level protocol
- Here data may or may not be deliver, data may change, data may not be in order.
- It is a connectionless protocol, No connection will be established between the computer but still the data will be sent. *(TCP makes sure the connection is established before anything else)*
- UDP uses checksums.
- **UDP Packet:** Consists of
    - Headers (8bytes) : Source Port No. (2 bytes) ,Destination port no. (2), length of datagram (2), Checksums(2)
    - Data which will be = 2^16-8 =  **65528 bytes**
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/62e3c29c-2c66-40e9-a99f-ca729d492e45/Untitled.png)
        
    - UDP is faster.
    - Video conferencing , Gaming , DNS uses UDP because its fast.
    
    <aside>
    💡 To check all data packets coming in and out of our computer
    `sudo tcpdump -c 5`
    
    </aside>
    
    ---
    

### Transmission Control Protocol (TCP)

- Its a transport layer.
- It takes data from transport to network from network to transport.
- Used in HTTP
- Application layer sends lot of raw data and TCP segments this data by dividing in chunks, adds headers.
- It may also collect the data from network layer , network layer may divide that data into more smaller chunks
- Also helps with congestion control
    - It takes care of when data not arrive.
    - maintains the order of the data using sequence number
- E.g. Email
- Features
    - Connection oriented
    - Error control
    - Congestion control
    - Full Duplex, By directional 
    One can send data other receives it or both can send data at the same time.
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/7ca2b234-2b6f-43da-87e3-ae1e61a044fd/Untitled.png)
        

How connection happens?

Its known as 3 way handshake,
*(Hey i wanna establish a connection with you , responds with: I wanna do it too !! , shakes hands)*

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/40d5e96f-0935-463c-9ef6-daaf8076e047/Untitled.png)

1. A flag is sent called synchronizing flag sent to establish connection.
It is assigned with sequence number which is randomly generated for security purposes so that not anyone can guess it and tamper with it.
2. Synchronizing Acknowledgement flag is received with a sequence number ( SN: other than what is sent, which is obtained by doing some math on synchronizing flags SN ) and Acknowledgement number will be sent which is current SN +1
3. Acceptance Acknowledgement flag will be sent , sequence number (Synchronizing flag SN +1 ), acknowledgement number .

---

> **Type of data that is dealt with in every layer**
> 
> 
> ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/19b66476-5108-436c-ab94-564d2e5dc823/Untitled.png)
> 

---

## Network Layer

- Here we work with routers
- Many routers are connected to each other.
Every routers will have their own network address.
- Segments are divided into packets
- A packet contains network address of the source and destination, data.
    1. Routing table contains: Address of all the forwarding table.
    2. Forwarding table: consists information about which next router to send the data to? Will contain information only about the next route. 
    This forwarding process is known as **Hop by Hop forwarding.**
    
    Routing hopping happens not with our modems (broadbands) but with network of Internet service providers.
    *****Hoping routers to routers until reaches the destinations*
    

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/fbf9ccad-5ac4-4cb3-bd7b-06fe89f20422/Untitled.png)

- **IP Address**
e.g. 192 . 168 . 2 . 30
    
                   Where →  Network address/ **Subnet ID** (192 . 168 . 2) 
                                    Device address / **Host ID**  (. 30)
    

- Control Plane : 
Routes → nodes
Links → edges
- There are 2 types of routing that is used to creating table
    1. Static Routing: Adding addresses manually, not adaptable
    2. Dynamic : This evolve , uses path finding algorithm e.g. Bellman-Ford algorithm,  Dijkstra
    
    (the entire Internet is built on it)
    
- Network layers are IP hosts

### Internet Protocol (IP)

- IP address : It uniquely defines a server, client a node or a route.
- IPv4 → 32bit numbers , 4 - words
- IPv6 → (Future) 128 bits.
- e.g. 5.6.9.14 (convert every number to binary to get 32bit IP address).
- Whenever a router forwards a packet it should know the subnet of the destination.

**IP Address**
e.g. 192 . 168 . 2 . 30 

               Where →  Network address/ **Subnet ID** (192 . 168 . 2) 
                                Device address / **Host ID**  (. 30)

### Internet Society created Classes of ID addresses:

| Class | From | To |
| --- | --- | --- |
| A | 0.0.0.0 | 127.255.255.255 |
| B | 128.0.0.0 | 191.255.255.255 |
| C | 192.0.0.0 | 223.255.255.255 |
| D | 224.0.0.0 | 239.255.255.255 |
| E | 240.0.0.0 | 255.255.255.255 |

### Subnet masking

Subnet masking is **the process of dividing an IP address into network and host portions using a 32-bit number**. The network portion identifies the network, while the host portion identifies a specific device on that network. 
DOUBTTTTT

---

### Packets

- Headers is of 20 bytes.
- IP, length , Identification number, flags, protocols, checksum, address, TTL (time to live) etc.
    - Basically you know that the packets are travelling its hoping from various routes, sometimes a packet maybe in a loop and will not reach after so many hops , that is what TTL.

---

### IPv6

- 2^(32*4) = 2^128 = 3.4 X 10^38
- It is not a backwards compatible
- ISP would have to shift lot of hardware work
- 8 numbers , every number is a hexadecimal digit represents 16 bit parts of the addresses hexadecimal
- e.g.   a:a:a:a:a:a:a:a , a is hexadecimal (16 bit string)
ABEF:FOO1:3210:9182:0:0:1:3

### IPv4

- 2^32 = around 4.2 billion

### Middlebox

1. Firewall 
Filter out IP packets based on various rules
    1. Global Internet
    2. Your trusted network
    
    Blocking IP packets coming from certain 
    Addresses
    Modify packets
    Port Nos
    Flags
    Protocols
    
    **Stateless v/s Stateful Firewall** 
    
    - Stateless wont maintain state
    - Stateful more efficient , Stores its unique cache memory
2. Network Address Translation NAT 
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/9cfd92d7-3a7c-49ad-a094-7c14cf6f9140/552b1b76-e9b3-4bd7-ac13-e3b872542371/Untitled.png)
    
    This is done to slow down the consumption of IP addresses
    

---

## Data Link Layer

- The packets that we receive from network layer data link layer is responsible to send these packets over physical layer
-
