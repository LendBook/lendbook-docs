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

## FIXME

- [ ] In dark mode, when the user is on a specific page, the name of the page in the sidebar (navigation) is using md-primary-fg-color which is too dark. Need to change the path for this specific color in order to use another color.
