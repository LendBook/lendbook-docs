In LendBook, **there are two types of liquidations :**

* **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated

* **Interest-based liquidation** when a collateralized position becomes under-collateralized due to the accumulation of interest rate (mainly for long-term borrowings)



<h2 style="font-weight: bold;">Price-based liquidation</h2>

In LendBook, when the price crosses a limit price, the closing of a borrowing position does not rely on the active monitoring of liquidators but on that of takers. Takers, by taking the non-borrowed part of the assets, initiate the internal transfer from the borrowers to the lenders.

**The borrower pays liquidation fee rate to lenders (between 1 and 5%, to be decided).** The goal is to compensate lenders for receiving the collateral and give borrowers incentives to repay their loan before liquidation. 

Since lenders agree to receive the collateral as a payment (plus liquidation fees), the protocol does not need to incentivize bots to liquidate unhealthy positions on time. 

<h2 style="font-weight: bold;">Interest-based liquidation</h2>

As time goes on, the borrowed amount increases due to the accumulation of interest rate. A collateralized position can become under-collateralized and subject to liquidation.

In order to manage this liquidation, **for each borrower we calculate its Excess Collateral (EC)**. The excess collateral represents the quantity of asset deposited as collateral by the borrower but not yet required as collateral for borrower's various loans. The Excess collateral is calculated per borrower and includes all borrowing positions. It is not calculated for each borrowing position independently.

Excess collateral can decrease depending on two aspects:

- interest rate continue to accumulate, and excess collateral is gradually reduced
- the borrower opens up a new borrowing position, and excess collateral is reduced by the amount of required collateral needed for this position.


**Excess collateral must always be positive.** Otherwise, liquidation is at the initiative of external actors who receive in exchange
up to a 3% bonus.

??? info "Calcul of the Excess Collateral (EC)"
    We need to define some variables :

    * **Total Collateral (TC) :** The sum of all the assets deposited in limit orders as collateral by the borrower
    * **Required Collateral (RC) :** The sum of collateral needed to repay all the borrowing positions, pay interest fees, and pay a possible price-based liquidation fee
    * **Liquidation Loan-To-Value (LLTV) :** In order to liquidate the position before there really isn't enough collateral left, we add this variable. This provides a safety zone to protect lenders from borrowers’ insolvency due to a growing debt burden. Since the interest rate is slowly increasing, the LLTV can be set close to 100% (e.i. 99%).

    So we have :

    <center>
    $EC=TC-\dfrac{RC}{LLTV}$
    </center>
