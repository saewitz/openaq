OpenAQ provides a REST API for programmatic access to the OpenAQ database.


Usage
-----


The OpenAQ API is currently available in two versions:


* Legacy version 1 \- only includes reference/government sources, i.e. does not include low\-cost sensors
* Current version 2 \- includes full OpenAQ dataset and additional query features compared to version 1


Interactive reference documentation of both versions of the REST API is available in the [reference](/reference) section.


API Key
-------



> 📘\`Starting July 1 2023 an API Key is required to access the OpenAQ API at the full rate limit. Key\-less access is still available but at a significantly lower rate limit.
> ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Register for an API Key at <https://explore.openaq.org/register>. Once registered with a valid email, you can access your API by signing in and visiting your OpenAQ Explorer account settings at <https://explore.openaq.org/account>. Do not share this key: each key is allocated a usage rate and sharing the your key will impact the amount of requests available. 


To use the API Key in requests to the OpenAQ API, add the key to the request headers using the `X-API-Key`header key. e.g.


shePython
```
curl --header "X-API-Key: my-openaq-api-key-12345-6789" https://api.openaq.org/v2/locations

```

```
import requests

res = requests.get("https://api.openaq.org/v2/locations/2178", headers={"X-API-Key": "my-openaq-api-key-12345-6789"})


```
Updated about 1 month ago 



---

