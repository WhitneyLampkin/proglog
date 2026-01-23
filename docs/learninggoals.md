# Learning Goals
_Summarized using Microsoft Copilot_

This repository follows the **Proglog** tutorial from *Distributed Services with Go* by Travis Jeffery. The project incrementally builds a **production‑grade distributed commit log** while introducing foundational distributed systems concepts.

---

## 1. Commit Log as the Core Abstraction

At the heart of the system is a **commit log**:

- Append‑only sequence of records  
- Each record is addressed by a monotonically increasing **offset**  
- Consumers read independently without impacting writers  

This abstraction simplifies replication, scalability, and recovery, and mirrors systems such as Kafka.

---

## 2. API Design: HTTP → gRPC

The service evolves from a basic **JSON/HTTP API** to **gRPC with Protobuf**:

- Strongly‑typed contracts  
- Backward‑compatible APIs  
- Efficient, binary communication  

Protobuf definitions act as the **single source of truth** for both servers and clients.

---

## 3. Custom Storage Layer

Proglog implements its own storage engine:

- Segment‑based log storage  
- Index files for fast offset lookups  
- Clear separation between in‑memory state and on‑disk persistence  

This demonstrates how storage design directly affects performance and recovery.

---

## 4. Concurrency and Safety in Go

Concurrency is a first‑class concern:

- Mutexes protect shared state  
- Goroutines handle concurrent work  
- Ordering guarantees preserve correctness  

The project emphasizes designing for correctness under concurrent access.

---

## 5. Security with Mutual TLS

The service is secured using **mTLS**:

- Every client and server authenticates each other  
- Certificates define trust boundaries  
- All communication is encrypted by default  

This mirrors production service‑to‑service security patterns.

---

## 6. Observability by Design

Proglog is instrumented for observability from the start:

- Structured logging  
- Metrics (counters, gauges, histograms)  
- Awareness of the **Four Golden Signals**: latency, traffic, errors, saturation  

Observability is treated as a core feature, not an afterthought.

---

## 7. Service Discovery and Client Load Balancing

Instead of fixed addresses:

- Servers register themselves dynamically  
- Clients discover available replicas  
- Client‑side load balancing distributes traffic  

This avoids central bottlenecks and improves fault tolerance.

---

## 8. Consensus with Raft

To support replication and consistency, Proglog integrates **Raft**:

- Leader election  
- Log replication  
- Safety under node failures and network partitions  

Raft ensures all replicas maintain a consistent view of the log.

---

## 9. Failure as a Design Input

Failures are assumed and designed for:

- Nodes crash  
- Networks partition  
- Clients retry  

The system is built to detect, surface, and recover from failures predictably.

---

## 10. Incremental Evolution to Production Readiness

A core theme of the book is **incremental system evolution**:

- Start simple  
- Introduce abstractions as needs emerge  
- Add security, observability, and consensus over time  

This reflects how real‑world distributed systems grow and mature.

---

## Why This Matters

The Proglog tutorial is less about building a perfect log system and more about learning how to **think like a distributed systems engineer**:

- Choose durable abstractions  
- Design for failure  
- Make systems observable  
- Build with evolution in mind  

---

### Suggested Placement

This section works well as:

- `## Project Overview`
- `## Architecture Summary`
- `## Learning Goals`
``
