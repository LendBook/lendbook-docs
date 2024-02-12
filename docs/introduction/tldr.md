
<h2 style="font-weight: bold;">Too Long; Didn't Read</h2>

If you don't have time to read everything, or if you want to get an overview before digging in the documentation, here are the main things you need to know :

1. **LendBook is a Lending Limit Order Book.** Each market is isolated and collateral assets are not lent out to borrowers

* **There are 3 types of market participants**:
      * **Lenders** post limit orders at specified prices which can be borrowed.
      * **Borrowers** deposit collateral as limit orders in order to borrow assets posted by lenders.
      * **Takers** can trade assets when market price reaches the limit price of orders they want to take. No fees applied. 

* **Orders can only be posted within a restricted range of limit prices which are called pool-of-orders.** Orders are grouped into pools to avoid diluting lending liquidity across all possible prices. Each pool-of-orders has an assigned limit price. The pools-of-orders architecture allows lenders to withdraw anytime as long as all there is non-borrowed liquidity in the pool.

* **The interest rate is calculated per pool. It depends on the pool's utilization rate.** Borrowers who borrow from a pool pay interest rates to the lenders in that same pool.

* **The market price is given by an oracle. When market price reaches the limit price of a pool-of-orders, borrowing positions from that pool are liquidated.** Lenders receive the borrowers' collateral plus the interest rate and liquidation fee.

* **There are 2 types of liquidations** :
      * **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated;
      * **Interest-based liquidation** when a collateralized position becomes under-collateralized due to the accumulation of interest rate. In case of liquidation, borrowers need to pay a small liquidation fee.

* **LendBook offers users multiple benefits:**
    * **No bad debt** — Borrowing positions cannot go under-collateralized
    * **No off-chain risk management** — risk management is on-chain and market-driven
    * **Simple debt management** — To avoid liquidation, the borrower simply needs to follow the market price and remember at what limit price he has placed his loan.
    * **Low liquidation cost** — liquidation fee = 4% for volatile assets (e.i. ETH/USDC market)
    * **High Loan-To-Value** — MaxLTV = 94% for volatile assets (e.i. ETH/USDC market)
    * **High leverage** — Max Theoretical Leverage is x16 for volatile assets (e.i. ETH/USDC market)
    * **Near zero governance** — on the path to full decentralization.










<!-- 
It makes a huge difference compared to existing lending protocols. This new financial primitive offers users multiple benefits: 

* **stop loss orders with guaranteed stop price**
* **low liquidation penalty**
* **high loan-to-value and leverage**
* **interest-bearing limit orders**

The protocol is immune to the risk of bad debt, there is no off-chain risk management.
-->
