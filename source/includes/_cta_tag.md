# Cta Tag

## The cta tag object

> Example Response

```json
{
  "id": 4,
  "name": "cta-4",
  "type": "CtaTag",
  "position_order": 4,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "button_text": "button_text",
  "cuepoints": [],
  "description": "desc",
  "fullscreen": false,
  "icon": "fa-dot-circle-o",
  "icon_color": "255,255,255",
  "icon_opacity": "0.5",
  "image": "http://image.com",
  "left": "30%",
  "link": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "pulse_color": "255,255,255",
  "pulse_opacity": "0.5",
  "skip": false,
  "sub_title": "sub_title",
  "tag_color": "255,255,255",
  "tag_opacity": "0.5",
  "title": "title",
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
tag_color | string | Tag color.
tag_opacity | string | Tag opacity.
pulse_color | string | Pulse color.
pulse_opacity | string | Pulse opacity.
icon | string | Icon type from FontAwesome. Example "fa fa-gift".
icon_color | string | Icon color.
icon_opacity | string | Icon opacity.
image | string | Image link.
description | string | Description text.
button_text | string | Button text.
title | string | Title text.
sub_title | string | Subtitle text.

<!-- /////////////////////////// CREATE CTA TAG /////////////////////////// -->

## Create a cta tag

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-4",
  "type": "CtaTag",
  "position_order": 4,
  "asset_id": 1,
  "options": {
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "link": "http://google.com",
    "title": "title",
    "sub_title": "sub_title",
    "image": "http://image.com",
    "button_text": "button_text",
    "description": "desc",
    "icon": "fa-dot-circle-o",
    "icon_color": "255,255,255",
    "icon_opacity": "0.5",
    "tag_color": "255,255,255",
    "tag_opacity": "0.5",
    "pulse_color": "255,255,255",
    "pulse_opacity": "0.5"
  }
}
```

> Example Response

```json
{
  "id": 4,
  "name": "cta-4",
  "type": "CtaTag",
  "position_order": 4,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "button_text": "button_text",
  "cuepoints": [],
  "description": "desc",
  "fullscreen": false,
  "icon": "fa-dot-circle-o",
  "icon_color": "255,255,255",
  "icon_opacity": "0.5",
  "image": "http://image.com",
  "left": "30%",
  "link": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "pulse_color": "255,255,255",
  "pulse_opacity": "0.5",
  "skip": false,
  "sub_title": "sub_title",
  "tag_color": "255,255,255",
  "tag_opacity": "0.5",
  "title": "title",
  "top": "30%"
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/api/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaTag".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left       | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
tag_color | true | string |     | Tag color. Must be in rgb format. Example: "100, 156, 144".
tag_opacity | true | string |     | Tag opacity. Must be in range (0.0..1.0). Example: "0.5".
pulse_color | true | string |     | Pulse color. Must be in rgb format. Example: "100, 156, 144".
pulse_opacity | true | string |     | Pulse opacity. Must be in range (0.0..1.0). Example: "0.5".
icon | true | string |     | Icon type from FontAwesome. Example "fa fa-gift".
icon_color | true | string |     | Icon color. Must be in rgb format. Example: "100, 156, 144".
icon_opacity | true | string |     | Icon opacity. Must be in range (0.0..1.0). Example: "0.5".
image | false | string |     | Image link.
description | false | string |     | Description text.
button_text | false | string |     | Button text.
title | false | string |     | Title text.
sub_title | false | string |     | Subtitle text.
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

## Update a cta tag

```shell
curl http://localhost:3500/api/v1/ctas/4 \
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
  "id": 4,
  "name": "new name",
  "type": "CtaTag",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "button_text": "button_text",
  "cuepoints": [],
  "description": "desc",
  "fullscreen": false,
  "icon": "fa-dot-circle-o",
  "icon_color": "255,255,255",
  "icon_opacity": "0.5",
  "image": "http://image.com",
  "left": "99%",
  "link": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "outside",
  "pulse_color": "255,255,255",
  "pulse_opacity": "0.5",
  "skip": false,
  "sub_title": "sub_title",
  "tag_color": "255,255,255",
  "tag_opacity": "0.5",
  "title": "title",
  "top": "30%"
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

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
left       | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top        | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
tag_color | false | string |     | Tag color. Must be in rgb format. Example: "100, 156, 144".
tag_opacity | false | string |     | Tag opacity. Must be in range (0.0..1.0). Example: "0.5".
pulse_color | false | string |     | Pulse color. Must be in rgb format. Example: "100, 156, 144".
pulse_opacity | false | string |     | Pulse opacity. Must be in range (0.0..1.0). Example: "0.5".
icon | false | string |     | Icon type from FontAwesome. Example "fa fa-gift".
icon_color | false | string |     | Icon color. Must be in rgb format. Example: "100, 156, 144".
icon_opacity | false | string |     | Icon opacity. Must be in range (0.0..1.0). Example: "0.5".
image | false | string |     | Image link.
description | false | string |     | Description text.
button_text | false | string |     | Button text.
title | false | string |     | Title text.
sub_title | false | string |     | Subtitle text.
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
