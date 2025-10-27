# Bitcoin-Market-sentiment-and-trader-performance
This project Analyze how trading behavior (profitability, risk, volume, leverage) aligns or diverges from  overall market sentiment (fear vs greed). Identify hidden trends or signals that could influence  smarter trading strategies.
# 📊 Trader Performance vs Market Sentiment

## 🗂️ Datasets Used

### **1. Fear & Greed Index**

* **Columns:** `date`, `classification` (Extreme Fear → Extreme Greed), `value`
* **Purpose:** Represents the **daily market sentiment** toward Bitcoin and the broader crypto market.
* **Range:** 5 sentiment classes — *Extreme Fear, Fear, Neutral, Greed, Extreme Greed*.

### **2. Historical Trader Data**

* **Includes:** `account`, `execution_price`, `side (buy/sell)`, `size_usd`, `closed_pnl`, `timestamp`, etc.
* **Purpose:** Captures **individual trades** executed by traders across multiple days and market conditions.

---

## 🎯 Objective

To Analyze how **trading behavior** (profitability, risk, volume) aligns or diverges from 
overall **market sentiment** (fear vs greed).
Ultimately, the goal is to **uncover hidden behavioral patterns** and generate **data-driven trading insights**.

---

## 🧠 Key Steps Performed

### **1. Data Cleaning & Preprocessing**

* Standardized and merged **sentiment** and **trader data** on the `date` field
* Encoded sentiment levels numerically:
  *(Extreme Fear → 0, Fear → 1, Neutral → 2, Greed → 3, Extreme Greed → 4)*
* Filtered and retained essential trade attributes for analysis
* Converted timestamps, ensured consistent data types (`datetime64[ns]`)


### **2. Feature Engineering**
First,  ensured the date column is a proper datetime object and create a boolean column for successful trades (Closed PnL > 0).

### **3. Aggregate Daily Performance Metrics**
Aggregated the trade-level data to calculate daily performance metrics, which we can then relate to the daily sentiment.

### **4. Analyze Performance by Sentiment Classification**
This is the core analysis. Grouped the daily metrics by the classification (Fear, Greed, etc.) to see how traders perform under different market sentiments.

### **4. Analyze Trading Behavior (Direction/Side) by Sentiment**
This checks whether traders are more inclined to Buy or Sell during different sentiment states.

---

## 📈 Key Insights

| Sentiment         | Avg_Daily_PnL | Avg_Win_Rate | Avg_Trade_Size | Days_Observed |
| ----------------- | ------------- | ------------ | -------------- | ------------- |
| **Extreme Fear**  | 52,793.6      | 0.327        | 4,091.8        | 14            |
| **Fear**          | 36,891.8      | 0.329        | 6,524.29       | 91            |
| **Neutral**       | 19,297.3      | 0.332        | 7,157.53       | 67            |
| **Greed**         | 11,140.6      | 0.336        | 6,735.3        | 193           |
| **Extreme Greed** | 23,817.3      | 0.467        | 4,410.52       | 114           |

---

## 💡 Interpretation Summary

* **Performance peaks during Extreme Fear** — suggesting traders benefit from *contrarian opportunities* when the market is overly fearful.
* **Win rate rises sharply in Extreme Greed**, but overall profit drops — indicating smaller, safer trades in overbought markets.
* **Trade sizes shrink in emotional extremes** (both Fear & Greed), possibly due to cautious sentiment or lower liquidity.
* **Most trading days occur in Greed zones**, showing markets spend more time in optimism than panic.

---

## 🚀 Outcome

A structured framework linking **sentiment data** with **real trading performance**, enabling:

* Adaptive position sizing based on sentiment conditions
* Identification of profitable behavioral biases
* Enhanced decision-making through sentiment aware analytics
