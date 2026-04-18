FedSpeak Analysis — NLP on FOMC Minutes
Objective

This project applies natural language processing (NLP) techniques to Federal Open Market Committee (FOMC) meeting minutes to quantitatively analyze monetary policy communication, sentiment dynamics, and shifts in economic outlook over time.

Methodology
Collected and preprocessed FOMC meeting minutes, including tokenization, lemmatization, and removal of stop words to standardize textual data
Constructed a TF-IDF document-term matrix using both unigrams and bigrams to capture key economic language and phrases
Implemented the Loughran-McDonald financial sentiment dictionary to compute document-level net sentiment and uncertainty scores
Visualized sentiment trends across more than two decades of FOMC communication to identify macroeconomic patterns
Reduced dimensionality of TF-IDF features using PCA and applied K-Means clustering to group documents into distinct communication regimes
Conducted a regime comparison by splitting the data into pre-COVID and post-COVID periods to evaluate structural changes in tone and uncertainty
Key Findings

The analysis reveals that FOMC communication is consistently measured and slightly positive on average, but varies meaningfully across economic cycles. Clustering results suggest distinct communication regimes, including policy-stable periods, growth-oriented discussions, and more cautious, risk-focused narratives. Following COVID-19, sentiment became notably less positive while uncertainty increased, reflecting heightened macroeconomic volatility, policy ambiguity, and evolving risks such as inflation dynamics and supply chain disruptions. These findings highlight how central bank language adapts systematically to changing economic conditions.
