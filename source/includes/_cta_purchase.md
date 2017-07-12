# Cta Purchase

## The cta purchase object

> Example Response

```json
{
  "cta": {
    "payment_titles_color": "151,108,14",
    "on_pause": true,
    "description": null,
    "cuepoints": [],
    "project_id": 1,
    "title": null,
    "button_bg_color": "237,140,45",
    "position_order": 16,
    "on_finish": false,
    "position": "inside",
    "id": 1,
    "sender_name": "Kirill",
    "created_at": "2017-07-05T15:52:07.698077",
    "download_link": null,
    "on_start": false,
    "ipn_url": null,
    "price": 9.99,
    "left_background_color": "18,18,18",
    "sub_title": null,
    "on_cuepoints": false,
    "image": null,
    "delivery_method": "none",
    "purchase_asset_ids": [],
    "paypal_integration_id": "6",
    "button_bg_opacity": "1",
    "price_color": "255,255,255",
    "left_background_color_opacity": "0.95",
    "skip": false,
    "right_background_color": "255,181,22",
    "right_background_color_opacity": "0.95",
    "type": "CtaPurchase",
    "stripe_integration_id": null,
    "title_color": "255,255,255",
    "billing_email": "email@gmail.com",
    "smart": false,
    "name": "CtaPurchase 9367",
    "updated_at": "2017-07-05T15:52:07.698138",
    "product_id": "dsaas",
    "description_color": "255,255,255",
    "asset_id": 1
  }
}
```

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the cta.
name | string | Cta name.
type | string | Cta type.
position_order | integer | Position in the queue when cta is displayed.
asset_id | integer | The identifier of the asset.
project_id | integer | The identifier of the project.
created_at | string | The date and time the cta was created.
updated_at | string | The date and time the cta was updated.
left | string | Distance from the left edge to cta.
top | string | Distance from the top edge to cta.
position | string | Position inside or outside the player.
cuepoints | array of arrays | Cuepoints timestamps.
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
fullscreen | boolean | Fullscreen.
billing_email | string | Billing email.
button_bg_color | string | Button background color.
button_bg_opacity | string | Button background opacity.
delivery_method | string | Delivery method.
description | string | Description text.
description_color | string | Description color.
download_link | string | Download link.
font_size | string | Text font size.
image | string | Image link. Must be secured(https).
ipn_url | string | Ipn link. Must be secured(https).
left_background_color | string | Left background color.
left_background_color_opacity | string | Left background opacity.
payment_titles_color | string | Payment titles color.
paypal_integration_id | string | The identifier of the paypal integration.
price | float | Price.
product_id | string | Product id.
purchase_asset_ids | array | Purchase assets ids.
right_background_color | string | Right background color.
right_background_color_opacity | string | Right background opacity.
sender_name | string | Sender name.
stripe_integration_id | string | The identifier of the stripe integration.
sub_title | integer | Subtitle text.
price_color | string | Price text color.
title | string | Title text.
title_color | string | Title color.

<!-- /////////////////////////// CREATE CTA PURCHASE /////////////////////////// -->

## Create a cta purchase

```shell
curl http://localhost:3500/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "cta": {
    "type": "CtaPurchase",
    "asset_id": 1
    "on_pause": true,
    "delivery_method": "none",
    "price": "9.99",
    "name": "CtaPurchase 9367",
    "paypal_integration_id": "6",
    "product_id": "dsaas",
    "billing_email": "email@gmail.com",
    "sender_name": "Kirill",
  }
}
```

> Example Response

