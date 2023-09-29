# API

Our API endpoint can be found at `https://api.growthepie.xyz/`

### Master endpoint

Contains info on all supported chains and metrics.

```
v1/master.json
```

### Fundamentals endpoint

This is a very powerful endpoint. It returns all Layer 2 metrics for all chains on a daily aggregation level. The data updates daily at 5am UTC.

`v1/fundamentals.json`

#### **Example Python**

You can quickly load data on all Layer 2s into a Pandas dataframe using the following code snippet:

```python
import requests
import pandas as pd

url = 'https://api.growthepie.xyz/v1/fundamentals.json'
response = requests.get(url)
df = pd.DataFrame(response.json())
```

If you want to quickly visualize the datapoints you can use the dataframe plot function. Here filtered down to Arbitrum and transaction count:

```python
df[(df['metric_key'] == 'txcount') & (df['origin_key'] == 'arbitrum')].sort_values('date').plot(x='date', y='value', figsize=(15, 5), title='Arbitrum Daily Transactions')
```

<figure><img src=".gitbook/assets/Screenshot 2023-09-29 091713.png" alt=""><figcaption></figcaption></figure>

#### Example PowerBI

PowerBI is a powerful BI and data visualisation tool. If you want to load all Layer 2 data into a PowerBI dashboard follow these steps:

* Open new PowerBI file
* Load data using the "Web" data connector
* Paste the api endpoint in the URL field
* Make sure the "value" column is formated as decimal
* Load the data into your report and have fun exploring.

Here is a quick video walkthrough: [https://x.com/web3\_data/status/1697573767751548953?s=20](https://x.com/web3\_data/status/1697573767751548953?s=20)

<figure><img src=".gitbook/assets/Screenshot 2023-09-29 092125.png" alt=""><figcaption></figcaption></figure>
