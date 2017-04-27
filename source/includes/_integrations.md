# Integrations

## The integration object

> Example Response

```json
{
  "id": 1,
  "title": "integration-1",
  "type": "IntegrationStripe",
  "account_id": 2,
  "use_cloudfront": false,
  "integration_type": "payment",
  "provider": "stripe",
  "created_at": "2017-04-25T22:00:47.047560",
  "updated_at": "2017-04-25T22:00:47.047560",
  "publishable_key": "publishable_key",
  "secret_key": "secret_key"
}
```

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the integration.
title | string | Integration title.
integration_type | string | Integration type(email, csn and etc).
type | string | Type(IntegrationAweber, IntegrationPaypal and etc).
provider | string | Integration provider(aweber, paypal and etc).
use_cloudfront | boolean | Cloudfront(true or false).
account_id | integer | The identifier of the account.
created_at | string | The date and time the integration was created.
created_at | string | The date and time the integration was updated.

Each integration may includes it's own fields

### Integration ActiveCampaign

Parameter | Type | Description
--------- | ---- | -----------
api_endpoint | string | Api endpoint.
actid | string | Act id.
api_key | string | Api key(encrypted).
event_key | string | Event key(encrypted).

### Integration Amazon

Parameter | Type | Description
--------- | ---- | -----------
bucket | string | Bucket .
access_key_id | string | Access key id.
cloudfront | string | Cloudfront.
ready | string | Bucket status.
secret_access_key | string | Secret access key(encrypted).

### Integration Aweber

Parameter | Type | Description
--------- | ---- | -----------
access_token | string | Access token.
consumer_key | string | Consumer key.
access_token_secret | string | Secret access token(encrypted).
consumer_secret | string | Consumer secret(encrypted).

### Integration Convertkit

Parameter | Type | Description
--------- | ---- | -----------
api_key | string | Api key.
secret_key | string | Secret key(encrypted).

### Integration Disqus

Parameter | Type | Description
--------- | ---- | -----------
forum_shortname | string | Forum shortname.

### Integration Drip

Parameter | Type | Description
--------- | ---- | -----------
api_account_id | string | Api account id.
access_token | string | Access token(encrypted).

### Integration Getresponse

Parameter | Type | Description
--------- | ---- | -----------
secret_api_key | string | Secret api key(encrypted).

### Integration Google Analytics

Parameter | Type | Description
--------- | ---- | -----------
api_account_id | string | Api account id.
web_property_id | string | Web property id.
access_token | string | Access token(encrypted).
refresh_token | string | Refresh token(encrypted).

### Integration Html

Parameter | Type | Description
--------- | ---- | -----------
html | string | Html code.
params | hash | Parameters inside html code.
url | string | Url inside html code.

### Integration Infusionsoft

Parameter | Type | Description
--------- | ---- | -----------
app_name | string | App name.
api_key | string | Api key(encrypted).

### Integration Intercom

Parameter | Type | Description
--------- | ---- | -----------
access_token | string | Access token(encrypted).

### Integration Mailchimp

Parameter | Type | Description
--------- | ---- | -----------
api_key | string | Api key(encrypted).

### Integration Ontraport

Parameter | Type | Description
--------- | ---- | -----------
app_id | string |App id.
api_key | string | Api key(encrypted).

### Integration Paypal

Parameter | Type | Description
--------- | ---- | -----------
client_id | string | Client id.
client_secret | string | Client secret(encrypted).

### Integration Sendreach

Parameter | Type | Description
--------- | ---- | -----------
api_key | string | Api key.
secret_api_key | string | Secret api key(encrypted).

### Integration Stripe

Parameter | Type | Description
--------- | ---- | -----------
publishable_key | string | Publishable key.
secret_key | string | Secret key(encrypted).

### Integration Wishlist

Parameter | Type | Description
--------- | ---- | -----------
endpoint | string | Endpoint.
api_key | string | Api key(encrypted).


<!-- /////////////////////////// INTEGRATIONS /////////////////////////// -->

## List all integrations

```shell
curl http://localhost:3500/api/v1/integrations \
  -d api_key=test_key
```

> Example Response

```json
[
  {
    "id": 1,
    "title": "integration-1",
    "type": "IntegrationStripe",
    "account_id": 2,
    "use_cloudfront": false,
    "integration_type": "payment",
    "provider": "stripe",
    "created_at": "2017-04-25T22:00:47.047560",
    "updated_at": "2017-04-25T22:00:47.047560",
    "publishable_key": "publishable_key",
    "secret_key": "secret_key"
  },
  {
    "id": 2,
    "title": "integration-2",
    "type": "IntegrationMailchimp",
    "account_id": 2,
    "use_cloudfront": false,
    "integration_type": "email",
    "provider": "mailchimp",
    "created_at": "2017-04-26T19:22:20.387166",
    "updated_at": "2017-04-26T19:22:20.387166",
    "api_key": "api_key"
  }
]
```

This endpoint retrieves all integrations.

### HTTP Request

`GET http://localhost:3500/api/v1/integrations`

### Returns
Returns a list of your integrations if the call succeeded.

<!-- /////////////////////////// SPECIFIC INTEGRATION /////////////////////////// -->

## Retrieve a integration

```shell
curl http://localhost:3500/api/v1/integrations/1 \
  -d api_key=test_key
```

> Example Response

```json
{
  "id": 1,
  "title": "integration-1",
  "type": "IntegrationStripe",
  "account_id": 2,
  "use_cloudfront": false,
  "integration_type": "payment",
  "provider": "stripe",
  "created_at": "2017-04-25T22:00:47.047560",
  "updated_at": "2017-04-25T22:00:47.047560",
  "publishable_key": "publishable_key",
  "secret_key": "secret_key"
}
```

This endpoint retrieves a specific integration.

### HTTP Request

`GET http://localhost:3500/api/v1/integrations/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the integration to be retrived.

### Returns
Returns a integration object if the call succeeded. If the integration ID does not exist, this call returns an error.

