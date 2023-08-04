# Portfolio optimization with Genetic algorithm
------------------------------------------------------------------------------------------------------------------------------------
### Background :

**Modern portfolio theory (MPT)** is a method used to construct portfolios that maximize expected return for a given level of risk. The main idea of MPT is that an investment's risk and return characteristics should not be viewed in isolation but should be evaluated by how the investment affects the overall portfolio's risk and return.

A genetic algorithm (GA) is a search heuristic that is inspired by Charles Darwin's theory of natural evolution. This algorithm reflects the process of natural selection, where the fittest individuals are selected for reproduction to produce the next generation's offspring. The power of GA makes it possible to find the optimal portfolio. 

------------------------------------------------------------------------------------------------------------------------------
### Problem statement :

The task is to optimize a portfolio composed of GICS (Global Industry Classification Standard) sector ETFs. The main goal is to maximize the utility function, which is a function of the portfolio's expected return and variance. The challenge is to find the optimal weights for each ETF in the portfolio that maximizes the utility function.

------------------------------------------------------------------------------------------------------------------------------------
### Given Data : 

The data used in this analysis are daily adjusted closing prices for each Vanguard ETF in the portfolio. The ETFs are crawled from Yahoo Finance and cover the period from Jan 1, 2006, to Dec 31, 2022. The portfolio includes the following ETFs:

- VDE: Energy
- VAW: Materials
- VIS: Industrial
- VCR: Consumer Discretionary
- VDC: Consumer Staples
- VHT: Health Care
- VFH: Financials
- VGT: Information Technology
- VOX: Communication Services
- VPU: Utilities Sector
- VNQ: Real Estate
------------------------------------------------------------------------------------------------------------------------------------
### Approach and Task

The approach taken in this analysis involves several steps:

1. Data Preparation: Download the ETF price data from Yahoo Finance and calculate daily log returns.

2. Parameter calculation: Calculate the Compound Annual Growth Rate (CAGR) and the annualized variance for each ETF. Also, calculate the covariance matrix for the ETF returns.

3. Define a Chromosome and Generate an initial population

4. Select an Elite population that filters the elite chromosome, which has the highest sharp ratio, which was calculated in the fitness function

5. **Mutation**: A function that will perform mutation in a chromosome. Randomly choose 2 numbers in the range of the number of assets

6. Genetic algorithm application: Apply the genetic algorithm to the portfolio optimization problem. This involves defining selection, crossover, and mutation operators. These operators are used to generate new solutions (weights) from the existing population.
   - Blended Crossover
   - Arithmetic crossover
   - Uniform Crossover

7. Next generation:  A function which performs mutation and crossover and builds a new generation of chromosomes.
   
8. Iteration: Iterate the genetic algorithm for a fixed number of iterations or until convergence. After each iteration, select the optimal solutions (the elite) based on the fitness function.
------------------------------------------------------------------------------------------------------------------------------------
### Conclusion

In conclusion, genetic algorithms provide a flexible and powerful tool for portfolio optimization. By defining a suitable fitness function and applying selection, crossover, and mutation operators, it is possible to generate a set of portfolio weights that maximize the utility(sharp) function. The result is a portfolio that balances the trade-off between risk and return, providing the highest utility. The final solution not only provides the optimal weights for the portfolio but also provides insight into the evolutionary process of the algorithm, illustrating how the portfolio's risk and return characteristics evolve over time.

### References
-----------------------------------------------------------------------------------------------------------------------------------
1. https://www.researchgate.net/publication/286952225_A_heuristic_crossover_for_portfolio_selection
2. https://www.semanticscholar.org/paper/Genetic-Algorithm-Application-to-Portfolio-Stomeo-Caenazzo/9888061ea3326ff9b41c807ed21f0c10463b7879?p2df
3. 