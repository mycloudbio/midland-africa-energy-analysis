# midland-africa-energy-analysis
Technical analysis of off-grid solar energy data

# 🌍 Midland Africa – Junior Data Analyst Technical Exercise

This project is part of a technical exercise for the Junior Analyst role at **Midland Construction & Energy Ltd.** It involved analyzing off-grid energy data using Python and presenting insights in a 3-minute walkthrough video.

---

## 🧠 Project Objective

Analyze off-grid energy system data (solar, battery, inverter, and load metrics) to generate **actionable insights** that improve performance, resilience, and efficiency.

---

## 🛠️ Tools & Libraries

- Python (Pandas, and Matplotlib for visualization)
- Jupyter Notebook
- Excel (initial exploration)

---

## 🔍 Analytical Focus Areas

1. **⚡ Peak Generation Analysis**: Solar peaks at 9am to 4pm  
2. **🔁 Load Pattern Recognition**: Spikes at 1pm to 7pm & Load power drop drastically around 6pm 
3. **🔋 Load Shaving Opportunities**: Load spikes between 6pm and 9pm, battery output is partially supporting load  
4. **🧠 System Optimization Timing**: Charger Power is highest betweenee 9am and 1pm, Battery is charging, and Load is lowest  
5. **🔋 Battery Usage & Health**: Morning Period between 12am – 6am - Battery stays nearly constant at ~72 W, indicating no active charging or discharging possibly idle
6. **👁️ Bonus Insight – Analyst’s Eye**: No Grid Failover will result to Full System Vulnerability (Entire load depends on PV generation and battery reserve).

---

## 📊 Sample Code Snippet

```python
df['Hours'] = pd.to_datetime(df['Timestamp']).dt.hour
optimized_df = df.groupby('Hours')[['charger power(W)', 'batt power(W)', 'PLoad(W)']].mean()
optimized_df.plot()

