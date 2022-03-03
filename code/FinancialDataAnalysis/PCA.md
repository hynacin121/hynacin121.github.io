```python
import numpy as np
from sklearn.decomposition import PCA
import pandas as pd
```

+ Using Scikit


```python
X = np.array([[-1, -1], [-2, -2], [-3, -2], [1, 1], [2, 1], [3, 2]])
pca = PCA(n_components = 2)
pca.fit(X)
print(pca.explained_variance_ratio_)

```

    [0.99157153 0.00842847]
    

+ Using Covariance 


```python
df = pd.DataFrame(X)

covariance = df.cov()
eigenvalue = np.linalg.eigvals(covariance)

pc1 = np.linalg.eigvals(df.cov())[0]/sum(np.linalg.eigvals(df.cov()))
pc2 = np.linalg.eigvals(df.cov())[1]/sum(np.linalg.eigvals(df.cov()))

print(pc1, pc2)
```

    0.9915715292774702 0.008428470722529814
    


```python

```
