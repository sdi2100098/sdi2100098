# Hi there, I'm Pántios 👋

I'm a Computer Science student at the **University of Athens (NKUA / DI UoA)**, passionate about systems programming, algorithms, and low-level software. My work spans from operating-systems internals and database storage engines to AI-driven games and performance-oriented CLI tooling — all built in C and C++.

---

## 🗂️ My Projects

### 🔍 [Project — Approximate Nearest Neighbor Search (Vamana)](https://github.com/sdi2100098/Project)
> **C++** · University group project (3 contributors)

Implements a full pipeline for **Approximate Nearest Neighbor (ANN) search** on graph-based indices. The core is a family of Vamana algorithms with support for filtered queries:

- **GreedySearch**, **RobustPrune**, **Vamana** — baseline graph-index construction and search
- **FilteredGreedySearch**, **FilteredRobustPrune**, **FilteredVamana** — extend the above with categorical/attribute filters
- **StitchedVamana** — multi-filter graph construction via stitching
- Binary file pre-computation of distances, ground-truth KNN, and graph snapshots for fast reruns
- Recall/accuracy evaluation against ground-truth datasets
- Unit tests, valgrind memory checks, and GitHub Actions CI
- Configurable via a config file; parametrised by L, R, α and filter sets

---

### 🖥️ [Virtual-Memory-Simulator](https://github.com/sdi2100098/Virtual-Memory-Simulator)
> **C** · Systems programming

A multi-process **virtual memory simulator** implementing a **Flush-When-Full (FWF)** page-replacement policy with hashed page tables:

- Two child processes stream memory references from real-world trace files (`bzip.trace`, `gcc.trace`)
- A parent memory manager receives references in rounds and applies the FWF policy
- Each process has its own **hashed page table** with dirty-bit tracking
- Communication via **POSIX shared memory and named semaphores** (two one-slot CMD/RESP channels per child)
- Collects global statistics: total references, page faults, disk reads, disk writes
- Configurable k-threshold, total frames, and round size (`q`)
- Build, run, test, and valgrind targets via Makefile

---

### 🔤 [CLI-Word-Frequency-Counter](https://github.com/sdi2100098/CLI-Word-Frequency-Counter)
> **C++** · CLI tooling

A command-line tool that reads a text file, counts word frequencies, and outputs the top-N words:

- Strips punctuation and normalises to lowercase
- Uses `std::unordered_map` for O(1) average-case lookups (benchmarked against `std::map`)
- Prevents accidental overwrites by requiring a new output filename
- Includes unit tests, benchmarks (`Benchmark/Times.txt`), and GitHub Actions CI
- Built with a Makefile (`make help` for all targets)

---

### 🎮 [Tic-Tac-Toe-AI](https://github.com/sdi2100098/Tic-Tac-Toe-AI)
> **C** · AI / Game programming

A terminal-based Tic Tac Toe game with a **Minimax AI** opponent:

- Human vs AI, choose who goes first
- Minimax recursive search scores: AI win +10, human win -10, tie 0
- Coloured terminal output for X and O
- Clean module separation: game loop, AI engine, move placement, board rendering, winner detection
- Sanity-check script (`scripts/sanity_check.sh`) for clean rebuild and strict warning check

---

### 🗃️ [External-Merge-Sort-on-Heap-Files](https://github.com/sdi2100098/External-Merge-Sort-on-Heap-Files)
> **C** · Database internals / University assignment

Implements an **external merge sort** pipeline over heap-file records using provided BF/HP storage libraries:

- Creates and populates a heap file with random records
- Sorts records in fixed-size chunks (initial runs)
- Repeatedly performs **k-way merge passes** until a single globally sorted output remains
- Sort key: `(name, surname)`
- Correctness validated by record-count preservation and zero inversions in final output
- Deterministic output-file naming for safe reruns

---

## 🛠️ Skills & Strengths

### Programming Languages
| Language | Experience |
|---|---|
| **C** | Systems programming, OS simulation, IPC, storage engines |
| **C++** | STL, performance-critical applications, graph algorithms |

### Tools & Technologies
| Category | Tools |
|---|---|
| **Build systems** | Make |
| **Version control** | Git, GitHub |
| **CI/CD** | GitHub Actions |
| **Debugging & profiling** | Valgrind, GCC warnings, benchmarking |
| **IPC & concurrency** | POSIX shared memory, named semaphores, multi-process architecture |

### Core Concepts & Strengths
- 📐 **Algorithms & Data Structures** — Minimax, ANN graph search (Vamana family), external merge sort, hash tables, k-way merge
- 🧠 **Systems Programming** — virtual memory management, page-replacement policies, process management, IPC
- 🗄️ **Database Internals** — heap files, block-level I/O, external sorting
- ⚡ **Performance Engineering** — benchmarking, profiling, data structure trade-offs (e.g. `unordered_map` vs `map`)
- 🧪 **Software Quality** — unit testing, memory-leak detection with Valgrind, CI pipelines

---

## 📬 Contact

- **Email:** sdi2100098@di.uoa.gr
