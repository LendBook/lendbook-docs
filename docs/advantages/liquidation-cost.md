<!-- 
We say low so :

* liquidation fee of 4% for price-based liquidation
* liquidation fee of 3% for interest-based liquidation
-->

In most of lending protocols, the prevalent liquidation mechanism allows a liquidator to repay a fraction of the borrower’s debt and acquire its collateral at a discount. 

In LendBook, when the price crosses a limit price, the closing of a borrowing position does not rely on the active monitoring of liquidators but on that of takers. Takers, by taking the non-borrowed part of the assets, initiate the internal transfer from the borrowers to the lenders. 

Since lenders agree to receive the collateral as a payment, the protocol does not need to incentivize bots to liquidate unhealthy positions on time. **The borrower only pays small liquidation fee rate, with the goal to compensate lenders for receiving the collateral and give borrowers incentives to repay their loan before liquidation.**