# Cta Purchase

## The cta purchase object

> Example Response

```json
{
  "id": 5,
  "name": "cta-5",
  "type": "CtaPurchase",
  "position_order": 5,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "billing_email": "some@gmail.com",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "cuepoints": [],
  "delivery_method": "play_video",
  "description": "desc",
  "description_color": "255,255,255",
  "download_link": "https://google.com",
  "font_size": "25px",
  "fullscreen": false,
  "image": "https://image.com",
  "ipn_url": "https://google.com",
  "left": "30%",
  "left_background_color": "255,255,255",
  "left_background_color_opacity": "0.5",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "payment_titles_color": "255,255,255",
  "paypal_integration_id": null,
  "position": "inside",
  "price": 10.0,
  "price_color": "255,255,255",
  "product_id": "12",
  "purchase_asset_ids": [],
  "right_background_color": "255,255,255",
  "right_background_color_opacity": "0.5",
  "sender_name": "sender_name",
  "skip": false,
  "smart": false,
  "stripe_integration_id": "15",
  "sub_title": "sub_title",
  "text_color": "255,255,255",
  "text_opacity": "0.5",
  "title": "title",
  "title_color": "255,255,255",
  "top": "30%"
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
text_color | string | Text color.
text_opacity | string | Text opacity.
title | string | Title text.
title_color | string | Title color.

<!-- /////////////////////////// CREATE CTA PURCHASE /////////////////////////// -->

## Create a cta purchase

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-5",
  "type": "CtaPurchase",
  "position_order": 5,
  "asset_id": 1,
  "options": {
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "title_color": "255,255,255",
    "text_color": "255,255,255",
    "text_opacity": "0.5",
    "button_bg_color": "255,255,255",
    "button_bg_opacity": "0.5",
    "price_color": "255,255,255",
    "left_background_color": "255,255,255",
    "right_background_color": "255,255,255",
    "left_background_color_opacity": "0.5",
    "right_background_color_opacity": "0.5",
    "payment_titles_color": "255,255,255",
    "description_color": "255,255,255",
    "billing_email": "some@gmail.com",
    "download_link": "https://google.com",
    "description": "desc",
    "sender_name": "sender_name",
    "font_size": "25px",
    "title": "title",
    "sub_title": "sub_title",
    "image": "https://image.com",
    "price": 10.0,
    "product_id": "12",
    "ipn_url": "https://google.com",
    "delivery_method": "play_video",
    "purchase_asset_ids": [],
    "stripe_integration_id": "15"
  }
}
```

> Example Response

