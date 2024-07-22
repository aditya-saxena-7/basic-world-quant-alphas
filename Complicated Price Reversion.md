### Alpha Strategy: Complicated Price Reversion

#### Alpha Formula
**Formula:**
rel_days_since_max = rank(ts_arg_max(close, 30));
decline_pct = (vwap - close) / close;
decline_pct / min( ts_decay_linear(rel_days_since_max, 1), 0.15)

#### Data Fields:
- **VWAP (Volume-Weighted Average Price):** An average price that takes into account the volume traded at different prices.
- **Close:** The final price at which the stock traded when the market closed.
- **Rank:** A ranking function that assigns a rank based on the value.
- **Time Since Max (ts_arg_max):** The number of days since the stock reached its maximum price in the past 30 days.
- **Linear Decay:** A function that decreases the value linearly over time.

#### Parameters:
- **Top 200 stocks:** The strategy applies to the top 200 stocks by market capitalization or liquidity.
- **Market neutralization:** The portfolio is balanced to have an equal weight of long and short positions across the market.

### Alpha Strategy: Complicated Price Reversion

#### Strategy Logic

#### Concept
This alpha strategy enhances the simple price reversion idea by incorporating the concept of **relative time since the stock's peak** and using the **Volume-Weighted Average Price (VWAP)** instead of the simple average price. The idea is to identify stocks that have recently experienced a maximum price (a peak) and then declined, with the assumption that these stocks are likely to revert to their mean price. This mean reversion tendency can be exploited for profit.

**Key Enhancements:**

1. **Relative Time Since Peak:** 
   - This concept identifies how long it has been since the stock hit its highest price within a specified period (30 days in this case). Stocks that have recently peaked might be more likely to revert to their average price.
   - The strategy ranks stocks based on how recent their peak was, with the assumption that more recent peaks might have a stronger reversion tendency.

2. **VWAP (Volume-Weighted Average Price):** 
   - VWAP is considered a more accurate measure of the average price because it takes into account the volume of trades at different prices, rather than just the simple average of high and low prices.
   - This ensures that the strategy considers the price levels at which most trading occurred, providing a more realistic view of the stock's average value.

#### Why It Works

**Example:**
Imagine we have two stocks, Stock A and Stock B, both in the top 200 by market capitalization. We analyze their price movements and VWAP over the last 30 days.

1. **Calculate Relative Time Since Peak:**
   - **Stock A:** Hit its highest price of $150 two days ago. Current price is $140.
   - **Stock B:** Hit its highest price of $120 fifteen days ago. Current price is $110.

   Stock A's peak is more recent, so it gets a higher rank in terms of relative time since the peak.

2. **Calculate Decline Percentage:**
   - **Stock A:** VWAP = $145, Current price = $140.
     \[ \text{Decline Percentage} = \frac{145 - 140}{140} \approx 0.036 \text{ or 3.6%} \]
   - **Stock B:** VWAP = $115, Current price = $110.
     \[ \text{Decline Percentage} = \frac{115 - 110}{110} \approx 0.045 \text{ or 4.5%} \]

3. **Compute the Alpha Value:**
   - For Stock A:
     \[ \text{Alpha} = \frac{0.036}{\min(\text{Linear Decay of Relative Days Since Max}, 0.15)} \]
   - For Stock B:
     \[ \text{Alpha} = \frac{0.045}{\min(\text{Linear Decay of Relative Days Since Max}, 0.15)} \]

   Assuming the linear decay value for Stock A (recent peak) is lower than 0.15, and for Stock B (older peak) it's higher, Stock A's alpha value will be higher, indicating a stronger buy signal.

**Why It Works:**

1. **Mean Reversion:** Stocks that have recently peaked and then declined are likely to revert to their average price. This mean reversion tendency can be exploited for profit.
2. **Accurate Average Price:** Using VWAP provides a more accurate measure of the average price, taking into account the volume of trades at different prices. This ensures that the strategy is based on realistic average values rather than simple averages.
3. **Relative Timing:** By focusing on the time since the last peak, the strategy targets stocks that have a stronger potential for mean reversion. Stocks that have recently peaked might have been overbought and are now more likely to revert to their average price.

