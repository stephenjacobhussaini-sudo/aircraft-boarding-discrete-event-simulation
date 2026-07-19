# Systems Engineering Evaluation of Aircraft Boarding Strategies Using Discrete-Event Simulation

## 📌 Project Overview
This project applies core systems engineering principles to critically evaluate passenger boarding strategies for single-aisle aircraft using a high-fidelity discrete-event simulation (DES) digital twin built in Witness Horizon. The turnaround sequence is highly variable and directly dictates operational efficiency, crew utilization, and airline profitability—especially for short-haul and low-cost carriers. This study models the boarding process as a complex socio-technical system intersecting human behavior, physical aircraft layout constraints, and operational policy rules.

## ⚙️ System Parameters & Stochastic Data Modeling
The digital twin was constructed under uniform operational parameters to isolate strategy efficiency:
* **Aircraft Configuration**: Single-aisle layout mirroring standard Airbus A320 or Boeing 737 dimensions, configured with 25 rows, 4 seats per row (100 total capacity), and a single forward boarding door.
* **Passenger Load**: 100% seat occupancy with on-time gate arrival and 100% compliance with carry-on luggage limits (one hand luggage item per passenger stowed in the overhead bin above their assigned row).
* **Stochastic Variable Distributions**: To reflect real-world operational variability, processing times were modeled using probability distributions derived from established airport operations literature:
  * *Boarding Pass Scanning*: Triangular distribution.
  * *Jet Bridge Transit*: Normal distribution.
  * *Cabin Aisle Walking Speed*: Uniform distribution per row.
  * *Overhead Luggage Stowage*: Lognormal distribution.
  * *Seat Interference/Clearance Delay*: Triangular distribution.

## 🔄 Boarding Strategies Evaluated
1. **Base Model (Random Boarding)**: First-come, first-served unzoned entry representing default low-cost carrier practices.
2. **Strategy 1 (Front-to-Back)**: Sequential row boarding starting from the front cabin down to the rear to control aisle overtaking behaviors.
3. **Strategy 2 (Back-to-Front)**: Reversing the sequence to minimize passengers pushing past already-seated individuals.
4. **Strategy 3 (Window-to-Aisle)**: An outside-in sequence based entirely on seat position rather than row order.
5. **Strategy 4 (Hybrid Rear-to-Front Zoned)**: Divides the cabin into five-row blocks, applying an outside-in boarding sequence within each zone to balance aisle clearance and minimize seat interference.

## 📊 Key Performance Indicators & Simulation Results
The primary operational KPI is total boarding time, supplemented by qualitative flow stability and aisle congestion analysis.

| Boarding Strategy | Total Boarding Time (s) | Relative Operational Performance |
| :--- | :--- | :--- |
| **Random Boarding (Base Baseline)** | 1209 | Benchmark standard |
| **Front-to-Back Boarding** | 1187 | ≈1.8% marginal improvement |
| **Back-to-Front Boarding** | 1145 | Moderate optimization |
| **Window-Aisle (WA) Boarding** | 1108 | High optimization (requires strict compliance) |
| **Hybrid Zoned Strategy** | **1085** | **Best overall performance (Recommended)** |

## 💡 Commercial & Operational Implications
* **Health & Safety**: The recommended Hybrid Zoned strategy minimizes aisle congestion, lowering the risk of slips, trips, and manual handling injuries for passengers and crew.
* **Sustainability & Emissions**: Accelerating boarding directly reduces the operational runtime of the aircraft's Auxiliary Power Unit (APU) at the gate, lowering localized airport carbon emissions.
* **Commercial Profitability**: Minimizing turnaround time variation enables higher daily aircraft utilization rates and prevents expensive network delay propagation.
