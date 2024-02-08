
<h2 style="font-weight: bold;">Stop loss</h2>

A stop-loss order allows traders to close long positions by selling the assets or a short position by buying the assets. In LendBook, users open stop-loss orders by borrowing assets from limit orders. The stop price in case of price decrease (or increase) is the limit price of the buy (sell) order from which they borrow.



???+ note "Example"
    
    In the ETH/USDC market, let's suppose the market price is 2110.

    Bob deposits 2 ETH as a sell order in the Pool~2200~ at limit price 2200.

    Bob borrows the maximum amount from Pool~2000~ at a limit price of 2000 : He can borrow up to 3920 USDC (=0.98×2×2000). 
    
    If the market price decreases to 2000, Bob's borrowing position is liquidated. Bob keeps the 3920 USDC and gives up his 2 ETH. This is as if he benefits from a stop loss (sell ETH when its price decreases) at the guaranteed price of 2000. His stop price is the limit price of the pool he borrowed from.

    (Interest rates are not included in this example)

In traditional or crypto finance, once the stop price is met, the stop loss order becomes a market order and is executed at the next available price. The obtained price can be significantly less favorable than the specified price when markets move fast. Here the stop price is guaranteed by the filling of the sell order at the limit price.

<h2 style="font-weight: bold;">Take profit</h2>

By posting their collateral in the order book, borrowers can program in advance the price at which they exit their strategy, which is the limit price of their collateral order.

???+ note "Another example"
    
    In the ETH/USDC market, let's suppose the market price is 2110.

    Bob deposits 2 ETH as a sell order in the Pool~2200~ at limit price of 2200. 

    Bob borrows 3920 USDC (=0.98×2×2000) from Pool~2000~ at a limit price of 2000.

    By depositing ETH in a sell order at 2200, Bob benefits from a take-profit at the same price. 
    
    If the market price increases to 2200, Bob’s sell order is filled and his borrowing position is closed out. His 2 ETH are exchanged against 4400 USDC (=2×2200) from which 3920 are used to pay back his borrowing position. He keeps the 3920 USDC borrowed from the pool and earns a profit of 480 USDC (=4400-3920). Bob leaves with 4400 USDC.

    (Interest rates are not included in this example)

Setting in advance an exit price is an integral part of risk management in case of leveraged position.

???+ note "Another example"

    In the ETH/USDC market, let's suppose the market price is 2110.

    Bob deposits 2 ETH as collateral in as a sell order in the Pool~2200~ at limit price of 2200. 

    Bob borrows 3920 USDC (=0.98×2×2000) from Pool~2000~ at a limit price of 2000.

    Bob swaps his loan for 1.86 ETH (=3920/2110) at market price 2110 and add this amount as collateral in his sell order in the Pool~2200~.
    
    Bob then borrows 3646 USDC (=0.98×1.86×2000) from Pool~2000~ at a limit price of 2000. 
    
    Bob swaps his loan for 1.73 ETH (=3646/2110) at market price 2110 and add this amount as collateral in his sell order in the Pool~2200~.

    If the market price increases 2200, his sell orders is filled and his borrowing positions are closed out. His 5.59 ETH (=2+1.86+1.73) are exchanged against 12298 USDC (=5.59×2200) from which 7566 (=3920+3646) are used to pay back his borrowing positions. Bob’s leveraged profit is 332 USDC (=12298-7566-2×2200).  Bob leaves with 4732 USDC.
    
    (Interest rates are not included in this example)

The combination of an order book with a lending protocol unlocks a rich set of strategies that borrowers can fine-tune and program in advance. They can spread their position over several collateral orders and pools with different limit prices. This way, their borrowing can be progressively reduced as the price reaches well-specified thresholds. 

For example, a Borrower can borrow from various pools in order to be liquidated gradually at various limit prices. Also, a borrower can deposit his collateral in various pools in order to gradually take profit.