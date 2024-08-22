
The main rules are :


1. **Limit orders can only be posted within a restricted range of limit prices.**

    As mentioned in the [pools of orders section](../pools-of-orders){target=_blank}, limit orders can be posted within a restricted set of pools. Each pool has an assigned limit price.

    !!! note "Example"
        In the ETH/USDC market, let's suppose the current market price is 3110.
        
        Alice deposits 6000 USDC as a buy order in the Pool~3000~ at limit price of 3000. 
        

* **Assets which serve as collateral cannot be borrowed.**

    Borrowers deposit collateral in the protocol. Collateral assets cannot be borrowed by another borrower.


* **When part of the assets in a pool of orders are taken, positions borrowing from the pool are closed out.**
    
    If the market price reaches the limit price of the pool, takers can trade part or all assets which are not borrowed in that pool. The trades liquidate the borrowing positions from the pool. Limit orders that have been borrowed are filled thanks to the collateral they receive from the borrowers.

    The market price is given by an oracle (Oracleless lending will be implemented in the V2 for long-tail assets).
    !!! note "Example continued"
        Bob deposits 1.5 ETH as collateral in the protocol and borrows 3600 USDC from the Pool~3000~. 
        
        When market price reaches the limit price of Pool~3000~ , a taker trades a portion of the assets that are not borrowed. This automatically closes Bob's position and Bob's collateral is transfered to Alice (and other lenders). 

* **Interest rates are shared between all the lenders of a pool.**
    
    Borrowers pay interest rates to all the lenders in the pool they borrow from. 
    
    Check the [interest rates section](../interest-rates){target=_blank} for more details.

* **Liquidated borrowers pay a small liquidation fee to lenders.**

    In the event of liquidation, liquidation fee is paid by borrowers to lenders. This liquidation fee exists to encourage borrowers to pay back their loans. Liquidation fees compensate lenders for receiving the collateral. 
    
    There are two types of liquidations : interest-based liquidation and price-based liquidation. Check the [liquidations section](../liquidation){target=_blank} for more details.

    !!! note "Example continued with the addition of a 4% liquidation fee (price-based liquidation)"
        When market price reaches the limit price of Pool~3000~ , a taker trades a portion of the assets that are not borrowed. This automatically closes Bob's position and Bob's collateral is transferred to Alice. 

        Bob's loan is equal to 3600 USDC, so Bob's collateral is equal to 1.2 ETH (=3600/3000 where 3000 corresponds to the pool limit price.)

        Bob’s collateral transferred to Alice is 1.2 + 1.2×0.04 = 1.248 ETH (collateral + liquidation fee). 
        
        Alice’s remaining buy order 2400 USDC (=6000-3600) is filled for 0.8 ETH (=2400/3000). 
        
        In total, Alice receives 2.048 ETH. For simplicity, interest rates are not included in this example.


* **Assets whose orders have been filled are automatically placed as sell orders on the opposite side of the order book.**

    When a buy order is filled, the converted assets are replaced as a new sell order on the other side of the order book. 
    
    The new limit price may have been specified by the lender, or, in the absence of such specification, at the same limit price. 
    
    By default, the order is placed in the same pool but as sell order (as it is the base asset). Lenders can then withdraw the assets or change the limit price if they wish. 

    Once the market price crosses again the limit price of this pool, the sell orders are taken and the lender gets back his quote assets. In the same way, the quote asset are then placed as buy order in the same pool. These buy orders can now be borrowed.

    !!! note "Example (follow up of example from rule 5)"
        When market price reaches the limit price of Pool~3000~ , Alice’s buy order is filled, and so Alice receives 2.048 ETH. 
        
        The protocol relocates the ETH (base asset) in a sell order which is located by default at the same limit price in the Pool~3000~ because now the market price is under 3000 USDC. 

