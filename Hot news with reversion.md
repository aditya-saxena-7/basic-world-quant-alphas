### Alpha Strategy: Hot News with Reversion

#### Alpha Formula
**Formula:**
\[ \text{Alpha} = \text{rank}\left(\text{ts\_sum}(\text{avg\_news}, 60)\right) > 0.5 ? 1 : \text{rank}\left(-\text{ts\_delta}(\text{close}, 2)\right) \]

Where:
- **avg_news:** Average news sentiment or score after certain news events (nws12_afterhsz_sl).
- **ts_sum:** The sum of a time series over a specified period (60 days here).
- **rank:** A function that assigns a relative rank to a value within a group.
- **ts_delta:** The change in the time series over a specified period (2 days here).

#### Data Fields:
- **avg_news:** The average sentiment or impact of news articles.
- **close:** The closing price of the stock.
- **rank:** A ranking function that assigns a rank based on the value.

#### Parameters:
- **Top 3000 stocks:** The strategy applies to the top 3000 stocks by market capitalization or liquidity.
- **Subindustry neutralization:** The portfolio is balanced to have an equal weight of long and short positions within each subindustry, reducing subindustry-wide risk.

### Strategy Logic

#### Concept
This alpha strategy combines momentum based on news with a reversion strategy. It buys stocks that are relatively newsworthy compared to their peers within the same subindustry. For stocks with less news coverage, it applies a simple price reversion strategy.

#### Execution
1. **Calculate Average News Impact:**
   - Determine the average news sentiment or score for each stock.
2. **Sum News Impact over 60 Days:**
   - Sum the average news scores over the past 60 days for each stock.
3. **Rank News Impact:**
   - Rank the stocks based on the summed news impact.
4. **Decision Rule:**
   - If the stock's news rank is above the median (0.5), assign a buy signal (1).
   - If the stock's news rank is below the median, apply a price reversion strategy by ranking the negative 2-day price change and buying the higher-ranked stocks.

### Terminologies

#### Average News Sentiment (avg_news) 📰
- **Definition:** The average impact or sentiment score of news articles related to a stock.
- **Example:** If a stock has three news articles with sentiment scores of 0.6, 0.4, and 0.8, the avg_news is:
  \[ \text{avg\_news} = \frac{0.6 + 0.4 + 0.8}{3} = 0.6 \]

#### Time Series Sum (ts_sum) 📊
- **Definition:** The total sum of a time series over a specified period.
- **Example:** If the avg_news scores over 5 days are [0.5, 0.6, 0.4, 0.7, 0.3], the ts_sum over these days is:
  \[ \text{ts\_sum} = 0.5 + 0.6 + 0.4 + 0.7 + 0.3 = 2.5 \]

#### Time Series Delta (ts_delta) 📉
- **Definition:** The change in the time series value over a specified period.
- **Example:** If a stock's closing prices over two days are $100 and $105, the 2-day ts_delta is:
  \[ \text{ts\_delta} = 105 - 100 = 5 \]

#### Rank 🔢
- **Definition:** A function that assigns a relative ranking to each stock based on a specific value.
- **Example:** If you rank stocks based on their news impact scores, the stock with the highest score gets rank 1, the second-highest gets rank 2, and so on.

#### Subindustry Neutralization ⚖️
- **Definition:** A strategy that balances long and short positions within each subindustry to reduce exposure to subindustry-wide movements.
- **Example:** If you invest $1 million in stocks within the pharmaceutical subindustry and also short $1 million in stocks within the same subindustry, you are subindustry-neutral.

### Performance Metrics

#### Sharpe Ratio 📈
- **Definition:** A measure of the risk-adjusted return of an investment. It is the ratio of the return of the investment to its standard deviation.
- **Example:** A Sharpe ratio of 1.84 means the strategy returns 1.84 units of return for every unit of risk.

#### Turnover 🔄
- **Definition:** The percentage of the portfolio that is bought and sold over a period.
- **Example:** A turnover rate of 9% means that 9% of the portfolio's holdings are changed during the period.

#### Annual Returns 📅
- **Definition:** The percentage gain or loss in the value of the portfolio over a year.
- **Example:** An annual return of 4.29% means the portfolio's value increases by 4.29% over a year.

#### Fitness 💪
- **Definition:** A measure of how well the alpha fits the historical data.
- **Example:** A fitness of 1.08 suggests the alpha performs 8% better than expected based on historical data.

### Why It Works
1. **News Impact:** This strategy captures the momentum effect where stocks with positive news tend to perform better in the short term.
2. **Reversion for Less Newsworthy Stocks:** By applying a simple price reversion strategy to less newsworthy stocks, the alpha leverages mean reversion tendencies.
3. **Subindustry Neutralization:** Balancing positions within subindustries minimizes exposure to sector-wide movements, focusing on relative performance within subindustries.
4. **Dynamic Strategy:** The combination of news-based momentum and price reversion makes the strategy adaptable to different market conditions.

### Learning Points for Beginners
- **Combining Strategies:** Learn how combining different strategies (momentum based on news and price reversion) can improve overall performance.
- **News Sentiment Analysis:** Understand the importance of news sentiment and its impact on stock prices.
- **Subindustry Neutralization:** Recognize the benefits of neutralizing positions within subindustries to reduce specific risks.
- **Key Metrics:** Familiarize yourself with key performance metrics like Sharpe ratio, turnover, and annual returns to evaluate strategy effectiveness.
- **Backtesting:** Appreciate the value of historical backtesting to validate strategies before real-world application.

This strategy highlights the effectiveness of blending momentum and reversion approaches, leveraging both news sentiment and price movements to generate consistent returns with lower turnover.

---

1. [Complicated Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Complicated%20Price%20Reversion.md)
2. [Hot news with reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Hot%20news%20with%20reversion.md)
3. [Short Overpriced Companies](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Short%20Overpriced%20Companies.md)
4. [Simple Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Simple%20Price%20Reversion.md)
5. [Too much buzz is bad](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Too%20much%20buzz%20is%20bad.md)
