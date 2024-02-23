- clone main repo

```
git clone git@github.com:berenslab/elephant-in-the-room.git
```

- inside the main repo, in `src`, clone our picasso fork, go back to main folder

```
cd src
git clone git@github.com:berenslab/picasso.git
cd ..
```

- install conda environment for picasso

for Linux: 

```
conda env create -f src/picasso/env/env3.7_LINUX.yml
```

for MacOS (untested, experimental)

```
conda env create -f src/picasso/env/env3.7_MACOS.yml
```

- activate the `picasso_env` environment and install our Picasso fork in it

```
conda activate picasso_env
pip install -e .
```

- install conda environment for our analysis

```
conda env create -f environment.yml
```

- activate the analysis environment and start jupyter lab to run notebooks 1&2. this will download the data, run preprocesing and compute PCA, t-SNE and UMAP embeddings

```
conda activate elephant_analysis_env
jupyter lab
```

- activate the Picasso anvironment and start jupyter notebook to run notebook 3. this will run picasso and create the elephant embeddings.

```
conda activate picasso_env
jupyter notebook
```

- again activate the analysis environment and start jupyter lab to run the remaining notebooks. this will run the evaluations and prepare the plots.

```
conda activate elephant_analysis_env
jupyter lab
```

