
<!-- <h2 style="font-weight: bold;">Introduction</h2> -->

<!-- LendBook protocol has been developed to **solve two major problems** associated with lending protocols:

* the risk management for lenders
* the debt management for borrowers -->

LendBook is a **Lending Limit Order Book**. It's the fusion of a limit order book and a lending protocol. LendBook is a non-custodial and permissionless **lending protocol that enables users to borrow limit orders’ assets**. 


LendBook was designed to be **the most robust protocol** for supplying, borrowing, and achieving **the highest leverage** in the market.

<!-- **Even if LendBook is an innovative lending protocol, it's easy to grasp**. 
This documentation is intended to explain in simple terms all the concepts behind this protocol and all the possibilities offered by LendBook to its users.

<h2 style="font-weight: bold;">What is a LendBook ?</h2> -->


<!-- <figure markdown>
  ![Image title](images/meme_panda.png){ width="400" }
</figure> -->



??? info "What is a limit order book?"
    A limit order book is a list that shows all buy and sell orders for assets like cryptocurrencies (e.g. USDC and ETH). People place orders to buy or sell at specific prices, and these orders are displayed in the list. The highest buyer's price and lowest seller's price are at the top of the list. When a buyer and seller agree on a price, a trade happens, updating the order book. It's a dynamic marketplace, showing asset supply and demand at various price levels.

??? info "What is a lending protocol?"
    In decentralized finance, with a lending protocol, you can lend or borrow money using cryptocurrencies. If you have extra cryptocurrency, you can lend it, and if you need money, you can borrow it. How much you can borrow depends on the amount of cryptocurrency you provide as collateral. Smart contracts on blockchain manage the loans, and borrowers pay interest to lenders.  It's a way to earn interest on your crypto or get a loan without involving centralised financial institutions.


<h2 style="font-weight: bold;">Main Logic</h2>

Users can lend and borrow limit orders' assets :

* Lenders post buy orders within a restricted set of limit prices. These orders can be borrowed.
* Borrowers deposit collateral to borrow assets from a pool of buy orders.
* Liquidation occurs when the market price crosses the limit price. Lenders receive collateral from borrowers.


<figure markdown>
  ![Image title](images/how-it-works-pool-B.png){ align="left" , width="80%" }
  <figcaption> <u>An example :</u> (1) Alice deposits some USDC as a buy order at price 3000 USDC. (2) Bob deposits some ETH as collateral. (3) With this ETH as collateral, he can then borrow USDC from the pool of buy orders.</figcaption>
</figure>

