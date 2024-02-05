In LendBook, **there are two types of liquidations :**

* **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated

* **Interest-based liquidation** when a collateralized position becomes under-collateralized due to the accumulation of interest rate (mainly for long-term borrowings)



<h2 style="font-weight: bold;">Price-based liquidation</h2>

In LendBook, when the price crosses a limit price, the closing of a borrowing position does not rely on the active monitoring of liquidators but on that of takers. Takers, by taking the non-borrowed part of the assets, initiate the internal transfer from the borrowers to the lenders.

Since lenders agree to receive the collateral as a payment, the protocol does not need to incentivize bots to liquidate unhealthy positions on time. 

**The borrower only pays small liquidation fee rate to lenders(1 or 2%, to be decided).** The goal is to compensate lenders for receiving the collateral and give borrowers incentives to repay their loan before liquidation. 

This liquidation fee is not shared between all the lenders of the pool, but only with the lenders whose limit orders have been filled (i.e. the lenders who have received the collaterals). Lenders whose orders are not filled during the first take of the first taker do not receive liquidation fees.


<h2 style="font-weight: bold;">Interest-based liquidation</h2>
