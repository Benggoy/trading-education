# Technical Analysis Fundamentals: RSI (Relative Strength Index)

## 📚 **Learning Objectives**
By the end of this lesson, you will understand:
- What RSI is and how it's calculated
- How to interpret RSI signals
- Common RSI trading strategies
- RSI limitations and best practices

---

## 🎯 **What is RSI?**

The **Relative Strength Index (RSI)** is a momentum oscillator that measures the speed and change of price movements. Developed by J. Welles Wilder Jr. in 1978, RSI oscillates between 0 and 100 and is primarily used to identify overbought or oversold conditions in a trading instrument.

### **Key Characteristics:**
- **Range**: 0 to 100
- **Default Period**: 14 periods
- **Type**: Momentum oscillator
- **Primary Use**: Identifying overbought/oversold conditions

---

## 🧮 **RSI Calculation**

### **Formula:**
```
RSI = 100 - (100 / (1 + RS))
where RS = Average Gain / Average Loss
```

### **Step-by-Step Calculation:**
1. **Calculate price changes** for each period
2. **Separate gains and losses**
3. **Calculate average gain and average loss** (typically using 14 periods)
4. **Calculate RS** (Relative Strength) = Average Gain ÷ Average Loss
5. **Apply RSI formula**

### **Example Calculation:**
```python
# Simplified example with 5-day data
prices = [100, 102, 101, 103, 105]
changes = [2, -1, 2, 2]  # Day-to-day changes

gains = [2, 0, 2, 2]     # Positive changes only
losses = [0, 1, 0, 0]    # Negative changes (absolute)

avg_gain = sum(gains) / 4 = 1.5
avg_loss = sum(losses) / 4 = 0.25

RS = 1.5 / 0.25 = 6
RSI = 100 - (100 / (1 + 6)) = 85.71
```

---

## 📊 **RSI Interpretation**

### **Traditional RSI Levels:**

| RSI Range | Market Condition | Typical Action |
|-----------|------------------|----------------|
| **70-100** | Overbought | Consider selling |
| **50-70** | Bullish momentum | Hold/buy on dips |
| **30-50** | Bearish momentum | Caution |
| **0-30** | Oversold | Consider buying |

### **Visual Interpretation:**
```
RSI Scale:
100 ├─── Extremely Overbought
 80 ├─── Overbought Zone
 70 ├─── Overbought Threshold ⚠️
 50 ├─── Midline (Neutral)
 30 ├─── Oversold Threshold ⚠️
 20 ├─── Oversold Zone
  0 └─── Extremely Oversold
```

---

## 🎯 **RSI Trading Strategies**

### **1. Basic Overbought/Oversold Strategy**
- **Buy Signal**: RSI < 30 (oversold)
- **Sell Signal**: RSI > 70 (overbought)
- **Best for**: Range-bound markets

```python
# Pseudo-code
if rsi < 30:
    signal = "BUY"
elif rsi > 70:
    signal = "SELL"
else:
    signal = "HOLD"
```

### **2. RSI Divergence Strategy**
**Bullish Divergence**: Price makes lower lows, but RSI makes higher lows
**Bearish Divergence**: Price makes higher highs, but RSI makes lower highs

### **3. RSI Centerline Crossover**
- **Bullish**: RSI crosses above 50
- **Bearish**: RSI crosses below 50

### **4. RSI Trend Following**
- **Strong Uptrend**: RSI stays above 40-50
- **Strong Downtrend**: RSI stays below 50-60

---

## 📈 **Practical Examples**

### **Example 1: Apple (AAPL) - Oversold Bounce**
```
Date        Price    RSI    Signal    Action
2024-01-15  $180     25     BUY       Entry at oversold
2024-01-22  $190     55     HOLD      RSI normalizing
2024-01-30  $195     75     SELL      Exit at overbought
Result: +8.3% gain
```

### **Example 2: Tesla (TSLA) - Divergence**
```
Price Trend: Higher highs ($250 → $260 → $270)
RSI Trend:   Lower highs (85 → 80 → 75)
Signal:      Bearish divergence
Action:      Consider taking profits
```

---

