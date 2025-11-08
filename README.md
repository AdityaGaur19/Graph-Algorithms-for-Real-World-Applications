````markdown
# 🌐 Graph Algorithms for Real-World Applications  

### _An analytical exploration of graph-based algorithmic strategies solving real-world problems through shortest paths, network optimization, and social graph analysis._

---

## 📘 Overview  

This project demonstrates the implementation and comparative analysis of **graph algorithms** in realistic domains such as social networking, route optimization, emergency response, and infrastructure planning.  
It was developed as part of the **Design and Analysis of Algorithms Lab (ENCA351)** under the **BCA (AI & Data Science)** program at **KR Mangalam University**.  

By applying classical graph algorithms — **BFS/DFS, Bellman-Ford, Dijkstra, and Kruskal/Prim** — the project bridges theoretical graph concepts with their real-world applications, analyzing efficiency, scalability, and performance trade-offs through profiling and visualization.  

---

## 🎯 Learning Objectives  

- Apply and compare **graph algorithms** to diverse real-world problem contexts.  
- Visualize **shortest path, connectivity, and optimization** problems.  
- Evaluate **runtime and memory usage** for each approach using performance profiling.  
- Demonstrate **how theoretical graph properties translate into real-world impact.**  

---

## ⚙️ Environment Setup  

All implementations were executed on **Google Colab (Python 3.10+)**.

### 🔧 Install Dependencies
```bash
!pip install networkx==3.3 matplotlib==3.9.2 numpy==1.26.4 pandas==2.2.2 memory_profiler==0.61.0
````

### 📦 Requirements File

`requirements.txt`

```
networkx==3.3
matplotlib==3.9.2
numpy==1.26.4
pandas==2.2.2
memory_profiler==0.61.0
heapq
time
```

---

## 📂 Project Structure

```
Graph-Algorithms-for-Real-World-Applications/
│
├── graph_algorithms_notebook.ipynb        # Main Colab notebook
├── images/                                # Generated plots
│   ├── social_graph.png
│   ├── dijkstra_graph.png
│   ├── kruskal_mst.png
│   ├── bfs_scale.png
│   ├── bellman_scale.png
│   ├── dijkstra_scale.png
│   └── mst_scale.png
├── tables/                                # CSV tables
│   ├── friend_suggestion_table.csv
│   ├── bellmanford_results.csv
│   ├── dijkstra_results.csv
│   ├── kruskal_mst.csv
│   ├── prim_mst.csv
│   ├── bfs_scale.csv
│   ├── bellman_scale.csv
│   ├── dijkstra_scale.csv
│   ├── mst_scale.csv
│   └── project_summary_graphs.csv
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 💻 Problem Implementations

### 🟩 **1. Social Network Friend Suggestion — BFS/DFS**

* **Objective:** Recommend new connections (friends-of-friends) within a social graph.
* **Algorithm Used:** Breadth-First Search (BFS).
* **Approach:** Traverse graph up to distance 2 from a given user and suggest unconnected nodes.
* **Complexity:** `O(V + E)`
* **Visualization:**

  * Plot — `social_graph.png`
  * Table — `friend_suggestion_table.csv`

---

### 🟦 **2. Route Finding (Google Maps) — Bellman-Ford Algorithm**

* **Objective:** Determine shortest paths in a weighted directed graph (supports negative edges).
* **Algorithm Used:** Bellman-Ford.
* **Approach:** Iteratively relax edges (V−1 times) to find minimum distances and detect negative cycles.
* **Complexity:** `O(V × E)`
* **Visualization:**

  * Table — `bellmanford_results.csv`
  * Plot — `bellman_scale.png`

---

### 🟨 **3. Emergency Response System — Dijkstra’s Algorithm**

* **Objective:** Compute the quickest routes from a hospital to various locations in a city.
* **Algorithm Used:** Dijkstra (min-heap optimization).
* **Approach:** Greedy selection of minimum distance nodes with priority queue for efficiency.
* **Complexity:** `O(E log V)`
* **Visualization:**

  * Graph — `dijkstra_graph.png`
  * Table — `dijkstra_results.csv`
  * Plot — `dijkstra_scale.png`

---

