Urban Parking Dynamic Pricing Engine
Overview
Urban parking spaces are a scarce and high-demand resource. Static pricing often leads to overcrowding or underutilization, resulting in lost revenue and increased congestion.
This project simulates a real-time, intelligent dynamic pricing engine for 14 urban parking lots using historical and streaming data. The system adjusts parking prices based on occupancy, queue length, traffic, special events, vehicle type, and competitor prices to optimize utilization and revenue.

Tech Stack
Python 3.10+

Pandas & Numpy — Data processing and modeling (no external ML libraries)

Pathway — Real-time data ingestion and stream processing

Bokeh — Real-time interactive visualizations

Google Colab — Development and execution environment
Project Architecture & Workflow
1. Data Ingestion
Data representing 14 parking lots over 73 days, with 18 timepoints per day, is streamed in real-time using Pathway.

Each record includes: location, occupancy, capacity, queue length, vehicle type, traffic, special day, and competitor prices.

2. Feature Engineering
Raw data is processed using Pandas and Numpy to extract relevant features:

Occupancy rate

Queue length

Traffic congestion level

Special event indicator

Vehicle type encoding

Proximity and competitor price analysis (for Model 3)
3. Pricing Engine
Model 1: Baseline Linear Model

Price increases linearly with occupancy.

Model 2: Demand-Based Model

Price is adjusted based on a weighted demand function of all key features.

Model 3: Competitive Model (Optional)

Incorporates competitor prices and suggests rerouting if overburdened.

All models ensure smooth, bounded price changes (0.5x–2x base price).

4. Real-Time Output
The engine emits real-time price predictions for each parking lot at every time step.

If a lot is full and cheaper alternatives are nearby, rerouting is suggested.

5. Visualization
Bokeh is used to create interactive, real-time plots:

Price trends per lot

Occupancy vs. price

Comparison with competitor prices
