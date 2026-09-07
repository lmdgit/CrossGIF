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

We report the main hyperparameter configurations of all baselines evaluated on the \textbf{DBP-FB5} dataset. The detailed settings are as follows.

\begin{table*}[t]
\centering
\caption{Main hyperparameter configurations of baselines on the DBP-FB5 dataset.}
\label{tab:baseline_configurations}
\resizebox{\textwidth}{!}{
\begin{tabular}{l|l}
\hline
\textbf{Method} & \textbf{Main Hyperparameters} \\
\hline
TransE &
\texttt{batch\_size}=1024, \texttt{hidden\_dim}=256, \texttt{learning\_rate}=1e-4, 
\texttt{max\_steps}=150000, \texttt{test\_batch\_size}=16, \texttt{gamma}=24.0 \\
\hline
RotatE &
\texttt{batch\_size}=1024, \texttt{hidden\_dim}=256, \texttt{learning\_rate}=1e-4, 
\texttt{max\_steps}=150000, \texttt{test\_batch\_size}=16, \texttt{gamma}=24.0 \\
\hline
KG-BERT &
\texttt{max\_seq\_length}=50, \texttt{train\_batch\_size}=32, 
\texttt{learning\_rate}=5e-5, \texttt{num\_train\_epochs}=5.0, 
\texttt{eval\_batch\_size}=5000 \\
\hline
CrossLink &
\texttt{emb\_dimension}=256, \texttt{batch\_size}=256, \texttt{epoch}=200, 
\texttt{learning\_rate}=5e-5, \texttt{margin}=9.0 \\
\hline
SS-AGA &
\texttt{transe\_margin}=0.3, \texttt{align\_margin}=6, \texttt{dim}=256, 
\texttt{learning\_rate}=5e-3, \texttt{align\_lr}=1e-3, 
\texttt{batch\_size}=200, \texttt{round}=25, 
\texttt{n\_layers\_KG}=2, \texttt{n\_layers\_align}=2 \\
\hline
LSMGA &
\texttt{margin}=0.3, \texttt{dim}=256, \texttt{round}=50, 
\texttt{batch\_size}=200, \texttt{learning\_rate}=5e-3, 
\texttt{test\_batch\_size}=200, \texttt{n\_layers\_gnn}=2, 
\texttt{epoch\_each}=3, \texttt{n\_heads}=1 \\
\hline
AlignKGC &
\texttt{learning\_rate}=0.8, \texttt{batch\_size}=500, 
\texttt{max\_epochs}=70, \texttt{embedding\_dim}=256, 
\texttt{ealoss\_coeff}=50.0, \texttt{regloss\_coeff}=0.02 \\
\hline
JMAC &
\texttt{margin\_completion}=5, \texttt{margin\_align}=1, \texttt{dim}=256, 
\texttt{epoch}=30, \texttt{batch\_size}=1000, 
\texttt{align\_lr}=3e-4, \texttt{completion\_lr}=3e-4, 
\texttt{num\_gcn\_layer}=2, \texttt{comp\_op}=\texttt{sub}, 
\texttt{pair\_sample\_weight}=0.2 \\
\hline
CLP &
\texttt{batch\_size}=2048, \texttt{test\_batch\_size}=100, 
\texttt{learning\_rate}=5e-4, \texttt{emb\_dim}=256, 
\texttt{margin}=9.0, \texttt{topk}=3, \texttt{lambda\_1}=0.7, 
\texttt{lambda\_2}=0.3, \texttt{alpha}=1.0, \texttt{warmup}=10 \\
\hline
\end{tabular}
}
\end{table*}



