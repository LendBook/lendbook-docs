<h2 style="font-weight: bold;">How do I borrow?</h2>

To borrow an asset, you need to choose the asset you wish to use as collateral and go to the corresponding market. For example, you might want to borrow USDC and use ETH as collateral, so you go to the ETH/USDC market.

**There is then a two-step process:**


1. Before borrowing, **you need to deposit some collateral in the protocol**. 


2. **Then you can borrow from a pool-of-orders**. Each pool has its own limit price and its own interest rate (which depends on its utilization ratio).

    Depending on your strategy, you can borrow from a pool-of-orders close to or far away from the market price. It will determine :
    
    * the maximum Loan-To-Value you can expect (Check out the [LTV section](../../advantages/loan-to-value){target=_blank} for more details)
    * and the price at which you can be liquidated (Check out the [Stop Loss section](../../use-cases/stop-loss){target=_blank} for more details).

??? note "Example"
    Bob wants to borrow USDC.
    He choose to use ETH as collateral. So he goes to the ETH/USDC market.

    Let's suppose market price is 3100.

    Bob deposits some ETH as collateral in the protocol.

    Then Bob borrows from Pool~3000~. Positions borrowed from this will be liquidated if the market price reaches 3000.


<h2 style="font-weight: bold;">How much I can borrow?</h2>

The maximum amount you can borrow **depends on the value you have supplied as collateral and the available liquidity in each pool**. 

You can not borrow assets from a pool if the utilization rate of that pool is equal to 100%. In addition you might not borrow asset if your Excess collateral is close to 0 otherwise your other borrowing positions might be subject to an interest-based liquidation (Check out the [Liquidation fees section](../../how-it-works/liquidation){target=_blank} for more details).

<h2 style="font-weight: bold;">What asset do I need to repay?</h2>

You repay your loan in the same asset you borrowed. For example, if you borrow 1 ETH you will pay back 1 ETH + interest accrued.

<h2 style="font-weight: bold;">How much would I pay in interest?</h2>

The interest rate you pay for borrowing assets may fluctuate over time. It depends on the utilization rate of the pool you borrowed from. The utilization rate is derived from the supply and demand ratio of the asset. Check out the [Interest rates section](../../how-it-works/interest-rates){target=_blank} for more details.

<h2 style="font-weight: bold;">When do I need to pay back the loan?</h2>

There is no fixed time period to pay back the loan. As long as your position is safe, you can borrow for an undefined period. However, as time passes, the accrued interest will grow, causing a decrease in your excess collateral, which could make this position liquidatable in the near future. Check out the [Liquidation fees section](../../how-it-works/liquidation){target=_blank} for more details.

<h2 style="font-weight: bold;">What happens if my Excess collateral is near zero ?</h2>

If your excess collateral is near zero, it means that you won't be able to continue paying the interest rates that accumulate over time. One of your borrowing positions will soon be liquidated if you do nothing (Check out the [Liquidation fees section](../../how-it-works/liquidation){target=_blank} for more details).

In order not to lose part (3%) of the required collateral used for the borrowing position which is about to be liquidated, you might want to :

* deposit more collateral as new limit orders
* or repay one of your borrowing positions


<h2 style="font-weight: bold;">How do I pay back the loan?</h2>

In order to repay the loan you simply go to the Borrow page and the Repay section. Select the borrowing position you want to repay, the amount to repay and confirm the transaction.

<h2 style="font-weight: bold;">How do I avoid liquidation?</h2>

As described in the [Liquidation fees section](../../how-it-works/liquidation){target=_blank}, there are two types of liquidations in LendBook :

* **Price-based liquidation** - It's when the market price reaches the pool limit price, borrowing positions are liquidated. If price-based liquidation occurs, it will cost you a liquidation fee. **To avoid this liquidation, you must repay your loan before the market price reaches the limit price of the pool you borrowed from.**

* **Interest-based liquidation** - It's when a collateralized position becomes under-collateralized due to the accumulation of interest rate. If interest-based liquidation occurs, it will cost you a liquidation penalty. **To avoid this liquidation, we advise you to repay your loan or deposit more collateral before the excess collateral reaches zero.**