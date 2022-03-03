```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
from scipy import optimize
from datetime import datetime
%matplotlib inline

try:
    import pandas_datareader.data as web
except:
    %pip install pip pandas-datareader
    import pandas_datareader.data as web
  
```


```python
def Asset(ticker, start, end, interval):
    return(web.get_data_yahoo(ticker, start, end, interval = interval))['Adj Close']

def beta(asset):
    CovBetweenMktandAsset = np.cov(MarketPortfolio, asset)    
    return(CovBetweenMktandAsset[0,1]/CovBetweenMktandAsset[0,0]) 

def ExpectedReturn(beta):
    ExpectedReturn = RiskFreeRate.mean() + beta * (MarketPortfolio.mean() -RiskFreeRate.mean())
    return(ExpectedReturn)
```


```python
RiskFreeRate = Asset("^TNX", '2001-01-01', '2021-12-31', 'm').pct_change().dropna()
MarketPortfolio = Asset("^GSPC", '2001-01-01', '2021-12-31', 'm').pct_change().dropna()
asset1 = Asset("aapl", '2001-01-01', '2021-12-31', 'm').pct_change().dropna()
```


```python
b = beta(asset1)

b

```




    1.2334810221586363




```python
ExpectedReturn = RiskFreeRate.mean() + b * (MarketPortfolio.mean() -RiskFreeRate.mean())

ExpectedReturn
```




    0.007318777689028467


