In LendBook, **there are two types of liquidation:**

* **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated

* **Interest-based liquidation** when a collateralized position become under-collateralized due to the accumulation of interest rate (mainly for long-term borrowings)



<h2 style="font-weight: bold;">Price-based liquidation</h2>

In LendBook, when the price crosses a limit price, the closing of a borrowing position does not rely on the active monitoring of liquidators but on that of takers. Takers, by taking the non-borrowed part of the assets, initiate the internal transfer from the borrowers to the lenders.

**Borrowers pay liquidation fees to lenders (fee rate is between 0.5 and 5%, depending on asset volatility).** The goal is to compensate lenders for receiving the collateral and give borrowers incentives to repay their loan before liquidation. 

Since lenders agree to receive the collateral as a payment (plus liquidation fees), the protocol does not need to incentivize bots to liquidate unhealthy positions on time. 


| Asset tier      | Liquidation fees                          | Examples |
| :----------: | :-----------------------------------:  | :--------: |
| Pegged assets       | 0.5%  | *DAI/USDC, wstETH/ETH* |
| Correlated assets     | 1% | *USDM/USDC, FRAX/USDC* |
| Volatile assets    | 3% | *ETH/USDC, WBTC/ETH* |
| Long-tail assets (in V2)    | 5% | *MKR/ETH, LINK/ETH*|


<h2 style="font-weight: bold;">Interest-based liquidation</h2>

As time goes on, the borrowed amount increases due to the accumulation of interest rate. A collateralized position can become under-collateralized and subject to liquidation.

In order to manage this liquidation, **for all borrowers, their Excess Collateral (EC) is calculated**. The excess collateral represents the quantity of asset deposited as collateral by the borrower but not yet required as collateral for borrower's various loans. It is calculated per borrower and includes all borrowing positions. It is not calculated for each borrowing position independently. Also the excess collateral is specific to each market.

Excess collateral can decrease depending on two aspects:

- interest rate continue to accumulate, and excess collateral is gradually reduced
- the borrower opens up a new borrowing position, and excess collateral is reduced by the amount of required collateral needed for this position.


??? info "Calcul of the Excess Collateral (EC)"
    We need to define some variables :

    * **Total Collateral (TC) :** The sum of all the assets deposited in limit orders as collateral by the borrower
    * **Required Collateral (RC) :** The sum of collateral needed to repay all the borrowing positions, pay interest fees, and pay a possible price-based liquidation fee
    * **Liquidation Loan-To-Value (LLTV) :** In order to liquidate the position before there really isn't enough collateral left, we add this variable. This provides a safety zone to protect lenders from borrowers’ insolvency due to a growing debt burden. 

    So we have :

    <center>
    $EC=TC-\dfrac{RC}{LLTV}$
    </center>


**Excess collateral must always be positive. Otherwise, liquidation is at the initiative of external actors who receive in exchange a liquidation incentive (3%).** 

<!-- TODO à ameliorer. Decrire ce que reçoit le lender, le borrower et l'external actor, et faire un exemple -->



??? note "Example"
    In the ETH/USDC market, let's suppose that market price is equal to 2110 :

    1. Bob deposited 3 ETH as collateral as sell order in the Pool~2200~.
    2. Bob borrowed 5100 USDC from the Pool~1818~ at limit price 1818. 
    3. As time goes on, the collateral needed for his position is now up to 5454 USDC. This collateral represents 3 ETH (=5454/1818) meaning that Bob's Excess collateral is now equal to zero. Bob's borrowing position needs to be liquidated.
    4. Market price is still 2110. Carol takes Bob's position. So she repays Bob's debt to the Pool~1818~ (5454 USDC). In exchange she gets 2.5848 ETH (=5454/2110) plus a 3% bonus of 0.078 ETH (=2.5848*0.03). So in total Carol trades 5454 USDC for 2.6628 ETH at market price 2110. 
    5. Bob's remaining order in Pool~2200~ is equal to 0.3372 ETH (=3-2.6628). Here Bob had to pay a liquidation fee of 0.078 ETH.


