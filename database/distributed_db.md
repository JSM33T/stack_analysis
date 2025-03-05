# **Distributed Databases in Cassandra**  

Cassandra is a **highly scalable, distributed NoSQL database** designed for handling large amounts of data across multiple nodes with **high availability** and **fault tolerance**.  

---

## **1. Key Features of Cassandra**  

| Feature                | Description |
|------------------------|-------------|
| **Peer-to-Peer Architecture** | No single point of failure; every node is equal. |
| **Horizontal Scalability** | Easily add more nodes to handle increasing traffic. |
| **High Availability** | Data remains accessible even if some nodes fail. |
| **Eventual Consistency** | Ensures data synchronization over time. |
| **Tunable Consistency** | Allows control over read/write consistency levels. |
| **Partitioning & Replication** | Distributes and copies data across multiple nodes for redundancy. |
| **Fast Writes** | Optimized for high-speed write operations with log-structured storage. |

---

## **2. How Cassandra Works (Core Concepts)**  

### **A. Data Distribution & Partitioning**  

- Uses a **partition key** to determine **which node stores the data**.  
- Data is distributed **using consistent hashing**, ensuring balanced storage across nodes.  

### **B. Replication & Fault Tolerance**  

- **Replication Factor (RF):** Determines how many copies of data exist.  
- Data is replicated across multiple nodes to ensure **high availability**.  
- Even if some nodes fail, other replicas keep the data accessible.  

### **C. Read & Write Process**  

#### **Write Flow:**  

1. Data is written to a **commit log** (for durability).  
2. Then stored in **memtables** (in-memory cache).  
3. Eventually flushed to **SSTables (disk storage)**.  
4. **Hinted Handoff:** If a node is down, writes are temporarily stored and sent when the node is back.  

#### **Read Flow:**  

1. A **coordinator node** receives the request.  
2. Reads from the **nearest available replica** based on the consistency level.  
3. **Read Repair:** If stale data is detected, it triggers a background repair.  

---

## **3. Consistency & Availability in Cassandra**  

### **A. Tunable Consistency**  

Cassandra allows adjusting consistency levels for **reads and writes** based on application needs.  

| Consistency Level | Description |
|------------------|-------------|
| **ONE** | A single replica must acknowledge the request. |
| **QUORUM** | Majority of replicas must respond. |
| **ALL** | All replicas must confirm the operation. |

### **B. CAP Theorem in Cassandra**  

- Prioritizes **Availability (A) & Partition Tolerance (P)** over **Strict Consistency (C)**.  
- Uses **Eventual Consistency**, meaning data syncs over time.  
- **Read Repair** and **Anti-Entropy** mechanisms keep replicas updated.  

---

## **4. How Cassandra Ensures Data Integrity**  

| Mechanism         | Function |
|------------------|------------|
| **Hinted Handoff** | Temporarily stores writes for unreachable nodes. |
| **Read Repair** | Fixes stale data by comparing replicas during reads. |
| **Anti-Entropy Repair** | Periodic process using **Merkle Trees** to detect and sync inconsistencies. |

---

## **5. Real-World Use Cases**  

- **Social Media (Facebook, Instagram)** → High-speed writes and global availability.  
- **Messaging Platforms (WhatsApp, Discord)** → Low-latency communication.  
- **IoT & Streaming Data** → Handles large-scale real-time data ingestion.  

---

## **Conclusion**  

Cassandra is designed for **massive-scale distributed applications**, offering **high availability, scalability, and fault tolerance**. With **tunable consistency**, it allows businesses to choose the right balance between **performance and data accuracy**.