```json
{
  "id": 5,
  "name": "cta-5",
  "type": "CtaPurchase",
  "position_order": 5,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "billing_email": "some@gmail.com",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "cuepoints": [],
  "delivery_method": "play_video",
  "description": "desc",
  "description_color": "255,255,255",
  "download_link": "https://google.com",
  "font_size": "25px",
  "fullscreen": false,
  "image": "https://image.com",
  "ipn_url": "https://google.com",
  "left": "30%",
  "left_background_color": "255,255,255",
  "left_background_color_opacity": "0.5",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "payment_titles_color": "255,255,255",
  "paypal_integration_id": null,
  "position": "inside",
  "price": 10.0,
  "price_color": "255,255,255",
  "product_id": "12",
  "purchase_asset_ids": [],
  "right_background_color": "255,255,255",
  "right_background_color_opacity": "0.5",
  "sender_name": "sender_name",
  "skip": false,
  "smart": false,
  "stripe_integration_id": "15",
  "sub_title": "sub_title",
  "text_color": "255,255,255",
  "text_opacity": "0.5",
  "title": "title",
  "title_color": "255,255,255",
  "top": "30%"
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/api/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. paypal_integration_id or stripe_integration_id must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaPurchase".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left  | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
billing_email | true | string |        | Billing email.
button_bg_color | true | string |        | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | true | string |       | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
delivery_method | true | string |       | Delivery method. Must be "", "play_video" or "link".
description | false | string |       | Description text.
description_color | true | string |       | Description color. Must be in rgb format. Example: "100, 156, 144".
download_link | false | string |       | Download link.
font_size | false | string |       | Text font size. Must end with "px". Example: "30px".
image | true | string |       | Image link. Must be secured(https).
ipn_url | true | string |       | Ipn link. Must be secured(https).
left_background_color | true | string |       | Left background color. Must be in rgb format. Example: "100, 156, 144".
left_background_color_opacity | true | string |       | Left background opacity. Must be in range (0.0..1.0). Example: "0.5".
payment_titles_color | true | string |       | Payment titles color. Must be in rgb format. Example: "100, 156, 144".
paypal_integration_id | false | string |       | The identifier of the paypal integration.
price | false | float |       | Price.
product_id | false | string |       | Product id.
purchase_asset_ids | false | array |  []     | Purchase assets ids.
right_background_color | true | string |       | Right background color. Must be in rgb format. Example: "100, 156, 144".
right_background_color_opacity | true | string |       | Right background opacity. Must be in range (0.0..1.0). Example: "0.5".
sender_name | true | string |       | Sender name.
stripe_integration_id | false | string |       | The identifier of the stripe integration.
sub_title | false | integer |       | Subtitle text.
text_color | true | string |       | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | true | string |       | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
title | false | string |       | Title text.
title_color | true | string |       | Title color. Must be in rgb format. Example: "100, 156, 144".
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.


### Returns
Returns a cta object if the call succeeded. If a parent cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta purchase

```shell
curl http://localhost:3500/api/v1/ctas/5 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "new name",
  "options": {
    "position": "outside",
    "left": "99%"
  }
}
```

> Example Response

```json
{
  "id": 5,
  "name": "new name",
  "type": "CtaPurchase",
  "position_order": 5,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "billing_email": "some@gmail.com",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "cuepoints": [],
  "delivery_method": "play_video",
  "description": "desc",
  "description_color": "255,255,255",
  "download_link": "https://google.com",
  "font_size": "25px",
  "fullscreen": false,
  "image": "https://image.com",
  "ipn_url": "https://google.com",
  "left": "99%",
  "left_background_color": "255,255,255",
  "left_background_color_opacity": "0.5",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "payment_titles_color": "255,255,255",
  "paypal_integration_id": null,
  "position": "outside",
  "price": 10.0,
  "price_color": "255,255,255",
  "product_id": "12",
  "purchase_asset_ids": [],
  "right_background_color": "255,255,255",
  "right_background_color_opacity": "0.5",
  "sender_name": "sender_name",
  "skip": false,
  "smart": false,
  "stripe_integration_id": "15",
  "sub_title": "sub_title",
  "text_color": "255,255,255",
  "text_opacity": "0.5",
  "title": "title",
  "title_color": "255,255,255",
  "top": "30%"
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. paypal_integration_id or stripe_integration_id must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
position_order | false      | integer |         | Position in the queue when cta is displayed.
options        | false      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | false      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left  | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
billing_email | false | string |        | Billing email.
button_bg_color | false | string |        | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | false | string |       | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
delivery_method | false | string |       | Delivery method. Must be "", "play_video" or "link".
description | false | string |       | Description text.
description_color | false | string |       | Description color. Must be in rgb format. Example: "100, 156, 144".
download_link | false | string |       | Download link.
font_size | false | string |       | Text font size. Must end with "px". Example: "30px".
image | false | string |       | Image link. Must be secured(https).
ipn_url | false | string |       | Ipn link. Must be secured(https).
left_background_color | false | string |       | Left background color. Must be in rgb format. Example: "100, 156, 144".
left_background_color_opacity | false | string |       | Left background opacity. Must be in range (0.0..1.0). Example: "0.5".
payment_titles_color | false | string |       | Payment titles color. Must be in rgb format. Example: "100, 156, 144".
paypal_integration_id | false | string |       | The identifier of the paypal integration.
price | false | float |       | Price.
product_id | false | string |       | Product id.
purchase_asset_ids | false | array |  []     | Purchase assets ids.
right_background_color | false | string |       | Right background color. Must be in rgb format. Example: "100, 156, 144".
right_background_color_opacity | false | string |       | Right background opacity. Must be in range (0.0..1.0). Example: "0.5".
sender_name | false | string |       | Sender name.
stripe_integration_id | false | string |       | The identifier of the stripe integration.
sub_title | false | integer |       | Subtitle text.
text_color | false | string |       | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | false | string |       | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
title | false | string |       | Title text.
title_color | false | string |       | Title color. Must be in rgb format. Example: "100, 156, 144".
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
