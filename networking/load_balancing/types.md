# OSI Model and Load Balancers

| OSI Layer         | Layer Number | Function                                  | Load Balancers Used                        |
|-------------------|-------------|-------------------------------------------|--------------------------------------------|
| **Application**   | Layer 7      | Processes network requests (HTTP, HTTPS)  | AWS ALB, NGINX, Traefik                    |
| **Presentation**  | Layer 6      | Data formatting, encryption (SSL/TLS)     | Handled by SSL Termination in L7 Load Balancers |
| **Session**       | Layer 5      | Manages sessions (Authentication, API)    | Managed at application level, not LB-specific |
| **Transport**     | Layer 4      | Manages TCP/UDP connections               | AWS NLB, HAProxy (L4 Mode)                 |
| **Network**       | Layer 3      | Routes packets (IP Addressing)            | Cisco Load Balancers, F5 BIG-IP            |
| **Data Link**     | Layer 2      | MAC addressing, switching                 | Switch-based load balancing, F5 Load Balancer |
| **Physical**      | Layer 1      | Physical hardware (Cables, Fiber, NICs)   | Not applicable to software-based load balancing |
