# cpp-multithreaded-chat

A high-performance, asynchronous multi-threaded chat server and client application implemented in modern C++ (C++11) utilizing the **Boost.Asio** asynchronous library.

## Key Technical Architecture & Concurrency
* **Asynchronous Event Handling:** Built entirely on `boost::asio` to handle non-blocking asynchronous operations seamlessly.
* **Thread Pool Serialization:** Utilizes `boost::asio::io_service::strand` to serialize server-side event handlers within the worker thread pool. This effectively eliminates the need for explicit locking mechanisms, preventing race conditions cleanly.
* **CPU Affinity Optimization:** Demonstrates how to set CPU affinity for worker threads on Linux environments to achieve core-level synchronization and lower latency.

## Key Features
1. **Real-time Broadcast:** Instant multi-client communication broadcasting messages dynamically to all active room participants.
2. **Structured Message Framing:** Chat messages are well-structured, containing server-side timestamps, user nicknames, and textual payloads.
3. **Session Persistence (Chat History):** Seamless onboarding for new participants by instantly feeding recent chat room history upon connection.
4. **Multi-Room Support:** Highly modular architecture capable of supporting multiple isolated chat rooms mapped to specific port numbers.
5. **Cross-Platform Readiness:** Fully tested and compliant across both **Windows** and **Linux** environments.

##  How to Build and Run

The project includes a unified `makefile` that compiles two optimized binaries: `chat_server` and `chat_client`.

### Compilation:
```bash
# Compile both server and client binaries instantly
make