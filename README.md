# Systems Engineering Evaluation of Aircraft Boarding Strategies Using Discrete-Event Simulation

## 📌 Project Overview
This project applies core systems engineering principles to critically evaluate passenger boarding strategies for single-aisle aircraft using a high-fidelity discrete-event simulation (DES) digital twin built in Witness Horizon[cite: 1]. The turnaround sequence is highly variable and directly dictates operational efficiency, crew utilization, and airline profitability—especially for short-haul and low-cost carriers[cite: 1]. This study models the boarding process as a complex socio-technical system intersecting human behavior, physical aircraft layout constraints, and operational policy rules[cite: 1].

## ⚙️ System Parameters & Stochastic Data Modeling
The digital twin was constructed under uniform operational parameters to isolate strategy efficiency[cite: 1]:
* **Aircraft Configuration**: Single-aisle layout mirroring standard Airbus A320 or Boeing 737 dimensions, configured with 25 rows, 4 seats per row (100 total capacity), and a single forward boarding door[cite: 1].
* **Passenger Load**: 100% seat occupancy with on-time gate arrival and 100% compliance with carry-on luggage limits (one hand luggage item per passenger stowed in the overhead bin above their assigned row)[cite: 1].
* **Stochastic Variable Distributions**: To reflect real-world operational variability, processing times were modeled using probability distributions derived from established airport operations literature[cite: 1]:
  * *Boarding Pass Scanning*: Triangular distribution[cite: 1].
  * *Jet Bridge Transit*: Normal distribution[cite: 1].
  * *Cabin Aisle Walking Speed*: Uniform distribution per row[cite: 1].
  * *Overhead Luggage Stowage*: Lognormal distribution[cite: 1].
  * *Seat Interference/Clearance Delay*: Triangular distribution[cite: 1].

## 🔄 Boarding Strategies Evaluated
1. **Base Model (Random Boarding)**: First-come, first-served unzoned entry representing default low-cost carrier practices[cite: 1].
2. **Strategy 1 (Front-to-Back)**: Sequential row boarding starting from the front cabin down to the rear to control aisle overtaking behaviors[cite: 1].
3. **Strategy 2 (Back-to-Front)**: Reversing the sequence to minimize passengers pushing past already-seated individuals[cite: 1].
4. **Strategy 3 (Window-to-Aisle)**: An outside-in sequence based entirely on seat position rather than row order[cite: 1].
5. **Strategy 4 (Hybrid Rear-to-Front Zoned)**: Divides the cabin into five-row blocks, applying an outside-in boarding sequence within each zone to balance aisle clearance and minimize seat interference[cite: 1].

## 📊 Key Performance Indicators & Simulation Results
The primary operational KPI is total boarding time, supplemented by qualitative flow stability and aisle congestion analysis[cite: 1].

| Boarding Strategy | Total Boarding Time (s) | Relative Operational Performance |
| :--- | :--- | :--- |
| **Random Boarding (Base Baseline)** | 1209 | Benchmark standard[cite: 1] |
| **Front-to-Back Boarding** | 1187 | ≈1.8% marginal improvement[cite: 1] |
| **Back-to-Front Boarding** | 1145 | Moderate optimization[cite: 1] |
| **Window-Aisle (WA) Boarding** | 1108 | High optimization (requires strict compliance)[cite: 1] |
| **Hybrid Zoned Strategy** | **1085** | **Best overall performance (Recommended)**[cite: 1] |

## 💡 Commercial & Operational Implications
* **Health & Safety**: The recommended Hybrid Zoned strategy minimizes aisle congestion, lowering the risk of slips, trips, and manual handling injuries for passengers and crew[cite: 1].
* **Sustainability & Emissions**: Accelerating boarding directly reduces the operational runtime of the aircraft's Auxiliary Power Unit (APU) at the gate, lowering localized airport carbon emissions[cite: 1].
* **Commercial Profitability**: Minimizing turnaround time variation enables higher daily aircraft utilization rates and prevents expensive network delay propagation[cite: 1].
