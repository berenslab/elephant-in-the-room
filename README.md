## The art of seeing the elephant in the room: <br/> 2D embeddings of single-cell data do make sense
<p align="center">
<img src="results/figures/embeddings_combined.png" alt="Main figure" width="600"/>
</p>


This repository holds the code to reproduce the analysis in [Lause, Berens & Kobak (2024) preprint ADD LINK](https://www.biorxiv.org) and shows [main and supplementary figures](results/figures). <p align="center">

</p>


To reproduce our analysis, follow the steps below. We assume you have `git` and `conda` installed.

### Install

- Clone this repository.
```
git clone git@github.com:berenslab/elephant-in-the-room.git
```

- Inside the main folder of the repo, go to the `src` folder.
- In `src`, clone our Picasso fork.
- Go back to main folder.
```
cd src
git clone git@github.com:berenslab/picasso.git
cd ..
```

- Install the conda environment for Picasso.
```
conda env create -f src/picasso/env/env3.7_LINUX.yml
```

- From the main folder of the `elephant-in-the-room` repo, activate the `picasso_env` environment and install our Picasso fork with `pip`.
```
conda activate picasso_env
pip install -e .
```

- Install our conda analysis environment.
```
conda env create -f environment.yml
```

### Run the analysis

- Activate our conda analysis environment.
- Start jupyter lab to run notebooks 1&2 in the `scripts` folder. This will download the data, run preprocesing and compute PCA, t-SNE and UMAP embeddings.
```
conda activate elephant_analysis_env
jupyter lab
```

- After that, activate the Picasso anvironment and start jupyter notebook to run notebook 3. This will run Picasso and create the elephant embeddings.
```
conda activate picasso_env
jupyter notebook
```

- After that, again activate our analysis environment.
- Start jupyter lab to run the remaining notebooks 4&5. This will run the evaluations and prepare the plots.
```
conda activate elephant_analysis_env
jupyter lab
```

### System information

We used `conda 23.11.0` on a recent laptop with 16GB RAM running `LINUX 6.5.0-18-generic #18~22.04.1-Ubuntu`. See [environment.yml](environment.yml) for more information on the analysis environment, and [env3.7_LINUX.yml](https://github.com/berenslab/picasso/blob/main/env/env3.7_LINUX.yml) for more information on the Picasso environment.

### Copyright information

[Notebook 1](scripts/01_prepare_data.ipynb) and [notebook 3](03_compute_picasso_embedding.ipynb) use code adapted from the github repository [CP_2023](https://github.com/pachterlab/CP_2023) by Chari & Pachter, which is subject to the following licence:

```
BSD 2-Clause License

Copyright (c) 2021, Pachter Lab
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

