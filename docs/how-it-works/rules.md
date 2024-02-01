
The main rules are :


1. **Limit orders can only be posted within a restricted range of limit prices.**

    As mentioned in the [Pools of orders section](../pools-of-orders), limit orders can be posted within a restricted set of pools. Eeach pool has an assigned limit price.

    !!! note "Example"
        In the ETH/USDC market, Alice can deposit USDC as a buy order in the Pool~2000~ at limit price of 2000. 
        

* **Assets which serve as collateral cannot be borrowed.**


    !!! note "Example"
        In the ETH/USDC market, Alice deposits USDC in buy orders in the Pool~2000~ at limit price of 2000. 
        
        Bob deposits ETH in sell orders as a collateral in the Pool~2200~. Bob can borrow the USDC deposited by Alice in the Pool~2000~. 
        
        However if Carol wants to borrow ETH from Pool~2200~ , Bob's collateral cannot be borrowed by Carol.

* **When part or all assets in a pool of orders are taken, positions borrowing from the pool are automatically closed out.**

    TBD
    !!! note "Example"
        When market price reaches the limit price of pool 2000, Alice’s buy order is taken at 2000, Bob’s position is closed out. The collateral is transfered to Alice.

* **Liquidated borrowers pay a small liquidation fee to lenders (1 or 2%).**

    The liquidation fee and the interest rate (see infra) are the two sources of income paid by borrowers for the liquidity service offered by lenders. Liquidation fees compensate lenders for receiving the collateral.

    !!! note "Example"
        Example continued with a 1% liquidation fee: Alice’s buy order is filled for 3 ETH. Bob’s collateral transferred to Alice is 2 × 1.01 = 2.02 ETH.

* **If borrowers’ limit orders, which assets serve as collateral, are filled, their borrowing positions are closed out.**

    The closing of the borrowing position guarantees that the type of assets serving as collateral always matches the type needed in case of liquidation.

    !!! note "Example"
        Example (variant): Bob’s sell order is filled first for 2 × 2200 = 4400 USDC, of which 3800 are kept by the protocol to close his borrowing position from Alice’s buy order. Bob is left with 3800 (borrowed assets) 600 = 4400 USDC.

* **Orders which assets are taken are automatically replaced on the opposite side of the order book.**

    The converted assets are replaced at a limit price specified by the lender, or, in the absence of such specification, at a default limit price. This default is set at 10% above or below the previous limit price, depending on the nature of the order. Lenders can then change the limit price if they wish or withdraw the assets.

    !!! note "Example"
        Example (follow up): Alice’s buy order is filled for 3 ETH. The protocol relocates the ETH in a sell order which limit price is by default is 2090 (1900 + 10%).
