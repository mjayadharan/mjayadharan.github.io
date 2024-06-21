# Approximations and use of Mathematical Models in Finance, with a focus on Options trading with the help of Greeks. 

Author: Manu Jayadharan

## Introduction

In this post, I will discuss the pros and cons of financial modeling, specifically in the case of stock option pricing. I will talk about why financial models are imperfect and less predictive compared to models derived from physical laws. I will provide the definition and usage of Greeks from the perspective of a mathematician and share my thoughts on their application. 

I have made several simplifications of concepts in this post to make the reading short and comprehensive. I am also talking about modelling of financial instruments and not algorithmic trading which is a different topic. 

This post is inspired by a similar post I wrote on Reddit on a related topic. This post can be found [here](https://www.reddit.com/r/options/comments/1dk4bc1/only_numbers_that_are_correct_about_an_option_are/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button).

![Stock Picture](../items/im/stock_pic.jpg)

## What are Options ? Can we model them perfectly ?

- __Role of Options:__ Options are perhaps the most powerul instrument in the trading world, offering the right, but not the obligation, to buy or sell an asset at a predetermined price, making them essential for both trading strategies and hedging risks. The asset or underlying of an option could be anything like stocks, bonds, commodities, etc. It gives the traders an "option" to buy or sell their securities under certain conditions. 

Since stock options are the most common type of options (at least from the perspective of mere mortals, aka retail traders like us), I will focus on discussing these options for the remainder of this discussion.


- __Modelling an option:__ To mathematically find the price of an option, we rely on mathematical models like Black-Scholes, which use complex formulas to estimate their value. However, let's not forget that these models, while incredibly useful, are still imperfect reflections of reality like every other model in the world. Models are our, mere humans', humble attempts to understand complex world around us using simplifications and assumptions. For options they may come in the form of probability distribution of stock price, constant volatility and interest rates, etc. 

## Can the model predict the future value of an option ? 

The short anwer is __NO!__

### The market is unpredictable!!
![Stock Picture](../items/im/stock_im_3.jpg)

- This should come as no surprise since if the price of an option can be predicted like a phenomenon in physics, the world of finance won't be as interesting and exciting as it is. 
- The unpredictability of the stock market can be attributed to the indefinite number of factors that affect the price of a stock or its options. The factors include, but are not limited to, market sentiment, company performance, industry trends, interest rates, government policies, currency exchange rates, market liquidity, technological advancements, and natural disasters or climate events.

### If the market is not predictable, what is the best we can do ? 

We can do two things: 
1. __Model on assumptions__: We can make simplified assumptions about the market, such as the stock price following a specific type of stochastic process, some market factors remaining constant over short durations of time, and create a simple mathematical model of reality.
2. __Observe the market__: We can record transactions in the open market and utilize the prices at which traders are buying and selling stocks or any other related financial instruments.

### Model fitting eh ? 

__If you are a Scientist, and you have a model and some measurements what will you do ?__ 

- __Parameter estimation__: The natural approach would be to fit the model to the observed data. This is precisely what you could do in our example of option pricing models as well. We can use interest rates, prices, and volatility that are either observed directly in the market or inferred from other transactions to fit the parameters of your model, ensuring that your model gives a price that exactly matches the market price.  
- __Bootstrapping__: In the finance world, the process of parameter estimation, more accurately the market data estimation, from various types of observed data is called bootstrapping. You can bootstrap the interest rate curve, credit curve, volatility surface, etc., from  rates/prices quoted on the market.

## Physics laws vs Financial models
- __Physics__: In physics, we can create highly accurate models based on reasonable assumptions, and these models, often represented by differential equations, excel at predicting future states. There are often separations of scales which allow us to isolate a particular phenomenon or state from the influence of surrounding factors.

  
![Stock Picture](../items/im/stock_im_2.jpg)

- __Finance__: Financial modeling, however, is a different beast. The models are inherently stochastic, and on top of that, we use a method called risk-neutral pricing for modeling financial derivatives. In simple terms, this approach assumes the market has perfect knowledge of an instrument's value and is always correct. However, the market is constantly changing and influenced by numerous interrelated factors, making the assumptions in financial modeling much more tenuous and the separation of scales impossible compared to those in physics.
- __Poor prediction__: Because of all the factors mentioned above, it is not surprising that the predictive capabilities of financial models are significantly less reliable than those of physical models.





## What good are financial models if they can't predict the future price ? 

![Stock Picture](../items/im/stock_im_1.jpg)

The short answer is __Risk Management__. 

- __Risk sensitivities__: Financial models can be used to determine the risk sensitivities of various financial instruments. In the case of options, various Greeks (which we will introduce shortly) play an important role in understanding the sensitivity of the option price to various market factors such as stock price and interest rates.
- __Stress testing and scenario analysis__: Models are also used to assess worst-case scenarios and potential profits and losses during extreme events such as the 2008 financial crisis and COVID-19. In fact, most banks are federally required to conduct stress tests on their accounts using approved models and to monitor their risks accordingly.
-  __Other applications__: Models can also be used for other applications like fair value estimation of an instrument in the primary market, pricing non-liquid instruments, portfolio analysis etc. You can also run monte-carlo simulations to see if you could predict the future behaviour (Good luck with that!). 

#### Now it is time to talk about 'em  Greeks!

![Stock Picture](../items/im/stock_im_4.jpeg)

## What are Greeks ? 

- The __Greeks__ of an option are it's price sensitivities to different market conditions. They are called greeks because as customary in mathematics, objects are denoted by greek letters and the people on wall street started calling them the greeks, probably because those are the only greek letters they see in their life. 

- Mathematically, if options are priced using a model (or a function), then Greeks are given by the rate of change of these functions with respect to various inputs of this model.
Greeks have the power to help traders and investors understand and manage the risks associated with their positions.

#### Types of Greeks

Popular and most useful Greeks are: __$\Delta$, $\Gamma$ $\Theta$, $\rho$, and $\nu$__. 
- $\Delta$: Delta measures how much an option's price is expected to move with a \$1 change in the underlying asset's price. 
- $\Gamma$: Gamma reveals how stable Delta is by showing its rate of change.
- $\Theta$: Theta, also known as the "time decay," tells us how much an option's price decreases as it nears expiration.
- $\rho$: Rho indicates how much the option's price will move with a 1% change in interest rates.
- $\nu$: Vega measures an option's sensitivity to changes in volatility, and Rho indicates how much the option's price will move with a 1% change in interest rates.

Together, these Greeks provide a way to understand the risk sensitivity of a large portfolio consisting of a large collection of financial instruments. 

### A more precise definition

Consider an option (Call or Put) of a stock (for example TSLA) without paying dividends. Using some models like Black Scholes', the price of the option,$ P$, can be expressed as a function of some variables:

\$P(S, K, T, \sigma, r) $,

where:
- $S $ is the current stock price
- $ K $ is the strike price
- $ T $ is the time to expiration
- $ \sigma$ is the volatility of the stock
- $ r $ is the risk-free interest rate

Here's a table summarizing the key Greeks, along with their descriptions and definitions using partial derivatives of \( P \):

| Greek       | Short Description                                              | Greek Calculation                                      |
|-------------|----------------------------------------------------------------|-------------------------------------------------|
| Delta $\Delta$       | Sensitivity of the option price to changes in the stock price          | $\Delta = \frac{\partial P}{\partial S}$            |
| Gamma $\Gamma$       | Sensitivity of Delta to changes in the stock price                    | $\Gamma = \frac{\partial^2 P}{\partial S^2}$           |
| Theta $\Theta$      | Sensitivity of the option price to the passage of time                | $\Theta = -\frac{\partial P}{\partial T}$           |
| Vega $\nu$             | Sensitivity of the option price to changes in the volatility          | $\nu = \frac{\partial P}{\partial \sigma}$             |
| Rho $\rho$          | Sensitivity of the option price to changes in the risk-free interest rate | $\rho = \frac{\partial P}{\partial r}$             |

## How can we use the greeks ?

Now that we know the definition of greeks and lets have a look at some of their usage. 

### Hedging

__Example__: Using $\Delta$ to estimate the sensitivity of option price to stock price movement and hedging to "eliminate" delta risk. 

Suppose we buy a __TSLA__ call option with:
- **Current stock price $S$**: \$180
- **Strike price $K$**: \$190
- **Time to expiration $T$**: 1 year
- **Volatility $\sigma$**: 60% per year
- **Risk-free interest rate $r$**: 5% per year
- **Delta $\Delta$**: 0.2

**What happens if the stock price goes up by 2$**: The stock price increases from \$180 to \\$182.

We can estimate the approximate change in option price by, 

$\Delta P =  2 \times \Delta = 0.4. $

Mathematically this is coming from first order approximation of \$P(S, K, T, \sigma, r) $, around the current market conditions as follows: 


$\Delta P = P($$\color{red}S=180+2$$, K=190, T=100, \sigma=0.6, r=0.05) - P($$\color{red}S=180$$, K=190, T=100, \sigma=0.6, r=0.05)  $

= $\frac{\partial P}{\partial S} (S=180, K=190, T=100, \sigma=0.6, r=0.05) \times \delta S = 0.2 *2 = 0.4$


#### How to hedge this position ? 

__Delta Hedging__:
- Now that we know about the sensitivity of the option price to the stock price through $\Delta$, we can use this information to reduce our delta risk (the risk of losing money due to changes in the stock price).
- We simply need to buy or sell another instrument with a negative $\Delta$ value such that it cancels out the $\Delta$ of our call option, making the portfolio $\Delta$ neutral (meaning our portfolio is not sensitive to price changes in the TSLA stock anymore). This technique is called delta hedging.

__Hedging other risks__:
-  Using the similar sensitivity analysis with other Greeks, we can hedge other risks as well.
-  For example, if a trader wants to hedge the interest rate risk of their portfolio, they can buy or sell financial instruments  with interest rate risk, $\rho$, in the opposite direction (I am looking at you,  __Interest Rate Swaps!__). 

### Word of caution about using Greeks for estimating risk and hedging

![Stock Picture](../items/im/stock_im_5.jpg)

__When you use Greeks to analyze and hedge your risks, you are making approximations at multiple levels__  

- __Inaccurate model__: All greeks are calculated using a base model like Black Schole's model which is imperfect to start with.
-  __There is no perfect hedge__: Even if you have a perfect model, depending on the order of the partial derivatives you end up using for your risk calculations, you may be only accounting for first-order terms. At the end of the day, hedging can be done only using first order risk. Nobody in the market sells products that is directly intended to hedge second order risks. 

### Understanding first-order approximations in risk calculations: How hedges can fall off !

Let's dive into the math of risk approximation with an example using an option pricing function $ P(S, T, \sigma, r) $.

#### Full Taylor Series Expansion

To find the change in the pricing function $ P $ when $ S $, $ T $, $ \sigma $, and $ r $ change by $ \delta_S $, $ \delta_T $, $ \delta_\sigma $, and $ \delta_r $ respectively, we use a Taylor series expansion around the point $(S, T, \sigma, r)$.

The full Taylor series expansion is:

$$
P(S + \delta_S, T + \delta_T, \sigma + \delta_\sigma, r + \delta_r) - P(S, T, \sigma, r) 
$$
$$
= \frac{\partial P}{\partial S} \delta_S + \frac{\partial P}{\partial T} \delta_T + \frac{\partial P}{\partial \sigma} \delta_\sigma + \frac{\partial P}{\partial r} \delta_r 
$$
$$
+ \frac{1}{2} \left( \frac{\partial^2 P}{\partial S^2} \delta_S^2 + \frac{\partial^2 P}{\partial T^2} \delta_T^2 + \frac{\partial^2 P}{\partial \sigma^2} \delta_\sigma^2 + \frac{\partial^2 P}{\partial r^2} \delta_r^2 \right) 
$$
$$
+ \left( \frac{\partial^2 P}{\partial S \partial T} \delta_S \delta_T + \frac{\partial^2 P}{\partial S \partial \sigma} \delta_S \delta_\sigma + \frac{\partial^2 P}{\partial S \partial r} \delta_S \delta_r + \frac{\partial^2 P}{\partial T \partial \sigma} \delta_T \delta_\sigma + \frac{\partial^2 P}{\partial T \partial r} \delta_T \delta_r + \frac{\partial^2 P}{\partial \sigma \partial r} \delta_\sigma \delta_r \right)
$$
$$
+ \text{Higher order terms} 
$$

__First-Order Approximation__:

Using only the first-order terms, the approximation is:

$$ 
P(S + \delta_S, T + \delta_T, \sigma + \delta_\sigma, r + \delta_r) - P(S, T, \sigma, r) \approx \frac{\partial P}{\partial S} \delta_S + \frac{\partial P}{\partial T} \delta_T + \frac{\partial P}{\partial \sigma} \delta_\sigma + \frac{\partial P}{\partial r} \delta_r 
$$

__Impact of missing higher-order terms__:

If any of any of the market movements, given by $ \delta_S $, $ \delta_T $, $ \delta_\sigma $, or $ \delta_r $ are large, the higher-order terms become significant. The error introduced by ignoring these terms can be substantial and our hedges fall out of sync. For example, for the example discussed above where we created a delta neutral portfolio buy buying a TSLA call option and shorting some TSLA stocks to cancel the delta risk. If the price of the TSLA option moves by a big number, say 10, then $\delta_S $ is large, and  $ \delta_S^2 =100$ is even larger, and the contribution of the second order terms to the total change in $P $ can be significant. Depending upon the positions we took, we could be very be in trouble even though we had a completely delta hedged portfolio!. 


```python

```
