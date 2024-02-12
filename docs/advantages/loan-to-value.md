When a pool-of-orders is close to the market price, maxLTV tends towards aLTV.

For each type of asset pair, we can calculate the interval of maxLTV for the pool-of-orders closest to the market price :


| Asset tier                | aLTV  | pool step  |  maxLTV  |Examples |
| :----------:              | :----:| :----:| :----:| :--------: |
| Pegged assets             | 98.5% | 0.1% | **from 98.4% to 98.5%** | *DAI/USDC, wstETH/ETH* |
| Correlated assets         | 96%   | 1% | **from 95% to 96%**  | *USDM/USDC, FRAX/USDC* |
| Volatile assets           | 94%   | 10% | **from 84.6% to 94%**  | *ETH/USDC, WBTC/ETH* |
| Long-tail assets <br>(in V2)  | 92%   | 15% | **from 78.2% to 92%**  | *MKR/ETH, LINK/ETH*|



[:octicons-info-16: More information on Loan-To-Value](../../how-it-works/max-loan-to-value){target=_blank, .md-button }