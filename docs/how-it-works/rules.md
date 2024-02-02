
The main rules are :


1. **Limit orders can only be posted within a restricted range of limit prices.**

    As mentioned in the [pools of orders section](../pools-of-orders), limit orders can be posted within a restricted set of pools. Each pool has an assigned limit price.

    !!! note "Example"
        In the ETH/USDC market, let's suppose the current market price is 2110.
        
        Alice can deposit USDC as a buy order in the Pool~2000~ at limit price of 2000. 
        

* **Assets which serve as collateral cannot be borrowed.**

    Borrowers place limit orders as collateral in a pool in order to borrow assets posted by lenders in another pool. Collateral assets cannot be borrowed by another borrower.

    !!! note "Example"
        Alice deposits 6000 USDC in buy orders in the Pool~2000~ at limit price of 2000. 
        
        Bob deposits 2 ETH in sell orders as a collateral in the Pool~2200~. Bob can borrow 3600 USDC deposited by Alice in the Pool~2000~. 
        
        However if Carol wants to borrow ETH from Pool~2200~ , Bob's collateral cannot be borrowed by Carol.

* **When part or all assets in a pool of orders are taken, positions borrowing from the pool are automatically closed out.**

    If the market price reaches the limit price of the pool, takers can trade part or all assets which are not borrowed in that pool. The first trade automatically liquidates all the borrowing positions from the pool. Limit orders that have been borrowed are filled thanks to the collateral they receive from the borrowers.
    !!! note "Example"
        Alice’s buy order is borrowed by Bob. 
        
        When market price reaches the limit price of Pool~2000~ , a taker trades a portion of the assets that are not borrowed. This automatically closes Bob's position and Bob's collateral is transfered to Alice. 

* **Interest rates are shared between all the lenders of a pool.**
    
    Borrowers pay interest rates to all the lenders in the pool they borrow from. 
    
    Check the [interest rates section](../interest-rates) for more details.

* **Liquidated borrowers pay a small liquidation fee to lenders.**

    In the event of liquidation, liquidation fee is paid by borrowers to lenders. This liquidation fee exists to encourage borrowers to pay back their loans. Liquidation fees compensate lenders for receiving the collateral. 
    
    There are two types of liquidations : interest-based liquidation and price-based liquidation. Check the [liquidations section](../liquidation) for more details.

    !!! note "Example continued with the addition of a 1% liquidation fee (price-based liquidation)"
        When market price reaches the limit price of Pool~2000~ , a taker trades a portion of the assets that are not borrowed. This automatically closes Bob's position and Bob's collateral is transfered to Alice. 

        Bob's loan is equal to 3600 USDC, so Bob's collateral is equal to 1.8 ETH (=3600/2000 where 2000 corresponds to the pool limit price.)

        Bob’s collateral transferred to Alice is 1.8 + 1.8×0.01 = 1.818 ETH (collateral + liquidation fee). 
        
        Alice’s remaining buy order 2400 USDC (=6000-3600) is filled for 1.2 ETH (=2400/2000). 
        
        In total, Alice receives 3.018 ETH. For simplicity, interest rates are not included in this example.

* **When a borrower limit order is filled, the borrowing positions linked to this order are automatically closed out.**

    Borrowers place limit orders as collateral in a pool in order to borrow assets posted by lenders in other pools. 
    
    If the market price reaches the limit price of the pool (where borrowers' orders are), takers can trade assets which serve as collateral for the borrowers. When a limit order is filled, borrowing positions linked to this order are automatically closed out inside the other pools.
  
    The closing of the borrowing position guarantees that the type of assets serving as collateral always matches the type needed in case of liquidation. 
    
    Check the [take profit use case](../../use-cases/take-profit) for more details.


    !!! note "Example (variant)"
        Bob has deposited his collateral (2 ETH) as a sell order in the Pool~2200~. 
        
        The market price has now reached 2200, the limit price of this pool. Bob's order is filled for 4400 USDC (=2×2200).
        
        The protocol keeps 3600 USDC to close Bob's borrowing position from Alice’s buy order. Bob is then left with 800 USDC (=4400-3600). 
        
        But Bob keeps his former loan of 3600 USDC, so all in all, Bob leaves with 4400 USDC.

* **Assets whose orders have been filled are automatically placed on the opposite side of the order book.**

    When a limit order is filled, the converted assets are replaced as a new limit order on the opposite side of the order book. 
    
    The new limit price may have been specified by the lender, or, in the absence of such specification, at a default limit price. 
    
    By default, the order is placed in the pool just above or just below the current market price. Lenders can then withdraw the assets or change the limit price if they wish.

    !!! note "Example (follow up of example from rule 5)"
        When market price reaches the limit price of Pool~2000~ , Alice’s buy order is filled, and so Alice receives 3.018 ETH. 
        
        The protocol relocates the ETH in a sell order which is located by default in the Pool~2200~.

