# lendbook-docs
LendBook protocol documentation


## How to contribute ?

mkdocs uses python.
In order to run the website locally, please install the mkdocs-material package in a virtual env.

```
conda create --name mkdocs-env python=3.10
conda activate mkdocs-env
pip install mkdocs-material
```

then inside the folder, you can run 
```
mkdocs serve
```


Once your branch is pushed to main branch, the documentation should shortly be available at: https://LendBook.github.io/lendbook-docs/



## TODO

- [ ] Before sharing the documentation on twitter, we need to implement the social card : https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/
- [ ] Add the different spaces between pools depending of the volatility of the asset pair

## FIXME

- [ ] Fix liquidation fees section
- [ ] Create a section where we talk about LTV



Isolated markets: All lending/borrowing markets are isolated from one another, this ensures that each risks are contained within a market and participants of a market is not affected by the outcome of another.