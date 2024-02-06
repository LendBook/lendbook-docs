## **How do I borrow?**

To borrow an asset, you need to choose the asset you wish to use as collateral and go to the corresponding market. There is then a two-step process:


1. Before borrowing, you need to deposit some collateral by posting a limit order on the other side of the order book. 

    Depending on your strategy, you can :

    * post a limit order in a pool-of-orders which is far far away from the market price. This means you don't want the order linked to your collateral to be filled. This is the most similar strategy to the one you're used to when depositing collateral in other lending protocols.
    * post a limit order in a pool-of-orders close to the market price. If market price goes up, your order will be filled and it means that you've set an exit price (Check out the [Take profit section](../../use-cases/take-profit) for more details).
    * post multiple limit orders in various pool-of-orders. If you want to progressively take profit.

2. You can now borrow from a pool-of-orders. Each pool has its own limit price. You choose the pool you want, depending on the price at which you want to be liquidated. Also each pool has its own interest rate, which depends on its utilization ratio.

    Depending on your strategy, you can borrow from a pool-of-orders close to or far away from the market price (Check out the [Stop Loss section](../../use-cases/stop-loss) for more details).

??? note "Example"
    Bob wants to borrow USDC.
    He choose to use ETH as collateral. So he goes to the ETH/USDC market.

    Let's suppose market price is 2110.

    Bob deposits his collateral as a sell order in the Pool~9190~ at limit price 9190 (This means he doesn't want his order to be filled soon :wink: ).

    Then Bob borrows from Pool~1818~. Positions borrowed from this will be liquidated if the market price reaches 1818.


## **How much I can borrow?**


## **What asset do I need to repay?**


## **How much would I pay in interest?**


## **When do I need to pay back the loan?**


## **How do I payback the loan?**


## **How do I avoid liquidation?**
