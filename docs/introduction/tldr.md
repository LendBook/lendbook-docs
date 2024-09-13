
<h2 style="font-weight: bold;">Too Long; Didn't Read</h2> 

If you want to get an overview before digging in the documentation, here are the main things you need to know :

1. **LendBook is a Lending Limit Order Book.** Each market is isolated and collateral assets are not lent out to borrowers

* **There are 3 types of market participants**:
      * **Lenders** post limit orders at specified prices which can be borrowed.
      * **Borrowers** deposit collateral in order to borrow assets posted by lenders.
      * **Takers** can   assets when the market price hits the order's limit price. No fees applied. 

* **Orders can only be posted within a restricted range of limit prices, known as pool-of-orders.** Each pool-of-orders has an assigned limit price. Orders are grouped into pools to prevent liquidity dilution, allowing lenders to withdraw anytime as long as all there is non-borrowed liquidity in the pool.

* **The interest rate is calculated per pool. It depends on the pool's utilization rate.** Borrowers who borrow from a pool pay interest rates to the lenders who have supplied the pool.

* **The market price is given by an oracle. When market price reaches the limit price of a pool-of-orders, borrowing positions from that pool are liquidated.** Lenders receive the borrowers' collateral plus the interest rate and liquidation fee.

* **There are 2 types of liquidations** :
      * **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated;
      * **Interest-based liquidation** when a collateralized position becomes under-collateralized due to the accumulation of interest rate. In case of liquidation, borrowers need to pay a small liquidation fee.

* **LendBook offers users multiple benefits:**
    * **No bad debt** — Borrowing positions cannot go under-collateralized
    * **No off-chain risk management** — Risk management is on-chain and market-driven. The risk is not managed by DAOs or opaque curators.
    * **Simple debt management** — Borrowers know the exact liquidation price in advance, not an approximation.
    * **Low liquidation cost** — Liquidation fee = 3% for volatile assets (e.i. ETH/USDC market)
    * **High Loan-To-Value** — MaxLTV = 96% for volatile assets
    * **High leverage** — Max Theoretical Leverage is x25 for volatile assets
    * **Near zero governance** — on the path to full decentralization.










<!-- 
It makes a huge difference compared to existing lending protocols. This new financial primitive offers users multiple benefits: 

* **stop loss orders with guaranteed stop price**
* **low liquidation penalty**
* **high loan-to-value and leverage**
* **interest-bearing limit orders**

The protocol is immune to the risk of bad debt, there is no off-chain risk management.
-->
