### Alpha Strategy: Profitability Compared to Capitalization

#### Concept
This alpha strategy is based on the hypothesis that if the performance ratio of a company's fundamentals (profitability) is increasing relative to its size (capitalization), then the stock price is likely to increase. By using time series operators on a ratio of fundamental metrics, the strategy aims to identify stocks that are becoming more efficient in generating profit relative to their size over time.

**Key Components:**

1. **Profit Field:**
   - Represents any measure of the company's income or earnings.
   - Examples include net income, earnings per share (EPS), operating income, etc.

2. **Size Field:**
   - Represents any measure of the company's size or market presence.
   - Examples include market capitalization, total assets, enterprise value (EV), etc.

3. **Time Series Operator:**
   - A function that applies calculations over a specified period to track changes and trends.

4. **Day Parameter:**
   - The number of days over which the time series operator is applied.
   - Common periods include week (5 days), month (20 days), quarter (60 days), or year (250 days).

#### Execution

1. **Calculate the Ratio:**
   - Compute the ratio of the profit field to the size field.
   - Example: \(\text{Ratio} = \frac{\text{Net Income}}{\text{Market Capitalization}}\)

2. **Apply Time Series Operator:**
   - Use a time series operator to observe changes in this ratio over a specified period.
   - Example: Calculate the average or growth rate of this ratio over the last 60 days (quarter).

3. **Identify Stocks with Increasing Ratios:**
   - Identify stocks where the ratio is increasing compared to earlier periods, indicating improving profitability relative to size.

#### Why It Works

**Example:**

Imagine we have two companies, Company A and Company B. We will compare their profitability to their capitalization over the last quarter (60 days).

1. **Calculate the Ratio:**
   - **Company A:**
     - Net Income: $100 million
     - Market Capitalization: $1 billion
     - Ratio: \(\frac{100 \text{ million}}{1000 \text{ million}} = 0.10\)
   - **Company B:**
     - Net Income: $50 million
     - Market Capitalization: $500 million
     - Ratio: \(\frac{50 \text{ million}}{500 \text{ million}} = 0.10\)

2. **Apply Time Series Operator:**
   - Over the past 60 days, track changes in the ratio for both companies.
   - **Company A:** Ratio increased from 0.08 to 0.10.
   - **Company B:** Ratio remained constant at 0.10.

3. **Identify Stocks with Increasing Ratios:**
   - **Company A:** Shows an increasing ratio (from 0.08 to 0.10), indicating improving profitability relative to its size.
   - **Company B:** Ratio is constant, indicating no significant improvement.

4. **Decision Rule:**
   - Based on the hypothesis, **Company A** is more likely to see an increase in stock price because its profitability relative to its size is improving.

**Why It Works:**

1. **Profitability Improvement:** An increasing ratio of profitability to size suggests the company is becoming more efficient at generating earnings relative to its market value. Investors are likely to reward this improvement with higher stock prices.
2. **Fundamental Analysis:** This strategy relies on fundamental analysis, providing a more stable and long-term perspective compared to purely technical indicators.
3. **Market Efficiency:** The market tends to recognize and price in improving company fundamentals over time. By identifying these trends early, the strategy can capitalize on anticipated price increases.
4. **Relative Valuation:** Comparing profitability to size allows for a relative valuation approach, identifying stocks that may be undervalued based on their improving fundamentals.

### Summary
This alpha strategy leverages fundamental metrics to identify stocks with improving profitability relative to their size. By calculating and tracking the ratio of profit to size over time, the strategy can pinpoint companies that are becoming more efficient and potentially undervalued. The example illustrates how this concept is applied and why it works, highlighting the benefits of using fundamental analysis to drive investment decisions.

---

1. [Simple Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Simple%20Price%20Reversion.md)
2. [Complicated Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Complicated%20Price%20Reversion.md)
3. [Hot news with reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Hot%20news%20with%20reversion.md)
4. [Short Overpriced Companies](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Short%20Overpriced%20Companies.md)
5. [Too much buzz is bad](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Too%20much%20buzz%20is%20bad.md)
6. [Profitability Compared to Capitalization](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Compared%20to%20Capitalization.md)
7. [Net Sentiment Analysis](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Net%20Sentiment%20Analysis.md)
