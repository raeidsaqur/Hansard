<h1>
  <img alt="RH" src="./icon.png" style="display:inline-block; vertical-align:middle" />
   Pedagogical Machine Translation (Dialect) dataset: the filtered Canadian Hansard Dataset. 
</h1>
The Canadian [Hansard](https://www.ourcommons.ca/documentviewer/en/35-2/house/hansard-index) is an archive of parliamentary sessions in the two official languages in Canada - English and Franch. 

## 📋 Table of Contents

- [🧩 Hansard Dataset](#-hansard-dataset)
  - [📋 Table of Contents](#-table-of-contents)
  - [📖 Usage](#-usage)
    - [Downloading the dataset](#downloading-the-dataset)
    - [Dataset structure](#dataset-structure)
    - [Loading the dataset](#loading-the-dataset)
  <!--- [Evaluating](#evaluating)
     - [Running the baselines](#running-the-baselines)
      - [Word Embeddings and Pre-trained Language Models](#word-embeddings-and-pre-trained-language-models)
      - [Large Language Models](#large-language-models) -->
  - [✍️ Contributing](#️-contributing)
  - [📝 Citing](#-citing)
  - [🙏 Acknowledgements](#-acknowledgements)

## 📖 Usage

### Downloading the dataset

The hansard dataset can be downloaded from [here](https://www.cs.toronto.edu/~raeidsaqur/hansard/hansard.tar.gz) or with a bash script:
    
```bash
bash download_hansard.sh
```

### Dataset structure

The dataset is provided as csv (and parquet) files, one for each partition: `train.[csv|parquet]` and `test.csv`. We also provide a `hansard.[csv|parquet]` file that contains all examples across all splits. The splits are sized as follows:

<!-- 
| Split | # Walls | 
|:-------|:---------:|
| `train` |   494   |
| `test`  | 62      |

Here is an example of the dataset's structure:

```csv

```
 -->

### Loading the dataset

The three partitions can be loaded the same way as any other csv file. For example, using Python:

```python
dataset = {
    "train": csv.load(open("./Hansard/train.csv", "r"))["dataset"],
    "test": csv.load(open("./Hansard/test.csv", "r"))["dataset"],
}
```

However, it is likely easiest to work with the dataset using the [HuggingFace Datasets](https://huggingface.co/datasets) library:

```python
# pip install datasets
from datasets import load_dataset

# The dataset can be used like any other HuggingFace dataset
dataset = load_dataset("raeidsaqur/hansard")

```

<!-- > __Note__ -->
<!-- ### Evaluating

We provide a script for evaluating the performance of a model on the dataset. Before running, make sure you have installed the requirements and package:

```bash
pip install -r requirements.txt
pip install -e .
```

To run the evaluation script:

### Running the baselines

 -->

## ✍️ Contributing

We welcome contributions to this repository (noticed a typo? a bug?). To propose a change:

```
git clone https://github.com/raeidsaqur/hansard
cd hansard
git checkout -b my-branch
pip install -r requirements.txt
pip install -e .
```

Once your changes are made, make sure to lint and format the code (addressing any warnings or errors):

```
isort .
black .
flake8 .
```

Then, submit your change as a pull request.

## 📝 Citing

If you use the Canadian Hansarddataset in your work, please consider citing our paper:

```
@article{raeidsaqur2024Hansard,
    title        = {The Canadian Hansard Dataset for Analyzing Dialect Efficiencies in Language Models},
    author       = {Raeid Saqur},
    year         = 2024,
    journal      = {ArXiv},
    url          = 
}
```

## 🙏 Acknowledgements

The entire CSC401/2511 teaching team at the Dept. of Computer Science at the University of Toronto.
