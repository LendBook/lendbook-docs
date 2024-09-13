The amount a borrower can borrow depends on the amount of collateral deposited. 
**In LendBook, the maximum Loan-To-Value (maxLTV) depends on two factors :**

* **the Liquidation LTV (LLTV)** - The LLTV is set so that borrowers are not immediately put into liquidation when they seek to borrow the maximum amount (as they will have to pay interest charges). The LLTV is calculated to take into account the fact that the borrower has to pay a liquidation fee in the event of liquidation.
* **distance of the pool's limit price to market price** - the more the borrower borrows from a pool-of-orders whose limit price is close to the market price, the greater the LTV.

So we have the maxLTV :
<center>
$maxLTV=LLTV\times  \dfrac{pool's\ limit\ price}{current\ market\ price}$
</center>

The LLTV is defined based on the type of asset pair :

| Asset tier      | LLTV                          | Examples |
| :----------: | :-----------------------------------:  | :--------: |
| Pegged assets    | 99%  | *DAI/USDC, wstETH/ETH* |
| Correlated assets     | 98% | *USDM/USDC, FRAX/USDC* |
| Volatile assets    | 96% | *ETH/USDC, WBTC/ETH* |
| Long-tail assets (in V2)    | 94% | *MKR/ETH, LINK/ETH*|



!!! note "Example - Calcul of maxLTV"
    
    In the ETH/USDC market, let's suppose the market price is 2110.
    For the ETH/USDC market, the LLTV is 96%.

    Bob deposits 2 ETH as a sell order in the Pool~2200~ at limit price of 2200. 

    Bob wants to calculate the max amount he can borrow based on the pool-of-orders he borrows from :

    * for Pool~2000~, the limit price is 2000, so the maxLTV is equal to 91% (=0.96×2000/2110). So Bob can borrow up to 3640 USDC (=2*2000*0.91) from Pool~2000~.
    * for Pool~1818~, the limit price is 1818, so the maxLTV is equal to 82.7% (=0.96×1818/2110). So Bob can borrow up to 3308 USDC (=2*1818*0.827) from Pool~1818~.


