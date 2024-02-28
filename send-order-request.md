---
description: >-
  This API is used to send a medication request from a client to the DrugNet
  portal.
---

# 📦 Send Order Request

**Endpoint:** `POST /send_request_web`



**Request Body Parameters**

1. `client_id` (integer, required): The ID of the client making the request. Obtain from after user login.
2. `prescription` (string, optional): The description of the prescription or medical condition.
3. `order_items` (string, optional): A JSON array containing the details of the medications being requested. Each item should have a `name` (string) and `quantity` (integer).



{% swagger method="post" path="" baseUrl="/send_request_web" summary="Send Request Web" %}
{% swagger-description %}
&#x20;Send a medication request from a client to the DrugNet portal..
{% endswagger-description %}

{% swagger-parameter in="body" name="client_id" required="true" type="integer" %}
The ID of the client submitting the request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="prescription" required="false" %}
The prescription or reason for the request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="order_items" type="JSON array" %}
An array of objects specifying the items in the order. Each object should have `name` (string) and `quantity` (integer) properties.
{% endswagger-parameter %}

{% swagger-parameter in="body" type="file " name="file" %}
The file to be uploaded, representing additional information or images related to the request.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}

{% endswagger-response %}

{% swagger-response status="204: No Content" description="Request Empty" %}

{% endswagger-response %}
{% endswagger %}



Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="Curl" %}
```
curl --location 'https://portal.drugnet.com.gh/api/send_request_web' \
--header 'x-api-key: YOUR API KEY' \
--form 'client_id="YOUR CLIENT ID"' \
--form 'prescription="YOUR PRESCRIPTION"' \
--form 'order_items="[{\"name\": \"drug 1\", \"quantity\": 2}, {\"name\": \"drug 2\", \"quantity\": 3}]"' \
--form 'file=@"YOUR FILE"'
```
{% endtab %}

{% tab title="PHP" %}
```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://portal.drugnet.com.gh/api/send_request_web',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('client_id' => 'YOUR CLIENT ID','prescription' => 'YOUR PRESCRIPTION','order_items' => '[{"name": "drug 1", "quantity": 2}, {"name": "drug 2", "quantity": 3}]','file'=> new CURLFILE('YOUR FILE')),
  CURLOPT_HTTPHEADER => array(
    'x-api-key: YOUR API KEY',

  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="Python" %}
```
import requests

url = "https://portal.drugnet.com.gh/api/send_request_web"

payload = {'client_id': 'YOUR CLIENT ID',
'prescription': 'YOUR PRESCRIPTION',
'order_items': '[{"name": "drug 1", "quantity": 2}, {"name": "drug 2", "quantity": 3}]'}
files=[
  ('file',('toda.png',open('YOUR FILE','rb'),'image/png'))
]
headers = {
  'x-api-key': 'YOUR API KEY',

}

response = requests.request("POST", url, headers=headers, data=payload, files=files)

print(response.text)

```
{% endtab %}
{% endtabs %}



## Example

```
{
  "client_id": 28378,
  "prescription": "Headache",
  "order_items": [
    {"name": "drug 1", "quantity": 2},
    {"name": "drug 2", "quantity": 3}
  ],
  "file": [file content]
}

```



> In case of errors, the API will return a JSON object with a `success` field indicating whether the request was successful, and a corresponding error message in the `message` field.



