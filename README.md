# OCaml Limit Order Book

A high-performance financial matching engine written in OCaml, designed to simulate a real-time exchange environment. This project focuses on functional programming paradigms to ensure type safety and correctness in order processing.

## 🚧 Status: Under Active Development

## Core Architecture
The system is designed around a central matching engine that processes incoming orders based on price-time priority.

### Key Components
* **Order Book Module:** Uses `Map` based data structures for efficient $O(\log n)$ insertion and deletion of limit orders.
* **Matching Engine:** Recursive functional logic to traverse the book and execute trades when bid/ask spreads cross.
* **TCP Interface:** A lightweight server listening on port 9000 to accept order entry protocols (FIX-lite).

## Technical Goals
* **Zero-allocation in the hot path:** Minimizing GC pauses during the matching cycle.
* **Immutability:** Leveraging OCaml's persistent data structures to maintain state integrity.
* **Concurrency:** Using `Lwt` or `Eio` for handling asynchronous client connections.
