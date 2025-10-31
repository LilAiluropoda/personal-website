# Personal Thoughts

Trading is tough!

# Description

This project constitutes the first part of my final year project, completed collaboratively with my groupmate Cassie (though I handled the majority of the work). The goal, set by our professor, was to study the non-stationarity phenomenon in stock price time-series and develop a model to represent it. In simple terms, this involved modeling the time series and performing predictions to demonstrate that we had successfully captured its behavior.

Coming from a pure Computer Science background, I had little initial understanding of non-stationarity. So, the first step was to conduct a literature review to learn from existing research. I found the work of Omer Sezer on the RSI-MA trading strategy to be particularly accessible—it was straightforward to understand and replicate.

The core of his strategy is RSI-SMA, a mean-reversion approach. He used Simple Moving Average (SMA) to identify the "market condition" and then applied the Relative Strength Index (RSI) to determine entry and exit points. The challenge lies in selecting the optimal RSI threshold (a continuous range from 1 to 100) and the ideal time window for the RSI calculation. Omer addressed this by using a genetic algorithm to optimize the RSI parameters based on historical data. However, to make the model predictive and adaptable to new data without repeatedly running the genetic algorithm, he employed a vanilla neural network to model the relationship between RSI and price movements.

We decided to reproduce his experimental results to validate his work. Although he kindly provided an open-source repository, the implementation was in Scala using the Hadoop framework. Since our tech stack is Python-based, I spent a week reading and translating the code from Scala to Python.

## Tech Used

The original work was implemented in **Scala** with **Hadoop**.  
I migrated the codebase to **Python**.

# Future Plan

There are no further development plans for this part of the project. The second part has also been published on GitHub:  
https://github.com/LilAiluropoda/CSCI4999-Deep-Learning-Application-In-Finance-Part2

# GitHub Repo Link

https://github.com/LilAiluropoda/CSCI4998-Deep-Learning-Application-In-Finance-Part1

# References

https://github.com/omerbsezer/SparkDeepMlpGADow30/blob/master/README.md?plain=1