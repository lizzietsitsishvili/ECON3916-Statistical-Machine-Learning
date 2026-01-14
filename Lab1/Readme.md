# 🍔 Global Purchasing Power Parity Analysis via the Big Mac Index

## Objective

This project applies the **Law of One Price** to real-world data by using The Economist's Big Mac Index as a proxy for analyzing international currency valuations and testing purchasing power parity (PPP) theory across global markets.

## Economic Context

The **Law of One Price** states that in efficient markets with no transaction costs, identical goods should sell for the same price when expressed in a common currency. The Big Mac Index, developed by The Economist in 1986, leverages this principle by comparing the price of McDonald's Big Mac sandwiches across countries to assess whether currencies are trading at their "correct" level relative to the US dollar.

## Methodology

- **Data Collection & Construction**: Manually constructed a structured dataset using Python dictionaries containing Big Mac prices across multiple countries and their corresponding local exchange rates, based on The Economist's 2015 global survey data.

- **Implied PPP Calculation**: Computed the implied purchasing power parity exchange rate for each currency by dividing the local Big Mac price by the US Big Mac price, establishing the theoretical exchange rate at which the burger would cost the same in both markets.

- **Currency Valuation Analysis**: Calculated the percentage deviation between the implied PPP exchange rate and the actual market exchange rate to determine whether each currency was overvalued or undervalued relative to the US dollar.

- **Data Transformation**: Leveraged Pandas DataFrames to organize, manipulate, and analyze the currency valuation metrics, enabling efficient computation and clear presentation of results.

## Key Findings

[Insert your specific findings here. Example format:]

The analysis revealed significant currency misalignments across the sample countries:
- The **Norwegian Krone** was overvalued by approximately **X%**, suggesting that Big Macs in Norway are substantially more expensive in dollar terms than in the United States, potentially indicating higher local costs or stronger currency fundamentals.
- The **[Currency Name]** showed undervaluation of **Y%**, implying potential arbitrage opportunities and suggesting the currency may be trading below its PPP-implied fair value.
- These deviations from PPP highlight market frictions, including differences in labor costs, rent, taxation, and local market conditions that prevent perfect price convergence.

## Economic Implications

While the Big Mac Index is a simplified measure, it provides valuable insights into:
- **Currency misalignment** that may signal future exchange rate movements
- **Relative cost of living** differences across economies
- **Market efficiency** and the extent to which arbitrage opportunities persist in real-world markets

The persistence of significant deviations from PPP underscores the importance of factors beyond simple price arbitrage in determining exchange rates, including interest rate differentials, trade balances, and capital flows.

## Technical Skills Demonstrated

- Data structure design and manual dataset construction in Python
- Foreign exchange rate calculations and PPP theory application
- Pandas DataFrame manipulation for financial analysis
- Economic interpretation of quantitative results

---

*This project demonstrates the application of fundamental economic theory to real-world data analysis, bridging theoretical concepts with practical implementation.*