## ⚠️ **RSI Limitations & Best Practices**

### **Limitations:**
1. **False signals** in strong trending markets
2. **Can stay overbought/oversold** for extended periods
3. **Lagging indicator** - reacts to price movements
4. **Not effective alone** - needs confirmation

### **Best Practices:**

#### **1. Use Multiple Timeframes**
- Short-term: 5-minute, 15-minute charts
- Medium-term: Daily charts
- Long-term: Weekly charts

#### **2. Combine with Other Indicators**
```python
# Example combination
def trading_signal(rsi, macd, volume):
    if rsi < 30 and macd > 0 and volume > avg_volume:
        return "STRONG_BUY"
    elif rsi > 70 and macd < 0:
        return "STRONG_SELL"
    else:
        return "NEUTRAL"
```

#### **3. Adjust for Market Conditions**
- **Trending Markets**: Use 80/20 levels instead of 70/30
- **Volatile Markets**: Use shorter periods (7-10)
- **Stable Markets**: Use longer periods (21-25)

#### **4. Consider Market Context**
- **Bull Market**: Focus on oversold signals (RSI < 30)
- **Bear Market**: Focus on overbought signals (RSI > 70)
- **Sideways Market**: Use traditional 70/30 levels

---

## 🛠️ **Hands-On Exercise**

### **Exercise 1: Calculate RSI**
Given the following 5-day price data, calculate the RSI:
```
Day 1: $100
Day 2: $105 (+5)
Day 3: $102 (-3)
Day 4: $108 (+6)
Day 5: $104 (-4)
```

**Solution:**
```python
gains = [5, 0, 6, 0]
losses = [0, 3, 0, 4]
avg_gain = 11/4 = 2.75
avg_loss = 7/4 = 1.75
RS = 2.75/1.75 = 1.57
RSI = 100 - (100/(1+1.57)) = 61.1
```

### **Exercise 2: Identify Signals**
For each RSI value, determine the signal:
- RSI = 25: **BUY** (oversold)
- RSI = 75: **SELL** (overbought)
- RSI = 55: **HOLD** (neutral)

---

## 📚 **Further Reading & Resources**

### **Books:**
- "New Concepts in Technical Trading Systems" by J. Welles Wilder Jr.
- "Technical Analysis of the Financial Markets" by John Murphy

### **Online Resources:**
- [RSI Calculator Tool](../tools/rsi_calculator.py)
- TradingView RSI Documentation
- Investopedia RSI Guide

### **Practice Platforms:**
- TradingView (free charting)
- Yahoo Finance
- Python with yfinance library

---

## 🎓 **Key Takeaways**

1. **RSI measures momentum** - not price direction
2. **Overbought ≠ Immediate sell** signal
3. **Context matters** - trending vs. range-bound markets
4. **Combine with other indicators** for better accuracy
5. **Practice with paper trading** before real money
6. **Backtest strategies** before implementation

---

## 📝 **Quiz: Test Your Knowledge**

### **Question 1**: What does an RSI of 85 typically indicate?
a) Strong buying opportunity
b) Overbought condition
c) Neutral market
d) Oversold condition

**Answer: b) Overbought condition**

### **Question 2**: In a strong uptrend, RSI levels above __ are common:
a) 30
b) 50
c) 70
d) 80

**Answer: b) 50 (RSI tends to stay elevated in uptrends)**

### **Question 3**: Bullish divergence occurs when:
a) Price and RSI both make higher highs
b) Price makes lower lows, RSI makes higher lows
c) RSI crosses above 70
d) RSI crosses below 30

**Answer: b) Price makes lower lows, RSI makes higher lows**

---

## 🔄 **Next Steps**

1. **Practice** identifying RSI signals on historical charts
2. **Backtest** RSI strategies with your preferred stocks
3. **Combine RSI** with moving averages or MACD
4. **Explore** other momentum indicators (Stochastic, Williams %R)
5. **Implement** the RSI calculator from our tools section

---

*Happy Trading! 📈*

---

**Disclaimer**: This educational material is for informational purposes only and does not constitute financial advice. Always conduct your own research and consider your risk tolerance before making investment decisions.
