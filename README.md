# Swap-N-Charge VRP: Energy-Aware Routing with Opportunistic Battery Exchange


---

## 📖 1. Project Background & Overview (Start Here)

### 1.1 The "Range Anxiety" in Green Delivery

We are moving towards a future where all delivery vehicles (vans, scooters, and drones) are completely electric. However, Electric Vehicles (EVs) suffer from a major bottleneck: **Battery Capacity and Charging Time**. If a delivery van runs out of power in the middle of a route, it cannot just pump gas in 2 minutes. It has to plug in and wait for hours, destroying the delivery schedule. This creates "Range Anxiety."

### 1.2 The "Swap-N-Charge" Revolution

Instead of plugging in and waiting, what if the vehicle simply drives to an automated station, pulls out the dead battery, and swaps in a fully charged one in under 3 minutes? This is known as **Battery Swap Station (BSS)** logistics (widely used by companies like NIO or Gogoro).
However, this creates a massive mathematical headache for logistics planners: *When* and *Where* should the vehicle swap its battery? If it swaps too early, it wastes valuable battery life and time. If it waits too long, it might run out of power before reaching the next station.

### 1.3 What is "Opportunistic" Battery Exchange?

In standard routing, a vehicle goes from A to B. But in **Opportunistic Routing**, the AI acts like a smart human on a road trip. The algorithm constantly calculates the vehicle's remaining energy—which drops faster if the vehicle is carrying heavy packages or stuck in traffic. If the algorithm sees a swap station nearby and realizes the remaining battery won't survive the next 5 deliveries, it "opportunistically" modifies the route to perform a battery swap first.

### 1.4 Your Mission

In this project, you will tackle a cutting-edge variant of the Vehicle Routing Problem (VRP). You will construct an optimization system that simultaneously calculates the shortest delivery paths AND manages battery depletion logic. You will start with basic mathematical models for energy consumption, move on to writing advanced Artificial Intelligence algorithms (Metaheuristics or Reinforcement Learning) to solve massive city-scale routing puzzles, and eventually visualize these dynamic, energy-aware routes on real-world city maps.

---

## 🎯 2. Research Objectives

| Priority           | Objective                                                                                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| **Primary**  | Develop an accurate non-linear energy depletion model factoring in vehicle mass, payload weight, and travel distance.        |
| **Primary**  | Formulate the Electric Vehicle Routing Problem with Battery Swapping (EVRP-BSS) mathematically.                              |
| **Primary**  | Design and code a smart heuristic/metaheuristic algorithm to solve the routing problem within realistic computational times. |
| **Extended** | Simulate dynamic factors (e.g., stochastic traffic delays impacting battery drain) and build a real-time map visualization.  |

---

## 🗺️ 3. Project Milestones (9 Nodes)

This project is meticulously divided into three progressive phases: Fundamentals, Core Algorithm Implementation, and Advanced Optimization.

### Phase 1: Mathematical Foundations & Energy Modeling (Introduction 1/3)

*Objective: Understand EV routing literature and translate physics into code.*

- [ ] **Node 1: Literature Scoping & VRP Basics**
  - Read foundational papers on Electric VRP (EVRP) and battery swapping.
  - *Deliverable:* A brief literature review highlighting how "charging" differs mathematically from "swapping."
- [ ] **Node 2: Energy Consumption Modeling**
  - Build a Python module that accurately calculates energy drain. It must account for the fact that a truck uses more battery when fully loaded with packages than when it is empty.
  - *Deliverable:* A Python script plotting battery depletion curves based on variable payload weights.
- [ ] **Node 3: Small-Scale Exact Solver (The Baseline)**
  - Model a tiny delivery network (e.g., 1 depot, 2 swap stations, 8 customers).
  - Use exact solvers (like PuLP or Gurobi) to find the absolute perfect, energy-safe route.
  - *Deliverable:* Python code and mathematical formulation document (MILP).

### Phase 2: Algorithm Design & Reproduction (The Core Work 1/3)

*Objective: Exact math is too slow for big cities. We need smart AI approximations (Metaheuristics).*

- [ ] **Node 4: Metaheuristic Framework Construction**
  - Implement a fast algorithmic framework, such as Adaptive Large Neighborhood Search (ALNS), Genetic Algorithm (GA), or simulated annealing.
  - *Deliverable:* A working codebase that solves classic, non-battery VRP benchmark datasets.
- [ ] **Node 5: Opportunistic Swapping Logic Integration**
  - Inject the energy constraints into your algorithm. Teach the AI to penalize routes that result in a dead battery, and reward routes that efficiently use swap stations without massive detours.
  - *Deliverable:* Updated algorithm that correctly routes vehicles through BSS nodes when needed.
- [ ] **Node 6: Benchmarking & Performance Profiling**
  - Test your solver against datasets containing 50-100 customers.
  - *Deliverable:* A comparative report showing computation time vs. route optimality (cost/energy used).

### Phase 3: Innovation, Dynamics & Visualization (The Research Frontier 1/3)

*Objective: Bring the code into the real world with dynamic traffic and map plotting.*

- [ ] **Node 7: Dynamic & Stochastic Uncertainty**
  - The real world is not perfect. Introduce "traffic jams" in your simulation that randomly drain battery power while the vehicle is stationary. Update the algorithm to re-route dynamically if a battery emergency occurs.
  - *Deliverable:* Ablation study on algorithm performance under stochastic traffic environments.
- [ ] **Node 8: Real-World Map Visualization**
  - Use mapping libraries (like `Folium` or `OSMnx`) to project your generated routes onto a real city map (e.g., Downtown New York or London).
  - Visually differentiate standard travel paths, low-battery warning paths, and battery-swap detours.
- [ ] **Node 9: Final Analysis & Poster Preparation**
  - Consolidate all metrics (Total distance, Total energy consumed, Number of swaps required).
  - *Deliverable:* Design and submit the academic poster summarizing your routing engine for the FURP Showcase.

---

## 🎓 4. Evaluation & Certificate Requirements

To successfully complete this FURP project and receive the official participation certificate, students **must** meet the following criteria:

1. **Milestone Completion**: Successfully complete, code, and document at least **50% of the project milestones (5 out of 9 Nodes)**.
2. **Poster Submission**: Submit a formal academic poster summarizing your optimization algorithm and energy models to the annual **FURP Showcase event**.
3. **Repository Standard**: All evaluations are strictly based on this GitHub repository. Ensure your Python scripts, solvers, and simulation maps are thoroughly documented.

---

## 🗂️ 5. Repository Structure Requirements

Create a repository named `FirstnameLastname-SwapVRP` within the designated GitHub Organization:

```text
FirstnameLastname-SwapVRP/
├── README.md                    # Project introduction 
├── docs/                        # Literature reviews, mathematical formulations
├── logs/                        # Weekly work logs (e.g., logs/2026-03-10.md)
├── src/                         # Python solvers, energy calculation modules
├── data/                        # Benchmark VRP datasets, simulated urban networks
├── assets/                      # Folium map HTML files, algorithm convergence plots
└── poster/                      # Final FURP Showcase poster (PDF + Source)
```
