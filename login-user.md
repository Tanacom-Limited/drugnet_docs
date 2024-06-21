---
description: Authenticate a web user by providing their username and password.
---

# 🧑‍💻 Login User

**Endpoint:** `POST /login_web_user`



**Request:**

```
POST /login_web_user
Host: portal.drugnet.com.gh
x-api-key: YOUR_API_KEY
Content-Type: application/x-www-form-urlencoded

username=your_username&password=your_password

```

## Login Web User

<mark style="color:green;">`POST`</mark> `/login_web_user`

Authenticate a web user by providing their username and password.

#### Request Body

| Name                                       | Type   | Description            |
| ------------------------------------------ | ------ | ---------------------- |
| username<mark style="color:red;">\*</mark> | String | Provided  username     |
| password<mark style="color:red;">\*</mark> | String | Provided user password |

{% tabs %}
{% tab title="200: OK Success" %}

{% endtab %}

{% tab title="204: No Content Request Empty" %}

{% endtab %}
{% endtabs %}



Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST '/login_web_user' \
--header 'x-api-key: YOUR API KEY' \

```
{% endtab %}

{% tab title="PHP" %}
```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => '/login_web_user',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
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

url = "/login_web_user"

payload = {}
files={}
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
  "success": true,
  "user": {
    "id": 123,
    "name": "John Doe",
    "email": "john.doe@example.com"
  }
}

```



> In case of errors, the API will return a JSON object with a `success` field indicating whether the request was successful, and a corresponding error message in the `message` field.



