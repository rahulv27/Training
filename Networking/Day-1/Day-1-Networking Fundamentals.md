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

---

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

### **TCP Flags**

![Networking Diagram](./Images/TCP_flags.png)

### **MAC, IP, ARP Basics**

---

### **TCP vs UDP**
**Use cases — SSH vs DNS vs HTTP**

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