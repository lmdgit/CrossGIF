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
| **TransE** | batch_size∈{512, 1024, 2048}, hidden_dim∈{128, 256, 512}, learning_rate∈{5e-5, 1e-4, 5e-4}, max_steps∈{100000, 150000, 200000}, gamma∈{18.0, 24.0, 30.0} |
| **RotatE** | batch_size∈{512, 1024, 2048}, hidden_dim∈{128, 256, 512}, learning_rate∈{5e-5, 1e-4, 5e-4}, max_steps∈{100000, 150000, 200000}, gamma∈{18.0, 24.0, 30.0} |
| **KG-BERT** | max_seq_length∈{32, 50, 64}, train_batch_size∈{16, 32, 64}, learning_rate∈{1e-5, 5e-5, 1e-4}, num_train_epochs∈{3.0, 5.0, 7.0} |
| **CrossLink** | emb_dimension∈{128, 256, 512}, batch_size∈{128, 256, 512}, epoch∈{100, 200, 300}, learning_rate∈{1e-5, 5e-5, 1e-4}, margin∈{3.0, 6.0, 9.0} |
| **SS-AGA** | transe_margin∈{0.1, 0.3, 0.5}, align_margin∈{3.0, 6.0, 9.0}, dim∈{128, 256, 512}, learning_rate∈{1e-3, 5e-3, 1e-2}, align_lr∈{5e-4, 1e-3, 2e-3}, batch_size∈{256, 512, 1024}, round∈{15, 25, 35}, n_layers_KG∈{1, 2, 3}, n_layers_align∈{1, 2, 3} |
| **LSMGA** | margin∈{0.2, 0.3, 0.5}, dim∈{128, 256, 512}, round∈{25, 50, 75}, batch_size∈{150, 200, 250}, learning_rate∈{1e-4, 5e-4, 1e-3}, n_layers_gnn∈{1, 2, 3}, epoch_each∈{1, 3, 5}, n_heads∈{1, 2, 4} |
| **AlignKGC** | learning_rate∈{0.4, 0.8, 1.2}, batch_size∈{250, 500, 1000}, max_epochs∈{50, 70, 100}, embedding_dim∈{128, 256, 512}, ealoss_coeff∈{10.0, 50.0, 100.0}, regloss_coeff∈{0.01, 0.02, 0.05} |
| **JMAC** | margin_completion∈{0, 5, 10}, margin_align∈{0, 5, 10}, dim∈{128, 256, 512}, epoch∈{20, 25, 30}, batch_size∈{500, 1000, 2000}, align_lr∈{1e-4, 5e-4, 1e-3}, completion_lr∈{1e-4, 5e-4, 1e-3}, num_gcn_layer∈{1, 2, 3}, pair_sample_weight∈{0.1, 0.2, 0.3} |
| **CLP** | batch_size∈{512, 1024, 2048}, learning_rate∈{1e-4, 5e-4, 1e-3}, emb_dim∈{128, 256, 512}, margin∈{9.0, 12.0}, topk∈{1, 3, 5, 10}, lambda_1∈{0.7, 0.8, 0.9}, lambda_2∈{0.2, 0.3, 0.4}, alpha∈{0.01, 0.1, 1.0}, warmup∈{8, 10, 12} |
| **GCPLM** | batch_size∈{64, 128, 256}, lr∈{3e-5, 4e-5, 5e-5}, epoch∈{5, 8, 10}, max_len∈{32, 35, 40}, alpha∈{0.0005, 0.001, 0.005}, beta∈{0.0005, 0.001, 0.005}, gama∈{5.0, 10.0, 20.0}, early_stop∈{5, 10, 15}, valid_per_step∈{500, 1000, 2000} |



