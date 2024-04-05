---
description: >-
  On this page, you can find our different endpoints and some examples of how to
  quickly connect them to your favorite data analytics tool.
---

# API

Our API endpoint can be found at `https://api.growthepie.xyz/`

## Master endpoint

This endpoint contains info on all supported chains and metrics. It is mostly static meta data like chain names, important links, etc.

```
v1/master.json
```

## Contracts endpoint

This endpoint returns all labeled contracts for all our covered chains. It includes contract address, contract name, project name, sub category key, and origin key (which is the chain)

```
v1/contracts.json
```

#### Sample Reponse

```json
[
    {
        "address": "0xEa2a41c02fA86A4901826615F9796e603C6a4491",
        "contract_name": "BridgeToBase",
        "project_name": "Base",
        "sub_category_key": "erc721",
        "origin_key": "base"
    },
    {
        "address": "0xBA12222222228d8Ba445958a75a0704d566BF2C8",
        "contract_name": "Vault",
        "project_name": "Balancer",
        "sub_category_key": "dex",
        "origin_key": "arbitrum"
    },
    ...
]
```

## Fundamentals endpoint

This is a very powerful endpoint for analytics and tracking. It returns all Layer 2 metrics for all chains on a daily aggregation level. The data updates daily at 5 a.m. UTC.

`v1/fundamentals_full.json`

This endpoint will grow in size and will return >10MB of data. We also created a filtered endpoint (only last 365 days and no eth values) which can be used in Google Sheets and other applications that limit the input data to 10MB.

`v1/fundamentals.json`

#### Sample Response

```json
[
    {
        "metric_key": "daa",
        "origin_key": "imx",
        "date": "2023-04-21",
        "value": 8300.0
    },
    {
        "metric_key": "txcount",
        "origin_key": "zksync_era",
        "date": "2023-02-14",
        "value": 6.0
    },
    {
        "metric_key": "daa",
        "origin_key": "imx",
        "date": "2023-04-25",
        "value": 7834.0
    },
    ...
]
```

### **Example Python**

You can quickly load data on all Layer 2s into a Pandas dataframe using the following code snippet:

```python
import requests
import pandas as pd

url = 'https://api.growthepie.xyz/v1/fundamentals_full.json'
response = requests.get(url)
df = pd.DataFrame(response.json())
```

If you want to quickly visualize the data points you can use the dataframe plot function. Here filtered down to Arbitrum and transaction count:

```python
df[(df['metric_key'] == 'txcount') & (df['origin_key'] == 'arbitrum')].sort_values('date').plot(x='date', y='value', figsize=(15, 5), title='Arbitrum Daily Transactions')
```

<figure><img src=".gitbook/assets/Screenshot 2023-09-29 091713.png" alt=""><figcaption></figcaption></figure>

### Example Excel

Excel is still the most widely used tool for data analytics. Using our API, you can build this neat dashboard in less than 2 minutes:

<figure><img src=".gitbook/assets/Recording 2024-04-05 at 12.26.31.gif" alt=""><figcaption><p>Excel dashboard example</p></figcaption></figure>

Here is a quick guide on how to pull data from our API and visualize it

{% embed url="https://twitter.com/web3_data/status/1776194203602571663" %}
Guide for Excel usage
{% endembed %}

### Example PowerBI

PowerBI is a powerful BI and data visualization tool. If you want to load all Layer 2 data into a PowerBI dashboard follow these steps:

* Open a new PowerBI file
* Load data using the "Web" data connector
* Paste the API endpoint in the URL field
* Make sure the "value" column is formatted as decimal
* Load the data into your report and have fun exploring.

Here is a quick video walkthrough: [https://x.com/web3\_data/status/1697573767751548953?s=20](https://x.com/web3\_data/status/1697573767751548953?s=20)

<figure><img src=".gitbook/assets/Screenshot 2023-09-29 092125.png" alt=""><figcaption></figcaption></figure>

### Example Google Sheets

Sometimes it can be useful to have up-to-date Layer 2 data in Google Sheets. With our endpoint, it is very simple.

* Create app script for ImportJson function (code: [https://gist.github.com/paulgambill/cacd19da95a1421d3164](https://gist.github.com/paulgambill/cacd19da95a1421d3164))
* Paste function in cell

```
=ImportJSON("https://api.growthepie.xyz/v1/fundamentals.json")
```

<figure><img src=".gitbook/assets/Screenshot 2023-09-29 093630.png" alt=""><figcaption></figcaption></figure>
