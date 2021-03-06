---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.2'
      jupytext_version: 1.5.0
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Load Extensions


## Notify after cell completion

```python
%load_ext jupyternotify

import time

time.sleep(5)

# notify when code block finish execution
%notify
```

## Notify after a threshold

```python
# autonotify on completion for cells that run longer than 10 seconds
%autonotify -a 10

time.sleep(11)
```

# Autoreload module


## Load Extension and Build Module

> Maybe if I copy `src` and `setup.py` to `/home/josue/work`, the module building could be done from the Dockerfile instead of a cell within jupyter.

```python
%load_ext autoreload

%autoreload 2

!pip install -e ..
```

```python
from src.example.foo import some_function

# Current return value from the function is 42
some_function()
```

```python
# change value from 42 to 500
some_function()
```

```python

```

```python

```

```python

```
