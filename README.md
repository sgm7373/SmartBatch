# SmartBatch - Automated Print Queue Optimizer for Manufacturing

A Python-based batch optimization tool that simulates and optimizes print job scheduling for high-volume dental manufacturing workflows. Built to demonstrate how intelligent batching reduces machine cycles, operator intervention, and total print time at scale.

---

## The Problem

Most labs run one print job per order. No batching, no coordination. The result is a build plate that's mostly empty, machines running around the clock for no reason, and operators constantly loading and unloading jobs that could have been combined.

At 20 orders a day, that's 20 separate print jobs — each one requiring its own setup, monitoring, and post-processing cycle.

---

## The Solution

SmartBatch takes an incoming order queue, analyzes part dimensions, and packs as many parts as possible onto the build plate before scheduling a print job. It uses a 2D grid-search bin-packing algorithm with overlap detection to place parts efficiently within the physical build volume constraints.

The result: fewer jobs, less machine wear, less operator time, and dramatically better build plate utilization.

---

## Results — 20 Orders, One Day of Lab Operations

| Metric | Naive Workflow | SmartBatch | Improvement |
|---|---|---|---|
| Print Jobs Required | 20 | 5 | 75% fewer jobs |
| Total Print Time | 23.3 min | 7.8 min | 67% faster |
| Avg Build Plate Usage | 14.6% | 58.4% | 4x improvement |

**Annualized impact (250 working days):**
- 3,750 machine cycles saved per year
- 65 hours of print time saved per year
- ~75% reduction in operator interventions

---

## Visualizations

**Optimized Build Plate Layout — all 20 orders packed into 5 jobs:**

![Build Plate Layout](Build%20Plate%20Layout.png)


**Key Metrics — Naive vs Optimized:**

![Comparison Chart](Comparison%20Chart.png)

---

## How It Works

1. **Order Queue Generation** — Simulates a day's worth of incoming dental lab orders (aligners, surgical guides, dental models, night guards, retainers) with realistic dimensions and resin volumes.

2. **Naive Scheduling Baseline** — Runs each order as its own print job, one at a time. Calculates total jobs, time, cost, and plate utilization.

3. **Batch Optimizer** — Places parts onto the build plate using a grid-search algorithm. When the plate is full, it closes the job and starts a new one. Tracks placement coordinates to prevent overlap.

4. **Comparison & Reporting** — Side-by-side analysis of naive vs optimized workflows with visualizations and an annualized impact summary.

---

## Tech Stack

- Python 3
- NumPy
- Pandas
- Matplotlib

No external dependencies beyond the standard scientific Python stack. Runs entirely in Google Colab.

---

## Run It

The easiest way to run this is directly in Google Colab — no setup needed.

1. Open the notebook: `SmartBatch_Automated_Print_Queue_Optimizer_for_Manufacturing.ipynb`
2. Click **Runtime → Run All**
3. All outputs, charts, and the final report will generate automatically

---

## Project Structure

```
smartbatch/
│
├── SmartBatch_Automated_Print_Queue_Optimizer_for_Manufacturing.ipynb
├── README.md
├── build_plate_layout.png
└── comparison_chart.png
```

---

## Potential Extensions

- REST API integration with lab order management systems for live queue ingestion
- Part orientation and support structure awareness
- Dynamic re-batching when rush orders arrive mid-queue
- Fleet scheduling across multiple printers
- Live operations dashboard showing real-time queue status and utilization

---

## Author

**Sourabh Gopinath More**  
MS Computer Science
[LinkedIn](https://www.linkedin.com/in/sourabhmore73/) | [Portfolio](https://sourabhmore.carrd.co/) | [GitHub](https://github.com/sgm7373)
