# Networking Fundamentals

## **Objective**
**Build a strong networking foundation from zero**

---

## **Topics**

### **What is Networking?**

Networking is the process of connecting two or more devices so they can communicate and share data.

![Networking Diagram](./Images/Networking.png)

---

### **LAN / WAN / VPN / Internet Concepts**

---

### **LAN (Local Area Network)**

A **LAN** is a network that connects devices within a **small, localized area** such as a home, office, or school.

It allows devices to share:
- Files
- Printers
- Internet access

Common technologies used in a LAN:
- **Ethernet**
- **Wi-Fi**

---

### **WAN (Wide Area Network)**

A **WAN** connects **multiple LANs** over **large geographical distances**, such as between cities or countries.

It enables communication between remote locations using:
- **Leased lines**
- **Satellite links**
- **Public Internet**

---

### **VPN (Virtual Private Network)**

A **VPN** creates a **secure, encrypted tunnel** over a public network (such as the internet).

It provides:
- **Privacy**
- **Security**
- **Access to restricted/private resources**

Users experience connectivity **as if they are directly connected to a private network**.

---

### **Internet**

The **Internet** is the **global network of interconnected computers and networks** that operate using the **TCP/IP protocol suite**.

It enables:
- Worldwide communication
- Information sharing
- Access to services such as:
  - Websites
  - Email
  - Cloud applications

---

### **LAN vs MAN vs WAN Comparison**

| Feature        | LAN                         | MAN                          | WAN / Internet               |
|----------------|-----------------------------|------------------------------|------------------------------|
| Area Covered   | Local (Room / Building)     | City / Metropolis            | Global (Country / World)     |
| Transmission   | Ethernet, Wi-Fi             | Fiber Optics, Microwave      | Satellite, Leased Lines      |

---

### **OSI Model**
**All layers explained with simple examples**

![Networking Diagram](./Images/OSI.png)

The Open Systems Interconnection model (**OSI model**) is a seven layer conceptual model that characterizes and standardizes the communication functions of a telecommunication or computing system.

The **physical layer**, which is the bottom layer of the OSI model, is concerned with the transmission and reception of the unstructured raw bit stream over a physical medium. It describes the electrical/optical, mechanical, and functional interfaces to the physical medium, and it carries the signals for all of the higher layers.

The **data link layer** provides error-free transfer of data frames from one node to another over the physical layer, allowing layers above it to assume virtually error-free transmission over the link.

The **network** layer controls the operation of the subnet, deciding which physical path the data should take based on network conditions, priority of service, and other factors.

The **transport layer** ensures that messages are delivered error-free, in sequence, and with no losses or duplications.

The **session layer** allows session establishment between processes running on different stations.

The **presentation layer** formats the data to be presented to the application layer. It can be viewed as the translator for the network. This layer may translate data from a format used by the application layer into a common format at the sending station, then translate the common format to a format known by the application layer at the receiving station.

The **application layer** serves as the window for users and application processes to access network services.

**Application Layer Protocols**
| Protocol | Purpose |
|--------|--------|
| HTTP / HTTPS | Web browsing |
| FTP | File transfer |
| SMTP | Send emails |
| POP3 / IMAP | Receive emails |
| DNS | Name to IP resolution |
| SSH | Secure remote access |
| Telnet | Remote access (insecure) |
| SNMP | Network monitoring |

**OSI** is like ordering food online:

	•	App → Application
	•	Formatting order → Presentation
	•	Tracking order → Session
	•	Delivery assurance → Transport
	•	Route planning → Network
	•	Delivery person identity → Data Link
	•	Road → Physical


| Layer | Name         | Simple Responsibility                  | PDU (Protocol Data Unit) |
|------:|--------------|----------------------------------------|--------------------------|
| 7     | Application  | User interaction                       | Data                     |
| 6     | Presentation | Format, encryption                     | Data                     |
| 5     | Session      | Session management                     | Data                     |
| 4     | Transport    | Reliable data delivery (TCP/UDP)       | Segment (TCP) / Datagram (UDP) |
| 3     | Network      | IP addressing & routing                | Packet                   |
| 2     | Data Link    | MAC addressing & framing               | Frame                    |
| 1     | Physical     | Transmission of bits                   | Bits                     |

Data → Segment → Packet → Frame → Bits

**PDU** is the name given to data at each OSI layer as it moves through the network stack.

### **TCP/IP Model**

![Networking Diagram](./Images/TCP:IP.png)

**Architecture and differences from OSI**


- **DoD 4 Model** stands for **Department of Defense networking model**
- Also known as the **TCP/IP Model**
- Consists of **4 layers**
- **Simpler** than the OSI model
- Used by the **Internet in real-world networking**


---

### **Protocol Headers**
1. TCP Header  
2. UDP Header  
3. IP Header  
4. Ethernet Header 
---
**TCP Header**

![Networking Diagram](./Images/WS_TCP_Header.png)

