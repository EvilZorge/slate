# Cta Tag

## The cta tag object

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:16:46.560570",
    "type": "CtaTag",
    "top": "30%",
    "title": "title",
    "tag_opacity": "1",
    "tag_color": "24,214,127",
    "sub_title": null,
    "skip": false,
    "pulse_opacity": "1",
    "pulse_color": "255,255,255",
    "project_id": 1,
    "position_order": 8,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-4",
    "link": "http://google.com",
    "left": "30%",
    "image": null,
    "id": 1,
    "icon_opacity": "1",
    "icon_color": "255,255,255",
    "icon": "fa-dot-circle-o",
    "description": null,
    "cuepoints": [],
    "created_at": "2017-07-01T00:16:46.560515",
    "button_text": null,
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
curl http://localhost:3500/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
 "cta": {
    "name": "cta-4",
    "type": "CtaTag",
    "asset_id": 1,
    "left": "30%",
    "top": "30%",
    "link": "http://google.com",
    "title": "title",
    "icon": "fa-dot-circle-o",
    "on_pause": true
  }
}
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:16:46.560570",
    "type": "CtaTag",
    "top": "30%",
    "title": "title",
    "tag_opacity": "1",
    "tag_color": "24,214,127",
    "sub_title": null,
    "skip": false,
    "pulse_opacity": "1",
    "pulse_color": "255,255,255",
    "project_id": 1,
    "position_order": 8,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-4",
    "link": "http://google.com",
    "left": "30%",
    "image": null,
    "id": 1,
    "icon_opacity": "1",
    "icon_color": "255,255,255",
    "icon": "fa-dot-circle-o",
    "description": null,
    "cuepoints": [],
    "created_at": "2017-07-01T00:16:46.560515",
    "button_text": null,
    "asset_id": 1
  }
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaTag".
asset_id       | true      | integer |         | The identifier of the asset.
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
left       | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
tag_color | false | string |  24,214,127  | Tag color. Must be in rgb format. Example: "100, 156, 144".
tag_opacity | false | string |   1  | Tag opacity. Must be in range (0.0..1.0). Example: "0.5".
pulse_color | false | string |  255,255,255 | Pulse color. Must be in rgb format. Example: "100, 156, 144".
pulse_opacity | false | string |  1  | Pulse opacity. Must be in range (0.0..1.0). Example: "0.5".
icon | true | string |     | Icon type from FontAwesome. Example "fa fa-gift".
icon_color | false | string |   255,255,255  | Icon color. Must be in rgb format. Example: "100, 156, 144".
icon_opacity | false | string |  1  | Icon opacity. Must be in range (0.0..1.0). Example: "0.5".
image | false | string |     | Image link.
description | false | string |     | Description text.
button_text | false | string |     | Button text.
title | false | string |     | Title text.
sub_title | false | string |     | Subtitle text.
on_pause  | false      | boolean  | false  | Display cta on pause.
on_start  | false      | boolean  | false  | Display cta on start.
on_finish | false      | boolean  | false  | Display cta on finish.
on_cuepoints | false      | boolean  |  false   | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  [] | Cuepoints timestamps.
smart  | false      | boolean  |  false  | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta tag

```shell
curl http://localhost:3500/v1/ctas/1 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
 "cta": {
    "name": "new name",
    "position": "outside",
    "left": "99%",
    "button_text": "text"
  }
}
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:18:52.882585",
    "type": "CtaTag",
    "top": "30%",
    "title": "title",
    "tag_opacity": "1",
    "tag_color": "24,214,127",
    "sub_title": null,
    "skip": false,
    "pulse_opacity": "1",
    "pulse_color": "255,255,255",
    "project_id": 278,
    "position_order": 8,
    "position": "outside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "new name",
    "link": "http://google.com",
    "left": "99%",
    "image": null,
    "id": 1,
    "icon_opacity": "1",
    "icon_color": "255,255,255",
    "icon": "fa-dot-circle-o",
    "description": null,
    "cuepoints": [],
    "created_at": "2017-07-01T00:16:46.560515",
    "button_text": "text",
    "asset_id": 1
  }
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
left       | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
tag_color | false | string |  24,214,127  | Tag color. Must be in rgb format. Example: "100, 156, 144".
tag_opacity | false | string |   1  | Tag opacity. Must be in range (0.0..1.0). Example: "0.5".
pulse_color | false | string |  255,255,255 | Pulse color. Must be in rgb format. Example: "100, 156, 144".
pulse_opacity | false | string |  1  | Pulse opacity. Must be in range (0.0..1.0). Example: "0.5".
icon | false | string |     | Icon type from FontAwesome. Example "fa fa-gift".
icon_color | false | string |   255,255,255  | Icon color. Must be in rgb format. Example: "100, 156, 144".
icon_opacity | false | string |  1  | Icon opacity. Must be in range (0.0..1.0). Example: "0.5".
image | false | string |     | Image link.
description | false | string |     | Description text.
button_text | false | string |     | Button text.
title | false | string |     | Title text.
sub_title | false | string |     | Subtitle text.
on_pause  | false      | boolean  | false  | Display cta on pause.
on_start  | false      | boolean  | false  | Display cta on start.
on_finish | false      | boolean  | false  | Display cta on finish.
on_cuepoints | false      | boolean  |  false   | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  [] | Cuepoints timestamps.
smart  | false      | boolean  |  false  | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
