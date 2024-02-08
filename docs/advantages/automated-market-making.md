
Orders which assets are filled are automatically replaced in the order book ([Main Rule n°7](../../how-it-works/liquidation){target=_blank}). Lenders choose at which limit price their assets are replaced. By default, their liquidity is posted as a limit order in the pool closest to the market price on the other side of order book.


!!! note "Example with pools-of-orders spaced with a 10% step: "
    
    In the ETH/USDC market, let's suppose market price is 2110. 

    Alice deposits 6000 in a buy order which limit price is 2000. Once the market price reaches 2000 and the order is filled, the protocol relocates the 3 ETH in the nearer pool of sell orders which is Pool~2200~ with a limit price of 2200.

This feature allows lenders (or protocols built on LendBook) to program in advance at which price they are willing to sell back the assets after a buy, or buy back them after a sell. The default strategy with automatic replacing in the nearest opposite pool is similar to what liquidity providers experience in Uniswap-type Automated Market Makers (AMMs), except that instead of earning a fee rate, lenders earn the spread on top of the interest rate paid by borrowers.


!!! note "Example (continued) "
    
    Now, the market price is 2000, and Alice has a sell order of 3 ETH deposited in the Pool~2200~.

    Let's suppose the market price goes up and crosses 2200. 

    Alice’s sell order is taken for 6600 USDC (=3×2200). Her net profit is 600 USDC (=6600-6000). Her profit rate is 10% (=600/6000).


From there, two types of lending strategies are made possible :

1.  Lenders act as market makers and post limit orders closed to current price. They constantly (and automatically) replace their filled order on the other side of the market to earn the spread in addition to the lending return rate. 

2. Lenders follow single-sided Aave-style strategies. They earn a return for their deposited assets but avoid conversion by posting limit orders far from current price and/or by withdrawing their funds before their orders are filled.