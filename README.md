# TradeCalc

[TradeCalc](https://hsabzehmeidani.github.io/trade-calc/) - Risk & Position Manager

---

### Trading Calculator Formulas – Real Trader Logic

Below are all the important formulas used in the calculator, presented in the logical order of a real trade (from market analysis to final calculations).

---

#### Stage 1: Entry Point & Stop Loss (Technical Analysis)

```python
Stop Loss (%) = |Entry Price - Stop Loss Price| / Entry Price × 100
```

**Explanation**:  
First, determine your **Entry Price** and **Stop Loss Price** based on market structure, price action, key levels, and risk management. Then calculate the percentage distance between your entry and stop loss.  

> **Pro Tip**: Professional traders typically only enter trades where the stop loss is between **0.5% and 2%** (1.5% in your example).

---

#### Stage 2: Position Sizing

```python
Position Size = (Capital × Risk% per Trade) / (Stop Loss% + Fee%)
```

**Explanation**:  
After calculating the stop loss percentage, this formula determines the **dollar value** of the position you should take. It ensures that if the stop loss is hit, you lose exactly the risk percentage you predefined (e.g., 1% of your total capital).

---

#### Stage 3: Required Margin

```python
Margin Required = Position Size / Leverage
```

**Explanation**:  
Calculates the actual amount of money that will be locked (margin) from your account, based on the chosen leverage. Higher leverage = lower margin required.

---

#### Stage 4: Risk per Trade (R Value)

```python
R (Risk per Trade in $) = Position Size × (Stop Loss% / 100)
```

**Explanation**:  
**R** represents the dollar amount you risk on a single trade if the stop loss is triggered. This is the fundamental unit of risk in professional money management.

---

#### Stage 5: Expected Average Profit per Winning Trade

Assuming you close **50% of the position at 1R** and **50% at 2R**:

```python
Average Profit per Win = R × 1.5
```

**Explanation**:  
- 50% of the position is closed at **1R** profit  
- 50% of the position is closed at **2R** profit  
→ Average profit per winning trade = **1.5R**

---

#### Stage 6: Average Loss per Losing Trade

```python
Average Loss per Loss = -R
```

**Explanation**:  
In the worst-case scenario, the full stop loss is hit, resulting in a loss of exactly **1R**.

---

#### Stage 7: Monthly Target

```python
Monthly Target ($) = Initial Capital × (Monthly Profit Goal / 100)
```

**Explanation**:  
Example: With $2,000 capital and a 10% monthly goal, your target is **$200** per month.

---

#### Stage 8: Number of Trades Needed to Reach Monthly Target

**Best Case (100% Win Rate)**

```python
Trades Needed (Best Case) = ceil(Monthly Target / Average Profit per Win)
```

**Realistic Case (with different Win Rates)**

```python
Expected Profit per Trade = (Win Rate × Avg Profit) + ((1 - Win Rate) × Avg Loss)

Trades Needed = ceil(Monthly Target / Expected Profit per Trade)
```
