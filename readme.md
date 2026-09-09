# Towards Multiple Knowledge Graphs Completion: A Cross-graph Information Fusion Method

## Overview
This repository provides the benchmark datasets and the code will be made publicly available as soon as the work is published.

## Data 

**DBP-5L**:  A Public dataset from  https://github.com/stasl0217/KEnS.

**DBP-FB5**: A novel benchmark constructed for the multi-KG completion. 

Here, we illustrate the files and folders contained in each benchmark. 

- entity: Folder with the list of entities for each individual KG.
- kg: Folder with the list of KG triples for each individual KG.
- seed_alignlinks: Folder with the list of seed entity alignment pairs between two individual KGs. 
- seed_alignlinks_available: Folder with the list of available seed entity alignment pairs between two individual KGs. 
- seed_alignlinks_unavailable: Folder with the list of unavailable seed entity alignment pairs between two individual KGs. 
- ent_name_emb.npy: The textual embeddings outputed by BERT for each entity in the benchmark. 
- relations.txt: File with the list of relations in the benchnark.



## Dataset Statistics

We provide the statistics of the benchmark datasets.

| Dataset  | KGs | Entities | Relations | Triples | Alignment links |
|----------|-----|----------|-----------|---------|-----------------|
| **DBP-5L** | EL | 5,231  | 111 | 13,839  | 9,042  |
|          | JA | 11,805 | 128 | 28,774  | 16,263 |
|          | ES | 12,382 | 144 | 54,066  | 16,347 |
|          | FR | 13,176 | 178 | 49,015  | 16,877 |
|          | EN | 13,996 | 831 | 80,167  | 16,916 |
| **DBP-FB5** | F1 | 10,812 | 236 | 81,701  | 8,598  |
|          | F2 | 10,835 | 236 | 81,701  | 8,624  |
|          | F3 | 10,817 | 236 | 81,702  | 8,610  |
|          | D1 | 11,858 | 243 | 44,011  | 8,831  |
|          | D2 | 11,879 | 240 | 44,011  | 8,867  |

## Baseline Configurations

We report the main hyperparameter configurations of all baselines evaluated on the **DBP-FB5** dataset. The detailed settings are as follows.

| Method | Main Hyperparameters |
|--------|----------------------|
| **TransE** | `batch_size=1024`, `hidden_dim=256`, `learning_rate=1e-4`, `max_steps=150000`, `test_batch_size=16`, `gamma=24.0` |
| **RotatE** | `batch_size=1024`, `hidden_dim=256`, `learning_rate=1e-4`, `max_steps=150000`, `test_batch_size=16`, `gamma=24.0` |
| **KG-BERT** | `max_seq_length=50`, `train_batch_size=32`, `learning_rate=5e-5`, `num_train_epochs=5.0`, `eval_batch_size=5000` |
| **CrossLink** | `emb_dimension=256`, `batch_size=256`, `epoch=200`, `learning_rate=5e-5`, `margin=9.0` |
| **SS-AGA** | `transe_margin=0.3`, `align_margin=6`, `dim=256`, `learning_rate=5e-3`, `align_lr=1e-3`, `batch_size=200`, `round=25`, `n_layers_KG=2`, `n_layers_align=2` |
| **LSMGA** | `margin=0.3`, `dim=256`, `round=50`, `batch_size=200`, `learning_rate=5e-3`, `test_batch_size=200`, `n_layers_gnn=2`, `epoch_each=3`, `n_heads=1` |
| **GCPLM** | `batch_size=128`, `lr=4e-5`, `epoch=8`, `max_len=35`, `alpha=0.001`, `beta=0.005`, `gama=10.0`, `early_stop=10`, `valid_per_step=1000` |
| **AlignKGC** | `learning_rate=0.8`, `batch_size=500`, `max_epochs=70`, `embedding_dim=256`, `ealoss_coeff=50.0`, `regloss_coeff=0.02` |
| **JMAC** | `margin_completion=5`, `margin_align=1`, `dim=256`, `epoch=30`, `batch_size=1000`, `align_lr=3e-4`, `completion_lr=3e-4`, `num_gcn_layer=2`, `comp_op=sub`, `pair_sample_weight=0.2` |
| **CLP** | `batch_size=2048`, `test_batch_size=100`, `learning_rate=5e-4`, `emb_dim=256`, `margin=9.0`, `topk=3`, `lambda_1=0.7`, `lambda_2=0.3`, `alpha=1.0`, `warmup=10` |


