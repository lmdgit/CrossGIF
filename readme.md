# CrossGIF: A cross-graph information fusion method for multiple knowledge graphs completion

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