### 🟥 **4. Network Cable Installation — Kruskal & Prim (MST)**

* **Objective:** Connect all buildings (nodes) with minimum total cable length.
* **Algorithm Used:** Kruskal’s Algorithm (Union-Find) and Prim’s Algorithm.
* **Approach:**

  * Kruskal sorts edges and uses disjoint sets to avoid cycles.
  * Prim grows MST incrementally by choosing minimum-weight edges.
* **Complexity:** `O(E log V)`
* **Visualization:**

  * Graph — `kruskal_mst.png`
  * Tables — `kruskal_mst.csv`, `prim_mst.csv`
  * Plot — `mst_scale.png`

---

## 📊 Experimental Profiling

Each algorithm was tested for **time and memory efficiency** using randomized input graphs of increasing size.
Profiling was conducted via:

* `time.perf_counter()` for runtime.
* `memory_profiler` for peak memory.
* `matplotlib` for visualization.

### Performance Graphs

| Algorithm                     | Plot                                 | Observation                               |
| ----------------------------- | ------------------------------------ | ----------------------------------------- |
| BFS/DFS (Friend Suggestion)   | ![bfs](images/bfs_scale.png)         | Linear growth with graph size             |
| Bellman-Ford (Route Finding)  | ![bellman](images/bellman_scale.png) | Runtime increases proportionally to edges |
| Dijkstra (Emergency Response) | ![dijk](images/dijkstra_scale.png)   | Scales efficiently for sparse graphs      |
| Kruskal (MST)                 | ![mst](images/mst_scale.png)         | Slightly slower for dense networks        |

---

## 🧮 Comparative Summary

| Problem                          | Algorithm    | Time Complexity | Space Complexity | Domain         | Output Table                   |
| -------------------------------- | ------------ | --------------- | ---------------- | -------------- | ------------------------------ |
| Social Network Friend Suggestion | BFS/DFS      | O(V + E)        | O(V)             | Social Graphs  | friend_suggestion_table.csv    |
| Route Finding                    | Bellman-Ford | O(VE)           | O(V)             | Navigation     | bellmanford_results.csv        |
| Emergency Response System        | Dijkstra     | O(E log V)      | O(V)             | Transportation | dijkstra_results.csv           |
| Network Cable Installation       | Kruskal/Prim | O(E log V)      | O(V)             | Infrastructure | kruskal_mst.csv / prim_mst.csv |

---

## 🧠 Insights

* **BFS/DFS** are ideal for connection discovery in social or network graphs.
* **Bellman-Ford** supports negative weights, suitable for dynamic routing scenarios.
* **Dijkstra** performs best for real-time shortest path queries in non-negative networks.
* **Kruskal and Prim** efficiently minimize costs in physical or virtual network infrastructures.

---

## 🧰 Tools & Technologies

| Tool               | Purpose                          |
| ------------------ | -------------------------------- |
| 🐍 Python 3.10+    | Core programming language        |
| 🧮 NetworkX        | Graph modeling and visualization |
| 📊 Matplotlib      | Graph and performance plotting   |
| 🧠 Memory Profiler | Memory tracking                  |
| 📘 Pandas          | Table generation and CSV exports |
| ☁️ Google Colab    | Execution environment            |
| 💾 GitHub          | Version control & documentation  |

---

## 🧑‍💻 Author

**Aditya Gaur**
🎓 BCA (AI & Data Science), KR Mangalam University
📧 [gauraditya0905@gmail.com](mailto:gauraditya0905@gmail.com)
🔗 [LinkedIn Profile](https://www.linkedin.com/in/adityagaur19)

---

## 🧑‍🏫 Faculty Guide

**Dr. Aarti Sangwan**
Faculty, School of Engineering & Technology
KR Mangalam University

---

## 🛡️ License

This project is open-source under the **MIT License**.
You are free to use, modify, and reference it for educational and research purposes.

---

## 🌟 Acknowledgment

Grateful to **Dr. Aarti Sangwan** for her academic guidance and mentorship throughout this project.
Special thanks to the open-source Python community for powerful tools enabling algorithmic experimentation.

---

> *“Graphs are not just mathematical structures—they are blueprints of the world’s connectivity and efficiency.”* 💡

````
