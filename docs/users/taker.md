
<h2 style="font-weight: bold;">Why would I want to be a taker?</h2>

Unlike common Decentralize Exchanges (DEXs), **takers do not pay any fees for swapping assets.**

Takers can swap an asset for another asset if the market price reaches the limit price of a pool-of-orders.
Takers can take all the non-borrowable liquidity in a pool.

<h2 style="font-weight: bold;">Why are there no fees for swapping assets?</h2>

Takers play an important role in LendBook. When a taker takes part of assets in a pool-of-orders, it automatically liquidates part of the borrowing positions from that same pool. So the gas of a taker's transaction is slightly higher than that of conventional swap. But this is balanced out by the fact that the taker doesn't have to pay any fees.

So in order to incentivize them to come and trade on LendBook rather than on a DEX, takers do not pay any fees for swapping assets.

<h2 style="font-weight: bold;">Who are the takers?</h2>

Takers can have different profils :

* A user who go to the "Take" section, he selects the limit order he wish to take, he select the amount to take and submit the transaction.

* A user who uses Decentralize Exchange (DEX) Aggregators. LendBook will be integrated to DEX aggregators.

* A bot who find arbitrage opportunities by becoming a taker on LendBook.

<h2 style="font-weight: bold;">What about the 3% bonus when there is an interest-based liquidation?</h2>

Good point, it means that you've read the [liquidation fees](../../how-it-works/liquidation){target=_blank} section :wink:


As time goes on, the borrowed amount of a borrower increases due to the accumulation of interest rate. A collateralized position can become under-collateralized and subject to liquidation. This type of liquidation is called interest-based liquidation.

The orders which are subject to liquidation are showed in the "Take" section. The taker can select the amount to take and submit the transaction. He will get a 3% bonus on the amount he takes.


??? note "Example"
    In the ETH/USDC market, let's suppose that market price is equal to 2110 :

    1. Bob has deposited 3 ETH as collateral as sell order in the Pool~2200~.
    2. Bob borrowed 5100 USDC from the Pool~1818~ at limit price 1818. 
    3. As time goes on, the collateral needed for this position is now up to 5454 USDC. This collateral represents 3 ETH (=5454/1818) meaning that Bob's Excess collateral is now equal to zero. Bob's borrowing position needs to be liquidated.
    4. Market price is still 2110. Carol takes Bob's position. So she repays Bob's debt to the Pool~1818~ (5454 USDC). And in exchange she gets 2.5848 ETH (=5454/2110) plus a 3% bonus of 0.078 ETH (=2.5848*0.03). So in total Carol trades 5454 USDC for 2.6628 ETH at market price 2110. 
    5. Bob's remaining order in Pool~2200~ is equal to 0.3372 ETH (=3-2.6628). Here Bob had to pay a liquidation fee of 0.078 ETH.


