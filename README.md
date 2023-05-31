# brainwalk

::: {.cell 0=‘h’ 1=‘i’ 2=‘d’ 3=‘e’}

``` python
import sys
sys.path.append("..")
from brainwalk.core import *
```

:::

> Spatial graph embeddings for ObsidianMD

## Install

``` sh
pip install brainwalk
```

## How to use

``` python

# Find the Obsidian Vault directory and assert that it exists
import os
from pathlib import Path
vault_dir = Path(os.getcwd()) / 'vault-stub'
assert vault_dir.exists()

# Retrieve a Gensim word2vec model of your Obsidian Graph
from brainwalk.core import brainwave
from wirewalk.core import jaccard_coefficient

model = brainwave(vault_dir,jaccard_coefficient)
```

``` python
model.wv.key_to_index
```

    {'Vulnera ubera': 0,
     'Causam mihi': 1,
     'Sussudio': 2,
     'Ne fuit': 3,
     'Brevissimus moenia': 4,
     'Alimenta': 5,
     'American Psycho (film)': 6,
     'Aras Teucras': 7,
     'Tydides': 8,
     'Dives': 9,
     'Caelum': 10,
     'Vita': 11,
     'Isolated note': 12,
     'Tarpeia': 13,
     'Manus': 14,
     'Amor': 15,
     'lipsum/Isolated note': 16,
     'Bacchus': 17,
     'Virtus': 18,
     'Aetna': 19}

``` python
model.wv.most_similar("Vulnera ubera")
```

    [('Ne fuit', 0.9992153644561768),
     ('Bacchus', 0.9991818070411682),
     ('Manus', 0.9991797804832458),
     ('Tydides', 0.9991616606712341),
     ('Sussudio', 0.9991515278816223),
     ('Vita', 0.9991357922554016),
     ('American Psycho (film)', 0.9991220831871033),
     ('lipsum/Isolated note', 0.9991198182106018),
     ('Virtus', 0.9991057515144348),
     ('Causam mihi', 0.999089777469635)]
