<div align="center">
  
  ![logo](https://github.com/user-attachments/assets/48ff868b-7bb3-456d-9b14-47aee4437b4d)

  [Discord](https://discord.gg/kTkF2e69fH) • [Website](https://flywhl.dev) • [Installation](#installation)
  <br/>
  <br/>
</div>

## Features

Diform uses dependency injection to orchestrate data-transformation pipelines on-the-fly.

## Installation

* `uv add diform`

## Usage

```python
from typing import Any, NewType

import diform
import numpy as np

Tensor = NewType("tensor", np.ndarray)

def subtract_mean(data: Tensor) -> MeanSubtracted[Tensor]:
    ...

def pca(data: MeanSubtracted[Any]) -> Tensor:
    ...

container = diform.Container(subtract_mean, pca, dataset=np.array([[1, 2, 3], [4, 5, 6]])

data = container["pca"]()

```


## Development

* `git clone https://github.com/flywhl/diform.git`
* `cd diform`
* `uv sync`
* `just test`

## Flywheel

Science needs humble software tools. [Flywheel](https://flywhl.dev/) is an open source collective building simple tools to preserve scientific momentum, inspired by devtools and devops culture. Join our Discord [here](discord.gg/fd37MFZ7RS).

