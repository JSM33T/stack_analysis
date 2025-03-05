# **Data Classification in Cassandra**  

Cassandra **distributes and manages data** using various techniques to ensure **scalability, fault tolerance, and performance**.  

---

## **1. Partitioning (Sharding) – Distributing Data Across Nodes**  

- **Partitioning splits data** so each node stores only a part of it, not the entire dataset.  
- Uses a **partition key** to determine **which node stores specific data**.  
- **Types of Partitioning:**  

  | Type | Description |
  |------|------------|
  | **Random (Hash-based)** | Uses **consistent hashing** to distribute data evenly across nodes. |
  | **Range-based** | Stores data in **ordered ranges** (not commonly used in Cassandra). |

---

## **2. Replication – Copying Data for Fault Tolerance**  

- Data is **replicated across multiple nodes** to ensure availability and prevent data loss.  
- **Replication Factor (RF)** decides how many copies exist.  
  - Example: If **RF = 3**, Cassandra keeps **3 copies** of each data piece on different nodes.  
- Helps in **handling node failures** without losing data.  

---

## **3. Consistency Levels – Controlling Data Accuracy**  

- Determines **how many copies of data must confirm a read/write operation** before it's considered successful.  
- **Types of Consistency Levels:**  

  | Consistency Level | Description |
  |------------------|-------------|
  | **ONE** | A single replica must acknowledge the request (fast but less accurate). |
  | **QUORUM** | Majority of replicas must respond (balance between speed and accuracy). |
  | **ALL** | All replicas must confirm the operation (strong consistency but slower). |

---

## **4. Data Centers & Multi-Region Strategy**  

- Large companies **distribute data across multiple data centers** for better performance and disaster recovery.  
- Ensures **low latency** by keeping data close to users.  
- Example:  
  - **Facebook stores user data in different geographic locations** to ensure fast access.  

---

## **Summary**  

| Concept | Purpose |
|---------|---------|
| **Partitioning (Sharding)** | Splits data across nodes for scalability. |
| **Replication** | Makes copies of data for fault tolerance and high availability. |
| **Consistency Levels** | Balances data accuracy vs. speed. |
| **Multi-Region Storage** | Ensures fast access and disaster recovery. |

This setup allows Cassandra to **handle massive traffic while staying fast, resilient, and highly available!** 🚀
