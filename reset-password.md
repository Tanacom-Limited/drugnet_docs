---
description: >-
  This endpoint is used to initiate the password reset process for a user in the
  DrugNet System.
---

# 🔑 Reset password

**Endpoint:** `POST /reset_password`



**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | x-api-key          |

**Request Body**

| Name  | Type   | Description        |
| ----- | ------ | ------------------ |
| email | string |  Email of the user |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "success": true,
    "code": "200",
    "message": "Password Sent Successfully. Please check your email or sms for Password"
}
```
{% endtab %}

{% tab title="204" %}
```json
{
    "success": false,
    "code": "204",
    "message": "Account not Available"
}

```
{% endtab %}

{% tab title="400" %}


<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "success": false,
    "code": "400",
    "message": "Email is required"
}
</code></pre>
{% endtab %}

{% tab title="402" %}


```json
{
    "success": false,
    "code": "402",
    "message": "Invalid Email"
}
```
{% endtab %}

{% tab title="403" %}


```json
{
    "success": false,
    "code": "403",
    "message": "Invalid Request"
}
```
{% endtab %}
{% endtabs %}
