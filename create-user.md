---
description: Create a new user in the DrugNet system.
---

# 🧑‍🤝‍🧑 Create User

{% hint style="info" %}
**Good to know:** A quick start guide can be good to help folks get up and running with your API in a few steps. Some people prefer diving in with the basics rather than meticulously reading every page of documentation!
{% endhint %}

## Make your first request

To make your first request, send an authenticated request to the drugnet endpoint. This will create a user, which is nice.

{% swagger baseUrl="/create_user" method="post" path="" summary="Create user." %}
{% swagger-description %}
This endpoint allows you to create a new user in the DrugNet System.
{% endswagger-description %}

{% swagger-parameter in="body" name="name" required="true" type="string" %}
The name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" type="string" %}
The email of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" type="string" %}
The phone of the user
{% endswagger-parameter %}

{% swagger-response status="200" description="User created sucessfully" %}
```javascript
{
  "status": "success",
  "message": "User created successfully",
  "user": {
    "id": 123,
    "name": "Anthony Tandoh",
    "phone": "0504305596",
    "email": "anthonytandoh90@yahoo.com"
  }
}

```
{% endswagger-response %}

{% swagger-response status="204: No Content" description="Empty field" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Invalid Request" %}
{ "status": "error", "message": "Invalid API key" }
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
**Good to know:** You can use the API Method block to fully document an API method. You can also sync your API blocks with an OpenAPI file or URL to auto-populate them.
{% endhint %}

Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="curl" %}
```
curl --location 'https://portal.drugnet.com.gh/api/create_user' \
--header 'x-api-key: YOUR API KEY' \
--form 'name="YOUR NAME"' \
--form 'phone="YOUR PHONE"' \
--form 'email="YOUR EMAIL"' 
```
{% endtab %}

{% tab title="Node" %}
```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'https://portal.drugnet.com.gh/api/create_user',
  'headers': {
    'x-api-key': 'YOUR API KEY'
  },
  formData: {
    'name': 'YOUR NAME',
    'phone': 'YOUR PHONE',
    'email': 'YOUR EMAIL'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});


```
{% endtab %}

{% tab title="PHP" %}
```python
<?php
$client = new http\Client;
$request = new http\Client\Request;
$request->setRequestUrl('https://portal.drugnet.com.gh/api/create_user');
$request->setRequestMethod('POST');
$body = new http\Message\Body;
$body->addForm(array(
  'name' => 'your name',
  'phone' => 'your phone',
  'email' => 'your email'
), array(

));
$request->setBody($body);
$request->setOptions(array());
$request->setHeaders(array(
  'x-api-key' => 'your api key'
));
$client->enqueue($request)->send();
$response = $client->getResponse();
echo $response->getBody();


```
{% endtab %}
{% endtabs %}



## Example

```
{
    "code": 200,
    "success": true,
    "message": "User created sucessfully"
}
```
