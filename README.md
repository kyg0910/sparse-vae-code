# Sparse VAE

This repository contains the code for the paper "Identifiable Deep Generative Models via Sparse Decoding" [(arXiv)](https://arxiv.org/abs/2110.10804).

## Data Sources

The datasets used in this paper were downloaded from the following sites.

- MovieLens 25M (Harper and Konstan, 2015): https://grouplens.org/datasets/movielens/25m/

- PeerRead (Kang et al., 2018): https://github.com/allenai/PeerRead

- Zeisel (Zeisel et al., 2015): https://storage.googleapis.com/linnarsson-lab-www-blobs/blobs/cortex/expression_mRNA_17-Aug-2014.txt

## Requirements

The code has been tested on Python 3.7.6 with the following packages:
```bash
bottleneck==1.3.2 
conda==4.9.2
nltk==3.6.1 
numpy==1.20.2
pandas==1.2.4
scikit-learn==0.24.1
scipy==1.6.2
torch==1.8.1
```

The R functions have been tested on R version 4.0.2 with the following packages:
```bash
preprocessCore
ggplot2
reshape2
ggpubr
Rtsne
```

## Instructions

You can run the Sparse VAE on the simulated dataset with:
```bash
python -m experiment.run_experiment --model=spikeslab
```

For a description of the list of flags and their default values, run:
```bash
python -m experiment.run_experiment --help
```

## References

-  D. Kang, W. Ammar, B. Dalvi, M. van Zuylen, S. Kohlmeier, E. Hovy, and R. Schwartz. A dataset of peer reviews (PeerRead): Collection, insights and NLP applications. arXiv preprint arXiv:1804.09635, 2018
- F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19. https://doi.org/10.1145/2827872
- Zeisel, A., Muñoz-Manchado, A.B., Codeluppi, S., Lönnerberg, P., La Manno, G., Juréus, A., Marques, S., Munguba, H., He, L., Betsholtz, C. and Rolny, C., 2015. Cell types in the mouse cortex and hippocampus revealed by single-cell RNA-seq. Science, 347(6226), pp.1138-1142.


## Added by YK (Default values)

  --batch_size: batch size to use in training.
    (default: '100')
    (an integer)
    
  --beta_vae: beta-vae parameter.
    (default: '1.0')
    (a number)
    
  --data: name of setting to use from [simulated, peerread_small,
    movielens_small, zeisel]
    (default: 'simulated')
    
  --datafile: path to file if using raw data files.
    (default: '')
    
  --epochs: number of epochs for training.
    (default: '100')
    (an integer)
    
  --hidden_dim: dimension of hidden layers.
    (default: '300')
    (an integer)
    
  --[no]is_discrete: flag that indicates if observed data is continuous or
    discrete.
    (default: 'false')
    
  --lambda0: lambda0 regularization parameter for spikeslab.
    (default: '10.0')
    (a number)
    
  --lambda1: lambda1 regularization parameter for spikeslab.
    (default: '1.0')
    (a number)
    
  --[no]load: flag to load saved model.
    (default: 'false')
    
  --loss_type: loss to use from [mse, binary, categorical]
    (default: 'mse')
    
  --lr: learning rate for Adam
    (default: '0.01')
    (a number)
    
  --model: variant of VAE model to fit from [spikeslab, vae, vsc]
    (default: 'spikeslab')
    
  --model_file: file where model is saved.
    (default: 'svae_simulated')
    
  --n_components: number of latent components to use.
    (default: '5')
    (an integer)
    
  --num_folds: number of splits.
    (default: '2')
    (an integer)
    
  --outdir: directory to which to write outputs.
    (default: '../out/')
    
  --[no]pretrained: flag to use pretrained topics or not.
    (default: 'false')
    
  --pretraining_file: path to pretrained data.
    (default: '')
    
  --procfile: path to file for processed data.
    (default: '')
    
  --[no]row_norm: flag to row normalize W or not in spike slab model.
    (default: 'false')
    
  --[no]save: flag to save model.
    (default: 'false')
    
  --split: split to run experiment.
    (default: '0')
    (an integer)
