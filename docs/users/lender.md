
<h2 style="font-weight: bold;">How do I supply?</h2>

First, you need to choose the quote asset to supply and the market in which you want to supply. For example, you might want to supply USDC in the ETH/USDC market.

Then, depending on your strategy, **you can choose in which pool-of-orders you want to post your quote asset as a limit order**. Indeed, you can deposit in a pool-of-orders close to or far away from the market price.

<h2 style="font-weight: bold;">How much will I earn?</h2>

There are two sources of earnings :

* [**Interest rates**](../../how-it-works/interest-rates){target=_blank} - In each pool, lenders share the interests paid by borrowers. The interest rate you earn depends on the utilization rate of the pool you deposited in. The interest rate can fluctuate over time.
* [**liquidation fees**](../../how-it-works/liquidation){target=_blank} - You earn a liquidation fee when your order is filled if there are borrowing positions that have been liquidated


<h2 style="font-weight: bold;">What happens when my limit order is filled?</h2>

When market price reaches the limit price of the pool, takers can trade part of assets which are in that pool. The trades made by takers will liquidate the borrowing positions in that pool. 

**When your limit order is filled, you will receive the base asset.** Although the origin of the base asset does not affect the lender, here are the two possible origins of the base asset :

* the non-borrowable liquidity inside your pool was taken by takers, so part of base assets is coming from takers
* borrowing positions were liquidated in your pool, so the other part of base assets is the collateral of the borrowers

**When your order is filled**, and there are borrowing positions that have been liquidated, **lenders from the pool receive and share liquidation fees paid by the borrowers** (in addition to the interest rates).

<h2 style="font-weight: bold;">I want to earn interest but I want to keep my asset at the end. What should I do ?</h2>

You have supplied quote asset in order to earn interest rates but you do not want your asset to be trade into the base asset. Here is what you can do :

* **you can track the market price and withdraw your supply before the market price reaches the limit price of the pool you deposited in.** Keep in mind that the utilization rate of this pool must be under 100% in order to withdraw your supply. If you wish to continue earning interest and keep your quote asset, once you have withdrawn your asset, you can deposit in a pool with a lower price limit.

* you can wait for your order to be filled. You will receive the base asset plus liquidation fees. You then go to your favorite decentralize exchange to swap back the base asset you received into the quote asset. The liquidation fees you earn should cover the price slippage you may encounter.


<h2 style="font-weight: bold;">How do I withdraw?</h2>
To withdraw you need to go to the "My positions" section, select the limit order you wish to withdraw and click on "Withdraw". Select the amount to withdraw and submit the transaction.

You would need to make sure there is enough available liquidity (not borrowed) in the pool in order to withdraw. If the utilization rate of the pool is near 100%, you would need to wait for more liquidity to enter from lenders or wait for borrowers to repay some of the borrowing positions. 