#### Execution
1. **Calculate Relative Days Since Max:**
   - Determine the number of days since the stock last hit its highest price in the past 30 days.
   - Rank this value among all stocks.
2. **Calculate Decline Percentage:**
   - Compute the percentage decline from the VWAP to the closing price.
3. **Combine Metrics:**
   - Divide the decline percentage by the minimum of the linear decay of relative days since max and 0.15.

### Terminologies

#### VWAP (Volume-Weighted Average Price) 📊
- **Definition:** VWAP is the average price a stock has traded at throughout the day, based on both volume and price.
- **Example:** If a stock traded 100 shares at $10, 200 shares at $15, and 300 shares at $20, the VWAP is calculated as:
  \[ \text{VWAP} = \frac{(100 \times 10) + (200 \times 15) + (300 \times 20)}{100 + 200 + 300} = 17.50 \]

#### Rank 🔢
- **Definition:** A function that assigns a relative ranking to each stock based on a specific value.
- **Example:** If you rank stocks based on their returns, the stock with the highest return gets rank 1, the second-highest gets rank 2, and so on.

#### Linear Decay 📉
- **Definition:** A function that decreases the value linearly over time.
- **Example:** If the initial value is 1 and it decreases by 0.1 each day, after 5 days the value will be 0.5.

#### Market Neutralization ⚖️
- **Definition:** A strategy that balances long and short positions to reduce exposure to the overall market movements.
- **Example:** If you invest $1 million in stocks you expect to go up (long positions) and $1 million in stocks you expect to go down (short positions), you are market-neutral. If the market goes up or down, your losses and gains from long and short positions should balance out.

### Performance Metrics

#### Sharpe Ratio 📈
- **Definition:** A measure of the risk-adjusted return of an investment. It is the ratio of the return of the investment to its standard deviation.
- **Example:** A Sharpe ratio of 1.58 means the strategy returns 1.58 units of return for every unit of risk.

#### Turnover 🔄
- **Definition:** The percentage of the portfolio that is bought and sold over a period.
- **Example:** A turnover rate of 49% means that nearly half of the portfolio's holdings are changed during the period.

#### Annual Returns 📅
- **Definition:** The percentage gain or loss in the value of the portfolio over a year.
- **Example:** An annual return of 23% means the portfolio's value increases by 23% over a year.

#### Fitness 💪
- **Definition:** A measure of how well the alpha fits the historical data.
- **Example:** A fitness of 1.09 suggests the alpha performs 9% better than expected based on historical data.

### Why It Works
1. **Refined Mean Reversion:** This strategy focuses on stocks that have recently peaked and then declined, targeting those with potential for reversion to the mean.
2. **Accurate Pricing with VWAP:** Using VWAP provides a more accurate measure of the average price, improving the strategy’s accuracy.
3. **Relative Comparison:** The use of percentages allows for fair comparison across different stocks, and clamping the denominator avoids skewing the results due to outliers.
4. **Market Neutralization:** By being market-neutral, the strategy minimizes exposure to market-wide movements, reducing risk and focusing on the relative performance of stocks.

### Learning Points for Beginners
- **Combining Metrics:** Learn how combining different metrics (price, time, volume) can refine a strategy.
- **Using VWAP:** Understand the importance of VWAP for a more accurate measure of average price.
- **Key Metrics:** Familiarize yourself with key performance metrics like Sharpe ratio, turnover, and annual returns to evaluate strategy effectiveness.
- **Backtesting:** Appreciate the value of historical backtesting to validate strategies before real-world application.

This advanced strategy demonstrates the power of refining simple concepts with additional data and metrics to improve performance while maintaining a disciplined approach to risk management.

---

1. [Simple Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Simple%20Price%20Reversion.md)
2. [Complicated Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Complicated%20Price%20Reversion.md)
3. [Hot news with reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Hot%20news%20with%20reversion.md)
4. [Short Overpriced Companies](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Short%20Overpriced%20Companies.md)
5. [Too much buzz is bad](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Too%20much%20buzz%20is%20bad.md)
6. [Profitability Compared to Capitalization](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Compared%20to%20Capitalization.md)
7. [Net Sentiment Analysis](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Net%20Sentiment%20Analysis.md)
