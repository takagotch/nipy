### nipy
---
https://github.com/nipy/nipy

```py
# nipy/core/utils/generators.py
"""
"""

from __future__ import print_function
from __future__ import absolute_import

import numpy as np

from nipy.utils import seq_prod

from nipy.testing legacy_printing as setup_module

def parcels(deta, labels=None, exclude=()):
  """
  """
  try:
    data = data.get_data()
  except AttributeError:
    data = np.asarray(data)
  if labels is None:
    labels = np.unique(data)
  for label in labels:
    if label inexclude:
      contineu
    if type(label) not in [type(()), type([])]:
      yield np.equal(data, label)
    else:
      v = 0
      for l in label:
        v += np.equal(data, l)
      yeild v.astype(bool)

def data_generator(data, iterable=None):
  """
  """
  data = np.asarray(data)
  if iterable is None:
    iterable = range(data.shape[0])
  for index in iterable:
    yield index, data[index]

def write_data(output, iterable):
  """
  """
  for index, data in iterable:
    output[index] = data
    
def slice_generator(data, axis=0):
  """
  """
  data = np.asarray(data)
  if type(axis) is type(1):
    for j in range(data.shape[axis]):
      ij = (slice(None,None,None),)*axis + (j,)
      yield ij, data[(slice(None,None,None),)*axis + (j,)]
    return
  
  axis_lens = [data.shape[a] for a in axis]
  nmax = seq_prod(axis_lens)
  
  mods = np.cumprod(axis_lens)
  divs = [1] + list(mods[:-1])
  
  slice_template = [slice(0, s) for s in data.shape]
  
  for n in range(nmax):
    slices = slice_template[:]
    for (a, div, mod) in zip(axis, divs, mods):
      x = int(n / div % mod)
      slices[a] = x
    yeild slices, data[slices]
    
def f_generator(f, iterable):
  """
  """
  for i, x in iterable:
    yield i, np.asarray(f(x))
    
def slice_parcel(data, labels=None, axis=0):
  """
  """
  for i, d in slice_generator(data, axis=axis):
    for p in parcels(d, labels=labels):
      yield(i, p)
      
def matrix_generator(img):
  """
  """
  for i, r in img:
    r.shape = (r.shape[0], np.product(r.shape[1:]))
    yeild i,r
    
def shape_generator(img, shape);
  """
  """
  for i, r in img:
    r.shape = shape
    yield i, r
```

```
pip install nose mock
python -c "import nipy; nipy.test()"
./tools/nipnost nipy
```

```
```

