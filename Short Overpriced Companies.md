### Alpha Strategy: Short Overpriced Companies

#### Alpha Formula
**Formula:**
\[ \text{Alpha} = -\text{ts\_zscore}\left(\frac{\text{Enterprise Value}}{\text{EBITDA}}, 63\right) \]

Where:
- **Enterprise Value (EV):** The total value of a company, including its market capitalization, debt, and excluding cash.
- **EBITDA:** Earnings Before Interest, Taxes, Depreciation, and Amortization, a measure of a company's overall financial performance.
- **ts_zscore:** Time series z-score, a statistical measure that describes a value's relation to the mean of a group of values over a specified lookback period (63 days in this case).

#### Parameters:
- **Top 3000 stocks:** The strategy applies to the top 3000 stocks by market capitalization or liquidity.
- **Industry neutralization:** The portfolio is balanced to have an equal weight of long and short positions within each industry, reducing industry-wide risk.

### Strategy Logic

#### Concept
This alpha strategy is based on identifying and shorting stocks with rising valuations that outpace their earnings, relative to their peers within the same industry. By using the enterprise value-to-EBITDA ratio, this strategy focuses on fundamental valuations rather than just price movements.

#### Execution
1. **Calculate EV/EBITDA Ratio:**
   - For each stock, calculate the enterprise value and EBITDA, then find their ratio.
2. **Compute Time Series Z-Score:**
   - Calculate the z-score of the EV/EBITDA ratio over the past 63 days to understand how current valuations compare to historical averages.
3. **Short Overpriced Stocks:**
   - Rank stocks by their z-scores within their industry. The strategy suggests shorting stocks with the highest (most positive) z-scores, as these are considered overpriced relative to their historical valuations.

### Terminologies

#### Enterprise Value (EV) 💼
- **Definition:** The total value of a company, including its market capitalization, debt, and excluding cash.
- **Example:** If a company has a market capitalization of $100 million, debt of $20 million, and cash of $10 million, the enterprise value is:
  \[ \text{EV} = \$100 \text{ million} + \$20 \text{ million} - \$10 \text{ million} = \$110 \text{ million} \]

#### EBITDA 💵
- **Definition:** Earnings Before Interest, Taxes, Depreciation, and Amortization. It measures a company's overall financial performance.
- **Example:** If a company has revenues of $50 million, expenses (excluding interest, taxes, depreciation, and amortization) of $30 million, the EBITDA is:
  \[ \text{EBITDA} = \$50 \text{ million} - \$30 \text{ million} = \$20 \text{ million} \]

#### Time Series Z-Score (ts_zscore) 📊
- **Definition:** A statistical measure that describes a value's relation to the mean of a group of values over a specified lookback period.
- **Example:** If a stock’s EV/EBITDA ratio has a mean of 10 and a standard deviation of 2 over the past 63 days, and the current ratio is 14, the z-score is:
  \[ \text{Z-Score} = \frac{14 - 10}{2} = 2 \]

#### Industry Neutralization ⚖️
- **Definition:** A strategy that balances long and short positions within each industry to reduce exposure to industry-wide movements.
- **Example:** If you short $1 million in tech stocks, you also hold $1 million in tech stocks you expect to go up, balancing the portfolio within that industry.

### Performance Metrics

#### Sharpe Ratio 📈
- **Definition:** A measure of the risk-adjusted return of an investment. It is the ratio of the return of the investment to its standard deviation.
- **Example:** A Sharpe ratio of 2.00 means the strategy returns 2.00 units of return for every unit of risk.

#### Turnover 🔄
- **Definition:** The percentage of the portfolio that is bought and sold over a period.
- **Example:** A turnover rate of 25% means that one-fourth of the portfolio's holdings are changed during the period.

#### Annual Returns 📅
- **Definition:** The percentage gain or loss in the value of the portfolio over a year.
- **Example:** An annual return of 10% means the portfolio's value increases by 10% over a year.

#### Fitness 💪
- **Definition:** A measure of how well the alpha fits the historical data.
- **Example:** A fitness of 1.26 suggests the alpha performs 26% better than expected based on historical data.

### Why It Works
1. **Fundamental Focus:** This strategy uses fundamental data (EV/EBITDA ratio) which is more stable and changes less frequently than price-volume data, leading to lower turnover.
2. **Industry Neutralization:** By being industry-neutral, the strategy minimizes exposure to industry-wide movements, focusing on relative overvaluation within the industry.
3. **Timely Analysis:** The use of a 63-day lookback period captures the most recent earnings and valuation trends, making the strategy responsive to quarterly reports.

### Learning Points for Beginners
- **Fundamental Analysis:** Understand how fundamental metrics like EV/EBITDA can indicate overvaluation or undervaluation.
- **Z-Score Usage:** Learn how statistical measures like the z-score help compare current values to historical averages.
- **Industry Neutralization:** Recognize the importance of balancing positions within industries to reduce specific risks.
- **Key Metrics:** Familiarize yourself with key performance metrics like Sharpe ratio, turnover, and annual returns to evaluate strategy effectiveness.
- **Backtesting:** Appreciate the value of historical backtesting to validate strategies before real-world application.

This strategy highlights how a focus on fundamental valuations and industry-relative comparisons can identify overpriced stocks to short, demonstrating the effectiveness of combining quantitative and fundamental analysis.

---

1. [Complicated Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Complicated%20Price%20Reversion.md)
2. [Hot news with reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Hot%20news%20with%20reversion.md)
3. [Short Overpriced Companies](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Short%20Overpriced%20Companies.md)
4. [Simple Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Simple%20Price%20Reversion.md)
5. [Too much buzz is bad](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Too%20much%20buzz%20is%20bad.md)
