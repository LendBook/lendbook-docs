In LendBook, **there are two types of liquidations :**

* **Price-based liquidation** when the market price reaches the pool limit price, borrowing positions are liquidated

* **Interest-based liquidation** when a collateralized position becomes under-collateralized due to the accumulation of interest rate (mainly for long-term borrowings)



<h2 style="font-weight: bold;">Price-based liquidation</h2>

In LendBook, when the price crosses a limit price, the closing of a borrowing position does not rely on the active monitoring of liquidators but on that of takers. Takers, by taking the non-borrowed part of the assets, initiate the internal transfer from the borrowers to the lenders.

Since lenders agree to receive the collateral as a payment, the protocol does not need to incentivize bots to liquidate unhealthy positions on time. 

**The borrower pays liquidation fee rate to lenders (between 1 and 5%, to be decided).** The goal is to compensate lenders for receiving the collateral and give borrowers incentives to repay their loan before liquidation. 

<h2 style="font-weight: bold;">Interest-based liquidation</h2>

As time goes on, the borrowed amount increases due to the compound interest rate. A collateralized position can become under-collateralized and subject to liquidation.


??? info "Equation of the Interest Rate curve"
    The IR curve is :
    <center>
    $\begin{cases}
        if\ \ UR \leq UR^*\ ;\ IR = \alpha+\beta \dfrac{UR}{UR^*} \\ 
        if\ \ UR \gt UR^*\ ;\ IR = \alpha+\beta +\gamma \dfrac{UR-UR^*}{1-UR^*}
        \end{cases}$
    </center>
    <center>
    $with\ α,\ β\ and\ γ\ three\ positive\ parameters\ (γ>β)$
    </center>