![Networking Diagram](./Images/TCP_Header_field.png)

 **Source Port(16 bits)**: The source port number(sending application).
 **Destination Port(16 bits)**:The destination port number(receiving application).

	•	Allows 65,536 ports (0–65535)
	•	Well-known ports: 0–1023
	•	Registered ports: 1024–49151
	•	Ephemeral ports: 49152–65535
    
	Client:  192.168.1.10:52344
    Server:  172.217.0.46:443 (HTTPS)

**Sequence Number(32 bits)**: Each byte of data gets a unique number, like tracking numbers on packages. Real-time example: You're downloading a 10MB video file. The sender breaks it into chunks and labels them: bytes 1-1000 (sequence 1), bytes 1001-2000 (sequence 1001), etc. If packet 5001 arrives before 3001, your computer knows to wait and reorder them correctly.

**Acknowledgment Number (32 bits)**: The acknowledgment number indicates the next byte the receiver expects to receive and confirms successful receipt of all bytes before this number.

**Data Offset(DO)**:Specifies the length of the TCP header in 32-bit words. A 4-bit field that tells the receiver where the header ends and the actual data begins.

### **TCP Flags**

### **Modern TCP headers have 9 control flags, not just 6.**

![Networking Diagram](./Images/TCP_flags.png)
Control Flags: 9 flags (URG, ACK, PSH, RST, SYN, FIN, NS, CWR, ECE)

	•	SYN – Starts a TCP connection (used in the 3-way handshake)
	•	ACK – Confirms successful receipt of data or control packets (set on almost all packets after connection setup)
	•	FIN – Gracefully closes a connection when no more data is to be sent
	•	Reset – Abruptly terminates a connection due to errors or unexpected conditions

	•	Push – Requests immediate delivery of received data to the application
	•	Urgent – Indicates the presence of urgent data (used with the Urgent Pointer)

### Example of Push and Urgent flag:

Difference between "sending data immediately" (PSH) and "interrupting the data stream" (URG).

**Push flag**:
SSH/Telnet Sessions

![Networking Diagram](./Images/push_flag.png)
![Networking Diagram](./Images/push_1.png)
When you type commands in an SSH terminal session, each keystroke is sent immediately with the PSH flag set. This prevents buffering and ensures your typing appears instantly on the remote server, making the terminal feel responsive. Without PSH, your keystrokes would wait in a buffer until enough data accumulated, causing noticeable lag in interactive sessions.

**Urgent flag**:
The most common real-world use of the URG flag is when you press Ctrl+C to interrupt a running process in an SSH or Telnet session. The interrupt signal is marked as urgent and processed immediately, even if there's data already queued in the buffer. This allows you to kill a stuck command without waiting for normal data processing.


### **Congestion Control (ECN-related)**

	•	ECE (ECN-Echo)– Signals network congestion detected via ECN
	•	CWR(Congestion Window Reduced) – Confirms that the sender has reduced its sending rate due to congestion
	•	NS (Nonce Sum) – Experimental flag used with ECN to detect misbehaving receivers (rarely used)

**Window Size**

Specifies how much data the receiver is willing to accept.  
Implements flow control to prevent buffer overflow.

**Checksum**

Used to verify the integrity of the TCP header and data.  
Protects against corruption during transmission.


**Urgent Pointer**

Indicates the end of urgent data in the TCP stream when the URG flag is set.  
Rarely used in modern applications.

**Options**
Carries additional TCP capabilities such as MSS, window scaling, and timestamps.  
Allows TCP to optimize performance.

**Padding**

Adds extra bits to ensure the TCP header length is a multiple of 4 bytes.  
Contains only zero values.

**Data**
Handed down to the TCP protocol at the Transport layer, which includes the
upper-layer headers. Contains the actual application payload being transmitted.  

---

### **UDP Header**
![Networking Diagram](./Images/udp_header.png)

## UDP Header Fields

- **Source Port**: Port number of the application on the sending host.
- **Destination Port**: Port number of the requested application on the destination host.
- **Length**: Total length of the UDP header + UDP data.
- **Checksum**: Error-checking value calculated over the UDP header and data  
  (UDP performs its own CRC, independent of lower layers).
- **Data**: Upper-layer application data (for example, DNS, Video streaming, VoIP).

### Key Note

Even though the **Frame Check Sequence (FCS)** at the Data Link layer provides CRC,  
**UDP does not trust lower layers**, so it still computes its own checksum.

---

### **IP Header**

---

### **Ethernet Header**



### **MAC, IP, ARP Basics**

---

### **TCP vs UDP**

**Use cases — SSH vs DNS vs HTTP**

**Three-way Handshake ?**

---

### **Packets, Ports, MTU**

---

## **Instructor Teaching Tip**
**Use real-world analogies**  
OSI is like a **food delivery pipeline** 🍔🚚

---

### **Hands-on Labs**
- Check IP address of the system  
- View ARP table  

---

## **Packet Capture (Intro)**
**Capture packets using `tcpdump`**