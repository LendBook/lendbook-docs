
[:octicons-info-16: More information on Loan-To-Value](../../how-it-works/max-loan-to-value){target=_blank, .md-button }

LendBook offers higher leverage than other lending protocols. 

To understand how, let’s examine how borrowers leverage their position. As in other protocols, they can borrow Y and swap them to amplify their position in X, or they can borrow X and swap them to short X. Borrowers can easily do loops of borrowing and swapping to amplify their leverage. **High LTV translates into high leverage.** Abstracting from gas and swap costs, the n-loop maximum leverage factor is:

<center>
$1+LTV+LTV^2+...+LTV^n$
</center>

Assuming borrowers could infinitely loop at the same limit price, their maximum leverage would be :

<center>
$\dfrac{1}{1-maxLTV}$
</center>

As the limit price gets closer to the market price, the maxLTV tends towards LLTV (Liquidation Loan-To-Value). **We can then calculate the theoretical maximum leverage for each type of asset pair :**



| Asset tier                | LLTV  | pool step  |  MaxLTV for pool closest to market price  | Theoretical Max leverage  |Examples |
| :----------:              | :----:| :----:| :----:| :--------: | :--------: |
| Pegged assets             | 99% | 0.03% | **from 98.9% to 99%** | x100 | *DAI/USDC, wstETH/ETH* |
| Correlated assets         | 98%   | 1% | **from 97% to 98%**  | x50 | *USDM/USDC, FRAX/USDC* |
| Volatile assets           | 96%   | 10% | **from 87.3% to 96%**  | x25 | *ETH/USDC, WBTC/ETH* |
| Long-tail assets <br>(in V2)  | 94%   | 15% | **from 81.7% to 94%**  | x16 | *MKR/ETH, LINK/ETH*|

