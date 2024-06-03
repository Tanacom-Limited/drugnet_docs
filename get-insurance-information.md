---
description: >-
  Retrieves insurance information from the DrugNet portal . The response is a
  JSON object containing a success boolean field, a message string field, and a
  data array field.
---

# ⛓️ Get Insurance Information

The data array contains objects with `name` and `image` string fields.



**Endpoint:** GET `/`get\_insurance



{% tabs %}
{% tab title="Curl" %}
```
curl --location '/get_insurance' \
--header 'x-api-key: YOUR KEY' \

```
{% endtab %}

{% tab title="PHP" %}
```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => '/get_insurance',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'x-api-key: YOUR KEY',
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}
{% endtabs %}





**Successful Response**

```
{
    "success": true,
    "message": "successful",
    "data": [
        {
            "name": "METROPOLITAN HEALTH INSURANCE GHANA LTD.",
            "image": "7tuyhzmq3ws68gb.jpg"
        },
        {
            "name": "COSMOPOLITAN HEALTH INSURANCE",
            "image": "61rukyp9z_ihlfb.png"
        },
       
    ]
}
```

