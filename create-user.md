---
description: Create a new user in the DrugNet system.
---

# 🧑‍🤝‍🧑 Create User

{% hint style="info" %}
**Good to know:** A quick start guide can be good to help folks get up and running with your API in a few steps. Some people prefer diving in with the basics rather than meticulously reading every page of documentation!
{% endhint %}

## Make your first request

To make your first request, send an authenticated request to the drugnet endpoint. This will create a user, which is nice.

## Create user.

<mark style="color:green;">`POST`</mark> `/create_user`

This endpoint allows you to create a new user in the DrugNet System.

#### Request Body

| Name                                    | Type   | Description           |
| --------------------------------------- | ------ | --------------------- |
| name<mark style="color:red;">\*</mark>  | string | The name of the user  |
| email<mark style="color:red;">\*</mark> | string | The email of the user |
| phone<mark style="color:red;">\*</mark> | string | The phone of the user |
| country                                 | string | Source country        |

{% tabs %}
{% tab title="200 User created sucessfully" %}
```javascript
{
  "status": "success",
  "message": "User created successfully",
  "user": {
    "id": 123,
    "name": "John Doe",
    "phone": "+233 xx xxx xxxx",
    "email": "john.doe@doe.com"
  }
}

```
{% endtab %}

{% tab title="400: Bad Request Invalid Request" %}
{ "status": "error", "message": "Invalid API key" }
{% endtab %}

{% tab title="204: No Content Empty field" %}

{% endtab %}

{% tab title="500: Internal Server Error Internal Server Error" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Good to know:** You can use the API Method block to fully document an API method. You can also sync your API blocks with an OpenAPI file or URL to auto-populate them.
{% endhint %}

Take a look at how you might call this method using our official libraries, or via `curl`:

{% tabs %}
{% tab title="curl" %}
```
curl --location '/create_user' \
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
  'url': '/create_user',
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
$request->setRequestUrl('/create_user');
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
