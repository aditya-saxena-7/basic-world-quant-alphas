### Alpha Strategy: Simple Price Reversion

#### Alpha Formula
**Formula:** (High + Low) / 2 - Close

#### Data Fields:
- **High:** The highest price at which the stock traded during the day.
- **Low:** The lowest price at which the stock traded during the day.
- **Close:** The final price at which the stock traded when the market closed.

#### Parameters:
- **Top 3000 stocks:** The strategy applies to the top 3000 stocks by market capitalization or liquidity.
- **Market neutralization:** The portfolio is balanced to have an equal weight of long and short positions across the market.

### Strategy Logic

#### Concept
This alpha strategy is based on **mean reversion**, a concept that suggests prices and returns eventually move back towards the mean or average level. In this strategy, if a stock's closing price is lower than the average of its high and low prices for the day, the strategy suggests buying the stock the next day. The assumption is that the price will revert to the mean, offering a potential profit.

#### Execution
- **Calculation:** Calculate the average price for the day as \((\text{High} + \text{Low}) / 2\).
- **Comparison:** Compare the average price to the closing price.
  - If the closing price is lower than the average price, it suggests that the price might increase the next day.
  - The strategy then indicates a buy signal for such stocks.

### Terminologies

#### Mean Reversion
- **Definition:** The theory that prices and returns eventually move back towards the mean or average level.
- **Example:** If a stock typically trades around $100 but falls to $90, mean reversion suggests it will move back towards $100 over time.

#### Market Neutralization
- **Definition:** A strategy to balance long and short positions such that the overall market movements do not affect the portfolio.
- **Example:** If you have $5 million in long positions, you also have $5 million in short positions. This way, gains and losses are relative to the stocks within the market rather than the market's overall movement.

#### Sharpe Ratio
- **Definition:** A measure of the risk-adjusted return of an investment. It is the ratio of the return of the investment to its standard deviation.
- **Example:** A Sharpe ratio of 1.80 means the strategy returns 1.80 units of return for every unit of risk.

#### Turnover
- **Definition:** The percentage of the portfolio that is bought and sold over a period.
- **Example:** A turnover rate of 51% means that more than half of the portfolio's holdings are changed during the period.

#### Annual Returns
- **Definition:** The percentage gain or loss in the value of the portfolio over a year.
- **Example:** An annual return of 17% means the portfolio's value increases by 17% over a year.

#### Fitness
- **Definition:** A measure of how well the alpha fits the historical data.
- **Example:** A fitness of 1.03 suggests the alpha performs slightly better than expected based on historical data.

### Why It Works
1. **Mean Reversion:** This strategy capitalizes on the mean reversion tendency of stock prices. By buying stocks that have dropped below their average daily price, it bets on their rebound.
2. **Market Neutralization:** By being market-neutral, the strategy minimizes exposure to market-wide movements, reducing risk and focusing on the relative performance of stocks.
3. **Simplicity:** The strategy's simplicity allows for easy implementation and monitoring, making it efficient in terms of computational resources and execution.

### Learning Points for Beginners
- **Understanding Mean Reversion:** Recognize that stocks often revert to a mean price, which can be exploited for profit.
- **Market Neutrality:** Learn the importance of balancing long and short positions to mitigate market-wide risks.
- **Key Metrics:** Familiarize yourself with key performance metrics like Sharpe ratio, turnover, and annual returns to evaluate strategy effectiveness.
- **Backtesting:** Appreciate the value of historical backtesting to validate strategies before real-world application.

This alpha demonstrates that even simple strategies can yield significant returns when properly tested and executed, providing a solid foundation for further exploration into more complex quantitative finance strategies.

---

1. [Simple Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Simple%20Price%20Reversion.md)
2. [Complicated Price Reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Complicated%20Price%20Reversion.md)
3. [Hot news with reversion](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Hot%20news%20with%20reversion.md)
4. [Short Overpriced Companies](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Short%20Overpriced%20Companies.md)
5. [Too much buzz is bad](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Too%20much%20buzz%20is%20bad.md)
6. [Profitability Compared to Capitalization](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Compared%20to%20Capitalization.md)
7. [Net Sentiment Analysis](https://github.com/aditya-saxena-7/basic-world-quant-alphas/blob/main/Net%20Sentiment%20Analysis.md)
