# DDPG on Option Hedging  

## Project Overview  
This project implements a reinforcement learning (RL) model using Deep Deterministic Policy Gradient (DDPG) to hedge the potential risk of selling a European call option by trading the underlying asset. The model is trained on Apple Inc. (AAPL) stock price data from Yahoo Finance and compared against delta hedging using the Black-Scholes model.  

## Features  
- **Reinforcement Learning for Option Hedging**: Utilizes DDPG to learn an optimal hedging strategy.  
- **Comparison with Delta Hedging**: Evaluates the RL approach against the traditional Black-Scholes delta hedging method.  
- **Real Market Data**: Uses AAPL adjusted closing prices from 2012 to 2024.  

## Methodology  
1. **Data Preparation**  
   - Source: Yahoo Finance  
   - Time Period: 2012–2024  
   - Split: 80% training, 20% testing  

2. **Environment Setup**  
   - State Space: `(last time step stock price, volatility, current position, time to maturity)`  
   - Action Space: `[0,1]` representing the hedge position in the stock  
   - Reward Function: Gain/loss after action, adjusted using an exponential utility function  

3. **Training & Evaluation**  
   - The RL agent interacts with simulated market conditions, learning to hedge risk effectively.  
   - Performance is evaluated based on mean profit and standard deviation compared to delta hedging.  

## Results  
- The DDPG model achieves similar mean profit and loss but with **lower variance** than delta hedging.  
- However, the RL agent does not always converge, indicating challenges in training stability.  

## Future Work  
- Improve model stability and convergence.  
- Investigate different reward functions and neural network architectures.  
- Extend to more complex options (e.g., American or exotic options).  
