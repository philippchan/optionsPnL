# Decomposition of P&L of European Options
Options is one of the most versatile instruments in the trading world. When you trade options, your profit or loss (P&L) depends on various factors. These factors are often measured using something called “Greeks,” which are sensitivity measures indicating how your option’s value changes in response to different factors like price movements, time passing, or changes in volatility. Think of it as breaking down your overall profit or loss into different parts, each representing the impact of a specific factor. This helps you understand where your gains or losses are coming from.

1. **Delta**: Delta measures how much the option price changes for a given change in the underlying stock price. So, part of your P&L comes from changes in the stock price, and delta tells you how much.

2. **Theta**: Theta measures how much the option price changes as time passes. Options lose value over time due to expiration, and theta tells you how much of your P&L is due to this time decay.

3. **Vega**: Vega measures how much the option price changes with changes in volatility. If volatility increases, option prices tend to rise, and vice versa. So, vega tells you how much of your P&L is due to changes in volatility.

4. **Gamma**: Gamma measures how fast delta changes with changes in the stock price. It's like the speed of delta. So, gamma tells you how much your delta (and therefore your P&L from price movements) changes for a given change in the stock price.

5. **Volga**: Volga measures how much the vega (sensitivity to volatility) changes with changes in volatility. It's like the gamma of vega. So, volga tells you how much your vega (and therefore your P&L from changes in volatility) changes with volatility changes.

6. **Vanna**: Vanna measures how much the delta changes with changes in volatility. It's like the combination of gamma and vega. So, vanna tells you how much your delta (and therefore your P&L from price movements) changes with changes in volatility.

7. **Unexplained**: Sometimes, there may be changes in your P&L that can't be completely explained by these factors. This is the "unexplained" part, which could be due to various reasons like market inefficiencies or factors not captured by the Greeks.

We’ll define a class to represent options based on the Black-Scholes model. This class will include methods to calculate the Greeks: Delta, Gamma, Theta, Vega, Volga, and Vanna.

We'll then decompose the P&L into contributions from different Greeks and plot it with a bar chart. The equations for each Greek:

1. **Delta**: $\Delta = \frac{{\partial V}}{{\partial S}}$
2. **Gamma**: $\Gamma = \frac{{\partial^2 V}}{{\partial S^2}}$
3. **Theta**: $\Theta = \frac{{\partial V}}{{\partial t}}$
4. **Vega**: $\nu = \frac{{\partial V}}{{\partial \sigma}}$
5. **Volga**: $\text{Volga} = \frac{{\partial \nu}}{{\partial \sigma}}$
6. **Vanna**: $\text{Vanna} = \frac{{\partial^2 V}}{{\partial S \partial \sigma}}$

And their profit and loss (P&L) contributions:

1. **Delta P&L:** $\text{Delta PnL} = \Delta \times (S_1 - S_0)$
2. **Gamma P&L:** $\text{Gamma PnL} = 0.5 \times \Gamma \times (S_1 - S_0)^2$
3. **Theta P&L:** $\text{Theta PnL} = \Theta \times \Delta t$
4. **Vega P&L:** $\text{Vega PnL} = \nu \times (\sigma_1 - \sigma_0)$
5. **Volga P&L:**$\text{Volga PnL} = 0.5 \times \text{Volga} \times (\sigma_1 - \sigma_0)^2$
6. **Vanna P&L:** $\text{Vanna PnL} = Vanna \times (S_1 - S_0) \times (\sigma_1 - \sigma_0)$
