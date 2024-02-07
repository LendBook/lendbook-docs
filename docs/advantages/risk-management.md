
<h2 style="font-weight: bold;">No bad debt</h2>

A major implication of borrowing assets from limit orders is the dramatic simplification and high safety of the liquidation process. **Borrowing positions cannot go under-collateralized even in case of strong and rapid price action, gas fee spike, or blockchain congestion/downtime.** 

While the risk of rapid price variation persists, it is borne by the maker of the limit order, creating an opportunity cost for them. Although this cost is inherent in all limit order books, in LendBook, lenders are compensated through an interest rate and liquidation fees.


The fact that lending pools stay well collateralized under any market conditions brings many benefits at the UX and governance levels. In particular, **there is no need for supervision by third party, funding a safety module, liquidation costs, or borrowing restrictions such as supply caps, borrowing caps and low loan-to-value.**


<h2 style="font-weight: bold;">No off-chain risk management</h2>

In most of lending protocols, risk management is off-chain and rely on DAO and/or third-parties.  **In LendBook, the risk management is on-chain and market-driven.**


###  **Implication: How high-volatility assets are managed in LendBook vs other protocols ?**
* **In protocols which use off-chain management**,
    DAOs and risk experts typically set lower collateral ratios in high volatility pools to give liquidators enough time to close risky positions and prevent the creation of bad debt in case of price fall.

* **In LendBook**,
    lenders handle the risk of volatile assets by migrating their capital to limit prices far enough from market price to reduce the risk of their assets being converted at an unfavorable rate. Liquidity migh be scarcer at limit prices closer to market price which drives the corresponding pools’ interest rate up and rewards lenders for the additional risk they take.

    By borrowing in pool-of-orders far from current price, borrowers benefit from lower LTV as in other lending protocols. The difference is that the lower LTV is not predetermined by an off-chain decision but the result of market forces and users’ decision.

