---
output:
  pdf_document: default
  html_document: default
---

Assignment- Web APIs

@author:Joseph Simone

The New York Times web site provides a rich set of APIs, as described here: https://developer.nytimes.com/apis


You'll need to start by signing up for an API key.
Your task is to choose one of the New York Times APIs, construct an interface in Python to read in

the JSON data
&
transform it into a pandas DataFrame.

### Solution

I decided to use the most sharded on Facebook API From NYT Dev API Website 

https://developer.nytimes.com/docs/most-popular-product/1/overview



```python
import requests
```


```python
import json
```


```python
from IPython.display import display
```


```python
import pandas as pd
```


```python
your_key = "FptvCLy8m9fKva5WGwlGQc2OJEjOJug5"
```


```python
url = 'https://api.nytimes.com/svc/mostpopular/v2/shared/1/facebook.json?api-key='+ your_key

```


```python
r = requests.get(url)
```


```python
json_data = json.loads(r.text)
```


```python
df = pd.DataFrame(json_data)

```


```python
display(df.head(10))  

```


<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>copyright</th>
      <th>num_results</th>
      <th>results</th>
      <th>status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Copyright (c) 2019 The New York Times Company....</td>
      <td>1095</td>
      <td>{'count_type': 'SHARED-FACEBOOK', 'org_facet':...</td>
      <td>OK</td>
    </tr>
  </tbody>
</table>
</div>

