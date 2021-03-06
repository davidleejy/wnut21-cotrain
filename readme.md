# Co-Training for Commit Classification

## Overview

This is the official repository for the paper [Co-Training for Commit Classification published at the Seventh Workshop on Noisy User-generated Text (W-NUT 2021)](https://aclanthology.org/2021.wnut-1.43/). This repository contains the dataset used in the paper. `poster.pdf` is our poster.

The 900Repo dataset is contained in `negative+CC-900repos.csv` and `positive+CC-900repos.csv`. These can be used directly to replicate experiments.

## Constructing 900Repo Dataset

To replicate the construction of the 900Repo dataset, follow these steps.

1. Get dataset by [RA21]. `$ git clone https://github.com/TQRG/security-patches-dataset.git` Set git head to commit we used: `$ git reset --hard ebcbfc8cdc1e1f3d1dfb97b6c5e75804b20c079f`.

2. At this commit, the `security-patches-dataset` repository contains about 8,000 positive and 110,000 negative samples (see `security-patches-dataset/dataset/negative.csv` and `positive.csv`). However, code diffs are not provided -- we'll have to download these ourselves.

3. Run `data-get.ipynb`. This notebook (a) downloads code diffs for the commit samples via the Github API, and (b) randomly selects a handful of negative commit samples out of the 110,000 provided by [RA21]. The .csv files saved will be similar to `negative+CC-900repos.csv` and `positive+CC-900repos.csv`.

## Cite

If our work has been useful, we would be grateful if you would consider citing

```
@inproceedings{lee2021co,
  title={Co-training for Commit Classification},
  author={Lee, Jian Yi David and Chieu, Hai Leong},
  booktitle={Proceedings of the Seventh Workshop on Noisy User-generated Text (W-NUT 2021)},
  pages={389--395},
  year={2021}
}
```


## References

[RA21] Sofia Oliveira Reis and Rui Abreu. 2021. A ground-truth dataset of real security patches.