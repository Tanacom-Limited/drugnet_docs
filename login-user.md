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

{% swagger method="post" path="" baseUrl="/login_web_user" summary="Login Web User" %}
{% swagger-description %}
Authenticate a web user by providing their username and password.
{% endswagger-description %}

{% swagger-parameter in="body" name="username" required="true" %}
Provided the username
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Provided user password
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
curl --location --request POST 'https://portal.drugnet.com.gh/api/login_web_user' \
--header 'x-api-key: YOUR API KEY' \

```
{% endtab %}

{% tab title="PHP" %}
```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://portal.drugnet.com.gh/api/login_web_user',
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

url = "https://portal.drugnet.com.gh/api/login_web_user"

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



