This guide explains how to convert MetaTrader 4 (MQL4) indicators into Pine Script for TradingView.  
It’s designed to help developers, traders, and coders transition custom MT4 indicators into the modern TradingView ecosystem.

---

## 🧩 Step-by-Step Conversion Guide

### 1. Understand the Indicator Logic

Before you start converting:
- Read the MQ4 code and identify:
  - **Inputs** (`input int`, `input double`)
  - **Main logic** (indicator calculations)
  - **Plotting/Buffer use**
- Note whether it uses:
  - Built-in functions like `iMA`, `iATR`, `iRSI`
  - Or custom math

---

### 2. Match MQ4 to Pine Script

| MQL4                          | Pine Script (v5)                |
|-------------------------------|----------------------------------|
| `input int`, `input double`   | `input.int`, `input.float`       |
| `OnInit()`                    | Initialization in `indicator()` |
| `OnCalculate()`               | Executes automatically           |
| `SetIndexBuffer()`            | Use `plot()` directly            |
| `DRAW_LINE`, `DRAW_HISTOGRAM` | `plot.style_line`, `plot.style_histogram` |
| `MathAbs`, `MathMax`          | `math.abs`, `math.max`           |
| `close[i]`, `high[i]`         | `close[i]`, `high[i]`            |

---

### 3. Convert Inputs

**MQ4:**
```mq4
input int period = 14;
input double multiplier = 2.0;
```

**Pine Script:**
```pinescript
period = input.int(14, title="Period")
multiplier = input.float(2.0, title="Multiplier")
```

---

### 4. Rewrite the Logic

- Replace custom loops with Pine’s `ta.*` functions if possible (`ta.sma`, `ta.atr`, etc.)
- If needed, use `array.*` and `var` with manual control
- Pine is forward-indexed (`[1]` means previous bar)

---

### 5. Plot the Result

**MQ4:**
```mq4
SetIndexBuffer(0, buffer);
SetIndexStyle(0, DRAW_LINE);
```

**Pine Script:**
```pinescript
plot(myLine, title="My Indicator", color=color.green, linewidth=2)
```

---

## 💡 Notes & Tips

- Pine doesn’t support loops across historical bars like MQL4 — use arrays or built-ins
- Pine code is real-time bar-based, not tick-based
- Some people use **ChatGPT 🤖** (like this repo 😉) for fast conversions
- Online converters are **unreliable** or very limited

---

## 📥 Want Help?

If you have a `.mq4` file you'd like converted:
- Create an issue
- Or fork the repo and submit a Pull Request with your script

---

## 🛠️ License

MIT License.  
Use, share, and adapt freely. Attribution is appreciated!

