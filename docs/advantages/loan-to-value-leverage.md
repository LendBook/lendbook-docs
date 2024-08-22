**When a pool-of-orders is close to the market price, maxLTV tends towards aLTV.**

For each type of asset pair, we can calculate the interval of maxLTV for the pool-of-orders closest to the market price :


| Asset tier                | aLTV  | pool step  |  MaxLTV for pool closest to market price  |Examples |
| :----------:              | :----:| :----:| :----:| :--------: |
| Pegged assets             | 98.5% | 0.1% | **from 98.4% to 98.5%** | *DAI/USDC, wstETH/ETH* |
| Correlated assets         | 96%   | 1% | **from 95% to 96%**  | *USDM/USDC, FRAX/USDC* |
| Volatile assets           | 94%   | 10% | **from 84.6% to 94%**  | *ETH/USDC, WBTC/ETH* |
| Long-tail assets <br>(in V2)  | 92%   | 15% | **from 78.2% to 92%**  | *MKR/ETH, LINK/ETH*|



[:octicons-info-16: More information on Loan-To-Value](../../how-it-works/max-loan-to-value){target=_blank, .md-button }

LendBook enables leverage factors a magnitude higher than what other lending protocols offer. 

To understand how, let’s examine how traders leverage their position. As in other protocols, they can borrow Y and swap them to amplify their position in X, or they can borrow X and swap them to short X. Borrowers can easily do loops of borrowing and swapping to amplify their leverage. **High LTV translates into high leverage.** Abstracting from gas and swap costs, the n-loop maximum leverage factor is:

<center>
$1+LTV+LTV^2+...+LTV^n$
</center>

Assuming borrowers could infinitely loop at the same limit price, their maximum leverage would be :

<center>
$\dfrac{1}{1-maxLTV}$
</center>

As the limit price gets closer to the market price, the max LTV tends to aLTV. We can then calculate the theoretical maximum leverage for each type of asset pair :



| Asset tier                | MaxLTV  | Theoretical Max leverage  |Examples |
| :----------:              | :----:| :----:| :--------: |
| Pegged assets             | 98.5% | x66 |  *DAI/USDC, wstETH/ETH* |
| Correlated assets         | 96%   | x25 |  *USDM/USDC, FRAX/USDC* |
| Volatile assets           | 94%   | x16 |  *ETH/USDC, WBTC/ETH* |
| Long-tail assets <br>(in V2)  | 92%   | x12 |  *MKR/ETH, LINK/ETH*|
