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