```json
{
  "cta": {
    "payment_titles_color": "151,108,14",
    "on_pause": true,
    "description": null,
    "cuepoints": [],
    "project_id": 1,
    "title": null,
    "button_bg_color": "237,140,45",
    "position_order": 16,
    "on_finish": false,
    "position": "inside",
    "id": 1,
    "sender_name": "Kirill",
    "created_at": "2017-07-05T15:52:07.698077",
    "download_link": null,
    "on_start": false,
    "ipn_url": null,
    "price": 9.99,
    "left_background_color": "18,18,18",
    "sub_title": null,
    "on_cuepoints": false,
    "image": null,
    "delivery_method": "none",
    "purchase_asset_ids": [],
    "paypal_integration_id": "6",
    "button_bg_opacity": "1",
    "price_color": "255,255,255",
    "left_background_color_opacity": "0.95",
    "skip": false,
    "right_background_color": "255,181,22",
    "right_background_color_opacity": "0.95",
    "type": "CtaPurchase",
    "stripe_integration_id": null,
    "title_color": "255,255,255",
    "billing_email": "email@gmail.com",
    "smart": false,
    "name": "CtaPurchase 9367",
    "updated_at": "2017-07-05T15:52:07.698138",
    "product_id": "dsaas",
    "description_color": "255,255,255",
    "asset_id": 1
  }
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. paypal_integration_id or stripe_integration_id must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaPurchase".
asset_id       | true      | integer |         | The identifier of the asset.
position   | false      | string  |  inside  | Position inside or outside the player. Must be "inside" or "outside"
currency | false | string | USD | Payment currency.
button_bg_color | false | string | 237,140,45 | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | false | string | 1 | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
description_color | false | string | 255,255,255 | Description color. Must be in rgb format. Example: "100, 156, 144".
left_background_color | false | string | 18,18,18  | Left background color. Must be in rgb format. Example: "100, 156, 144".
left_background_color_opacity | false | string |  0.95  | Left background opacity. Must be in range (0.0..1.0). Example: "0.5".
right_background_color | false | string | 255,181,22 | Right background color. Must be in rgb format. Example: "100, 156, 144".
right_background_color_opacity | false | string | 0.95 | Right background opacity. Must be in range (0.0..1.0). Example: "0.5".
payment_titles_color | false | string | 151,108,14 | Payment titles color. Must be in rgb format. Example: "100, 156, 144".
price_color | false | string | 255,255,255  | Price text color. Must be in rgb format. Example: "100, 156, 144".
title_color | false | string |  255,255,255 | Title color. Must be in rgb format. Example: "100, 156, 144".
billing_email | true | string |        | Billing email.
delivery_method | true | string |       | Delivery method. Must be "", "play_video" or "link".
description | false | string |       | Description text.
download_link | false | string |       | Download link.
image | false | string |       | Image link. Must be secured(https).
ipn_url | false | string |       | Ipn link. Must be secured(https).
price | true | float |       | Price.
product_id | true | string |       | Product id.
purchase_asset_ids | false | array |  [] | Purchase assets ids.
sender_name | true | string |       | Sender name.
paypal_integration_id | false | string |       | The identifier of the paypal integration.
stripe_integration_id | false | string |       | The identifier of the stripe integration.
title | false | string |       | Title text.
sub_title | false | integer |       | Subtitle text.
on_pause  | false      | boolean  |  false  | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false   | Display cta on finish.
on_cuepoints | false      | boolean  |   false   | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  [] | Cuepoints timestamps.
smart  | false      | boolean  |  false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.


### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta purchase

```shell
curl http://localhost:3500/v1/ctas/1 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "cta": {
    "price": "18.99",
    "name": "new_name",
    "product_id": "new_product_id",
    "billing_email": "new_mail@gmail.com"
  }
}
```

> Example Response

```json
{
  "cta": {
    "payment_titles_color": "151,108,14",
    "on_pause": true,
    "description": null,
    "cuepoints": [],
    "project_id": 1,
    "title": null,
    "button_bg_color": "237,140,45",
    "position_order": 16,
    "on_finish": false,
    "position": "inside",
    "id": 1,
    "sender_name": "Kirill",
    "created_at": "2017-07-05T15:52:07.698077",
    "download_link": null,
    "on_start": false,
    "ipn_url": null,
    "price": 18.99,
    "left_background_color": "18,18,18",
    "sub_title": null,
    "on_cuepoints": false,
    "image": null,
    "delivery_method": "none",
    "purchase_asset_ids": [],
    "paypal_integration_id": "6",
    "button_bg_opacity": "1",
    "price_color": "255,255,255",
    "left_background_color_opacity": "0.95",
    "skip": false,
    "right_background_color": "255,181,22",
    "right_background_color_opacity": "0.95",
    "type": "CtaPurchase",
    "stripe_integration_id": null,
    "title_color": "255,255,255",
    "billing_email": "new_mail@gmail.com",
    "smart": false,
    "name": "new_name",
    "updated_at": "2017-07-05T16:23:13.382511",
    "product_id": "new_product_id",
    "description_color": "255,255,255",
    "asset_id": 1
  }
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. paypal_integration_id or stripe_integration_id must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
options        | false      | hash    |         | Cta options.
position   | false      | string  |  inside  | Position inside or outside the player. Must be "inside" or "outside"
currency | false | string | USD | Payment currency.
button_bg_color | false | string | 237,140,45 | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | false | string | 1 | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
description_color | false | string | 255,255,255 | Description color. Must be in rgb format. Example: "100, 156, 144".
left_background_color | false | string | 18,18,18  | Left background color. Must be in rgb format. Example: "100, 156, 144".
left_background_color_opacity | false | string |  0.95  | Left background opacity. Must be in range (0.0..1.0). Example: "0.5".
right_background_color | false | string | 255,181,22 | Right background color. Must be in rgb format. Example: "100, 156, 144".
right_background_color_opacity | false | string | 0.95 | Right background opacity. Must be in range (0.0..1.0). Example: "0.5".
payment_titles_color | false | string | 151,108,14 | Payment titles color. Must be in rgb format. Example: "100, 156, 144".
price_color | false | string | 255,255,255  | Price text color. Must be in rgb format. Example: "100, 156, 144".
title_color | false | string |  255,255,255 | Title color. Must be in rgb format. Example: "100, 156, 144".
billing_email | true | string |        | Billing email.
delivery_method | true | string |       | Delivery method. Must be "", "play_video" or "link".
description | false | string |       | Description text.
download_link | false | string |       | Download link.
image | false | string |       | Image link. Must be secured(https).
ipn_url | false | string |       | Ipn link. Must be secured(https).
price | true | float |       | Price.
product_id | true | string |       | Product id.
purchase_asset_ids | false | array |  [] | Purchase assets ids.
sender_name | true | string |       | Sender name.
paypal_integration_id | false | string |       | The identifier of the paypal integration.
stripe_integration_id | false | string |       | The identifier of the stripe integration.
title | false | string |       | Title text.
sub_title | false | integer |       | Subtitle text.
on_pause  | false      | boolean  |  false  | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false   | Display cta on finish.
on_cuepoints | false      | boolean  |   false   | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  [] | Cuepoints timestamps.
smart  | false      | boolean  |  false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
