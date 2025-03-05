# **CAP Theorem (Consistency, Availability, Partition Tolerance)**  

The **CAP theorem** states that a **distributed database** can only guarantee **two out of three** properties at any time:  

## **1. CAP Properties**  

| Property         | Description |
|-----------------|-------------|
| **Consistency (C)** | Every read receives the latest write (all nodes have the same data). |
| **Availability (A)** | The system responds to every request (even if some nodes fail). |
| **Partition Tolerance (P)** | The system works despite network failures (nodes being disconnected). |

## **2. Trade-offs in Distributed Systems**  

A database can only provide **two** out of the three CAP properties:  

| Model  | Guarantees | Trade-off | Example Databases |
|--------|-----------|-----------|------------------|
| **CP (Consistency + Partition Tolerance)** | Ensures up-to-date data across nodes, but some requests may fail during network issues. | Sacrifices **Availability**. | MongoDB, HBase |
| **AP (Availability + Partition Tolerance)** | Ensures system stays online, but data may be **temporarily inconsistent**. | Sacrifices **Consistency**. | Cassandra, DynamoDB |
| **CA (Consistency + Availability)** | Ensures **immediate consistency and uptime**, but **cannot tolerate network failures**. | Unrealistic in distributed systems. | Not feasible in distributed DBs |

## **3. Real-World Impact**  

- **Most modern distributed databases prioritize Partition Tolerance (P)** since network failures are unavoidable.  
- Depending on business needs, they lean towards **CP (Consistency-first) or AP (Availability-first)** models.  

**Example Use Cases:**  

- **CP (Consistency-focused)** → Banking transactions (MongoDB, HBase).  
- **AP (Availability-focused)** → Large-scale, distributed apps like social media (Cassandra, DynamoDB).  

## **Conclusion**  

CAP theorem helps **architect distributed systems** by choosing the right balance between **Consistency, Availability, and Partition Tolerance** based on business needs.
