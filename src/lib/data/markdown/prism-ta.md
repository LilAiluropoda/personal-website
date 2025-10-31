# Personal Thoughts

Just put the money into index funds, passive investment is good enough.

# Description

This project represents the second and final part of my final year project, completed collaboratively with my groupmate Cassie. To recap our previous work: we identified significant room for improvement in Omer Sezer's strategy during strongly trended markets (characterized by sudden rapid price movements). This became the focus of our second project—enhancing his solution.

Our approach was straightforward: if his strategy underperforms in strongly trending markets, why not switch to alternative strategies? We designed a system consisting of a market trend predictor and a collection of trading strategies. The predictor would select the most appropriate strategy based on the forecasted market direction. While this sounds simple in theory, we immediately encountered our first challenge: how do we define "market trend"?

While it's easy to identify extreme cases like the 2008 bear market, broader perspectives might classify that same period as neutral with high volatility. The key insight was that trend definition requires specifying a time scale. After consideration, I selected a 20-day window (roughly one month of trading days) as our timeframe.

Using data from Omer Sezer's repository, we constructed our dataset. Without access to 20 years of Dow 30 market news, we used index data as a proxy for general market conditions and technical indicators for specific stocks to capture various price movement patterns. We labeled our data using a simple algorithm: within each 20-day window, we ran representative strategies for uptrend, no trend, and downtrend conditions, then labeled the period with the strategy that yielded the highest returns. We selected Buy and Hold for uptrends, Sell and Hold for downtrends, and Omer's Mean Reversion strategy for neutral markets.

The most interesting challenge for me was strategy design. How could I create an approach that directly reflected the predictor's performance without being influenced by sophisticated risk management features? If I added mechanisms like stop-loss or profit-taking, success might stem from these features rather than the model's predictive accuracy. My solution was the "Roulette" strategy.

This approach divides the portfolio into 20 chunks (matching our time window). Each day, the model invests one chunk into the strategy selected by the predictor and locks the position for 20 days. On the 21st day, the first locked position exits and is reinvested into the newly selected strategy. This design provides the most direct translation of the predictor's performance into trading outcomes.

While this strategy would be impractical in real markets due to transaction costs, our goal wasn't profitability but rather demonstrating predictive capability for price movements.

## Tech Used

We maintained **Python** as our primary tech stack. For visualization, we used ***Matplotlib** for static plots and created interactive charts with **Streamlit**.

A notable improvement from our first project was addressing two key pain points: file management and collaboration. The first project involved cumbersome CSV I/O operations and difficult-to-track data transformations. Collaboration also proved challenging with frequent git conflicts and code review difficulties.

For this project, I implemented a completely different approach:

- **Data Management**: We used **PostgreSQL** with multiple tables and schemas to store indicators, stock data, and experiment results—a far more elegant solution than directory-based CSV files.

- **Collaboration**: We adopted a **polyrepo** architecture, breaking the project into component-specific repositories. This reduced cognitive load, made code complexity manageable, and minimized conflicts by rarely working on the same repository simultaneously (though occasional firefighting in my partner's repo was still necessary).

# Future Plan

The backtesting framework I built from scratch is interesting and could be extended to support additional strategies. However, I currently have other priorities to pursue.

# GitHub Repo Link

https://github.com/LilAiluropoda/CSCI4999-Deep-Learning-Application-In-Finance-Part2

# References

https://github.com/LilAiluropoda/CSCI4998-Deep-Learning-Application-In-Finance-Part1

https://github.com/omerbsezer/SparkDeepMlpGADow30/blob/master/README.md?plain=1