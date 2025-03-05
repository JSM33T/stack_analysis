# **Load Balancer: How It Works?**

## **What is a Load Balancer?**

A **Load Balancer** is a network component that distributes **incoming traffic** across multiple servers to:

- Prevent overload on any single server.
- Improve response times and availability.
- Ensure fault tolerance by redirecting requests if a server fails.

---

## **Step-by-Step Load Balancing Process**

### **Step 1: Handling Incoming Requests**

- Users send requests to an application or website.
- The **Load Balancer intercepts all incoming requests**.

### **Step 2: Load Balancer Algorithm**

- The Load Balancer decides which server to forward the request to using an algorithm:

| **Algorithm**  | **Description** |
|---------------|----------------|
| **Round Robin** | Requests are distributed sequentially across all available servers. |
| **Least Connections** | The server with the fewest active connections receives the request. |
| **IP Hashing** | Assigns users to specific servers based on their IP addresses for session persistence. |

### **Step 3: Routing Requests to Servers**

- The selected **server processes the request**.
- The **server sends the response back** to the Load Balancer.

### **Step 4: Sending Response to User**

- The Load Balancer **forwards the response** back to the user.

---

## **Types of Load Balancers**

1. **Application Layer (L7) Load Balancer** → Routes traffic based on **URLs, Cookies, Headers** (e.g., NGINX, AWS ALB).  
2. **Network Layer (L4) Load Balancer** → Routes traffic based on **IP & Port** (e.g., HAProxy, AWS NLB).  
3. **Global Load Balancer** → Distributes traffic **across multiple data centers** for redundancy.  

---

## **Key Benefits**

- **Prevents Server Overload** by distributing traffic.
- **Improves Response Times** with optimized routing.
- **Provides Fault Tolerance** by redirecting traffic when a server fails.
- **Supports Scalability** by adding or removing servers dynamically.

---

## **Conclusion**

Load Balancers ensure **high availability, fault tolerance, and optimal performance** by distributing traffic efficiently using smart algorithms.  
They are essential for **scalable and reliable web applications**.
