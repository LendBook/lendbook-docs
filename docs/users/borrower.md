## **How do I borrow?**

To borrow an asset, you need to choose the asset you wish to use as collateral and go to the corresponding market. For example, you might want to borrow USDC and use ETH as collateral, so you go to the ETH/USDC market.

There is then a two-step process:


1. Before borrowing, you need to deposit some collateral by posting a limit order on the other side of the order book. 

    Depending on your strategy, you can :

    * post a limit order in a pool-of-orders which is far far away from the market price. This means you don't want the order linked to your collateral to be filled. This is the most similar strategy to the one you're used to when depositing collateral in other lending protocols.
    * post a limit order in a pool-of-orders close to the market price. If market price goes up, your order will be filled and it means that you've set an exit price (Check out the [Take profit section](../../use-cases/take-profit) for more details).
    * post multiple limit orders in various pool-of-orders. If you want to progressively take profit.

2. You can now borrow from a pool-of-orders. Each pool has its own limit price and its own interest rate (which depends on its utilization ratio).

    Depending on your strategy, you can borrow from a pool-of-orders close to or far away from the market price. It will determine :
    
    * the maximum Loan-To-Value you can expect (Check out the [LTV section](../../advantages/loan-to-value) for more details)
    * and the price at which you can be liquidated (Check out the [Stop Loss section](../../use-cases/stop-loss) for more details).

??? note "Example"
    Bob wants to borrow USDC.
    He choose to use ETH as collateral. So he goes to the ETH/USDC market.

    Let's suppose market price is 2110.

    Bob deposits his collateral as a sell order in the Pool~9190~ at limit price 9190 (This means he doesn't want his order to be filled soon :wink: ).

    Then Bob borrows from Pool~1818~. Positions borrowed from this will be liquidated if the market price reaches 1818.


## **How much I can borrow?**

The maximum amount you can borrow depends on the value you have supplied as collateral and the available liquidity in each pool. 

You can not borrow assets from a pool if the utilization rate of that pool is equal to 100%. In addition you might not borrow asset if your Excess collateral is close to 0 otherwise your other borrowing positions might be subject to an interest-based liquidation (Check out the [Liquidation fees section](../../how-it-works/liquidation) for more details).

## **What asset do I need to repay?**

You repay your loan in the same asset you borrowed. For example, if you borrow 1 ETH you will pay back 1 ETH + interest accrued.

## **How much would I pay in interest?**

The interest rate you pay for borrowing assets depends on the utilization rate of the pool you borrowed from. The utilization rate is derived from the supply and demand ratio of the asset. Check out the [Interest rates section](../../how-it-works/interest-rates) for more details.

## **When do I need to pay back the loan?**

There is no fixed time period to pay back the loan. As long as your position is safe, you can borrow for an undefined period. However, as time passes, the accrued interest will grow, causing a decrease in your excess collateral, which could make this position liquidatable in the near future. Check out the [Liquidation fees section](../../how-it-works/liquidation) for more details.

## **What happens if my Excess collateral is near zero ?**

If your excess collateral is near zero, it means that you won't be able to continue paying the interest rates that accumulate over time.

One of your loan positions will soon be liquidated if you do nothing (Check out the [Liquidation fees section](../../how-it-works/liquidation) for more details).

In order not to lose part (3%) of the required collateral for the borrowing position which is about to be liquidated, you might want to :
* deposit more collateral
* or pay back one of your borrowing positions


## **How do I payback the loan?**

In order to payback the loan you simply go to the Borrowings section of your dashboard and click on the repay button for the asset you borrowed and want to repay. Select the amount to pay back and confirm the transaction.

## **How do I avoid liquidation?**

As described in the [Liquidation fees section](../../how-it-works/liquidation), there are two types of liquidations in LendBook:

* Price-based liquidation : It's when the market price reaches the pool limit price, borrowing positions are liquidated. If price-based liquidation occurs, it will cost you a liquidation fee. To avoid this liquidation, you must repay your loan before the market price reaches the limit price of the pool you borrowed from.

* Interest-based liquidation : It's when a collateralized position becomes under-collateralized due to the accumulation of interest rate. If interest-based liquidation occurs, it will cost you a liquidation penalty. To avoid this liquidation, we advise you to repay your loan or deposit more collateral before the excess collateral reaches zero.