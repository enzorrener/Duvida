# Duvida
Duvida em um projeto em Python quem puder me ajudar eu agradeço
o código é esse:

import pandas as pd
from pandas_datareader import data as web
import matplotlib.pyplot as plt

# vamos pegar cotação do Indice e de Petrobras

#indice
df = web.DataReader(f'^BVSP', data_source='yahoo', start=f'02-20-2020', end='02-20-2021')

MAS O ERRO É ESSE:

AttributeError                            Traceback (most recent call last)
<ipython-input-20-1afbf5611b40> in <module>
      6 
      7 #indice
----> 8 df = web.DataReader(f'^BVSP', data_source='yahoo', start=f'02-20-2020', end='02-20-2021')

~\anaconda3\envs\envpowerbi\lib\site-packages\pandas\util\_decorators.py in wrapper(*args, **kwargs)
    197                 else:
    198                     kwargs[new_arg_name] = new_arg_value
--> 199             return func(*args, **kwargs)
    200 
    201         return cast(F, wrapper)

~\anaconda3\envs\envpowerbi\lib\site-packages\pandas_datareader\data.py in DataReader(name, data_source, start, end, retry_count, pause, session, api_key)
    376             retry_count=retry_count,
    377             pause=pause,
--> 378             session=session,
    379         ).read()
    380 

~\anaconda3\envs\envpowerbi\lib\site-packages\pandas_datareader\base.py in read(self)
    251         # If a single symbol, (e.g., 'GOOG')
    252         if isinstance(self.symbols, (string_types, int)):
--> 253             df = self._read_one_data(self.url, params=self._get_params(self.symbols))
    254         # Or multiple symbols, (e.g., ['GOOG', 'AAPL', 'MSFT'])
    255         elif isinstance(self.symbols, DataFrame):

~\anaconda3\envs\envpowerbi\lib\site-packages\pandas_datareader\yahoo\daily.py in _read_one_data(self, url, params)
    150         ptrn = r"root\.App\.main = (.*?);\n}\(this\)\);"
    151         try:
--> 152             j = json.loads(re.search(ptrn, resp.text, re.DOTALL).group(1))
    153             data = j["context"]["dispatcher"]["stores"]["HistoricalPriceStore"]
    154         except KeyError:

AttributeError: 'NoneType' object has no attribute 'group'
