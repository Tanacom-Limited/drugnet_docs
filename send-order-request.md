---
description: >-
  This API is used to send a medication request from a client to the DrugNet
  portal.
---

# 📦 Send Order Request

**Endpoint:** `POST /send_request_web`



## Send Request Web

<mark style="color:green;">`POST`</mark> `/send_request_web`

&#x20;Send a medication request from a client to the DrugNet portal..

#### Request Body

| Name                                         | Type       | Description                                                                                                                         |
| -------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| client\_id<mark style="color:red;">\*</mark> | integer    | The ID of the client submitting the request                                                                                         |
| prescription                                 | String     | The prescription or reason for the request.                                                                                         |
| order\_items                                 | JSON array | An array of objects specifying the items in the order. Each object should have `name` (string) and `quantity` (integer) properties. |
| insurance\_card                              | String     | The insurance card id                                                                                                               |
|                                              |            |                                                                                                                                     |
| file                                         | file       | The file to be uploaded, representing additional information or images related to the request.                                      |

{% tabs %}
{% tab title="200: OK Success" %}
```json
{
    "code": 200,
    "success": true,
    "message": "Order sent successfully"
}

```
{% endtab %}

{% tab title="204: No Content Request Empty" %}
```json
{
    "code": 204,
    "success": false,
    "message": "Error message"
}
```
{% endtab %}
{% endtabs %}



Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="Curl" %}
```
curl --location '/send_request_web' \
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
  CURLOPT_URL => '/send_request_web',
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

url = "/send_request_web"

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



