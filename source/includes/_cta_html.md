# Cta Html

## The cta html object

> Example Response

```json
{
  "cta": {
    "width": "30%",
    "updated_at": "2017-06-30T21:53:24.130443",
    "type": "CtaHtml",
    "top": "30%",
    "smart": false,
    "skip": false,
    "project_id": 278,
    "position_order": 4,
    "position": "inside",
    "on_start": true,
    "on_pause": false,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-7",
    "left": "30%",
    "id": 1,
    "height": "30%",
    "cuepoints": [],
    "created_at": "2017-06-30T21:53:24.130435",
    "background_opacity": "0.5",
    "background_color": "92,121,128",
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
html | string | Html code.
left | string | Distance from the left edge to cta.
top | string | Distance from the top edge to cta.
width | string | Cta width.
height | string | Cta height.
position | string | Position inside or outside the player.
cuepoints | array of arrays | Cuepoints timestamps.
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
background_color | string | Background color.
background_opacity | string | Background opacity.

<!-- /////////////////////////// CREATE CTA HTML /////////////////////////// -->

## Create a cta html

```shell
curl http://localhost:3500/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "cta": {
    "name": "cta-7",
    "type": "CtaHtml",
    "asset_id": 1,
    "html": "<div>Htmlcode</div>",
    "on_start": true,
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%"
  }
}
```

> Example Response

```json
{
  "cta": {
    "width": "30%",
    "updated_at": "2017-06-30T21:53:24.130443",
    "type": "CtaHtml",
    "top": "30%",
    "smart": false,
    "skip": false,
    "project_id": 1,
    "position_order": 4,
    "position": "inside",
    "on_start": true,
    "on_pause": false,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-7",
    "left": "30%",
    "id": 1,
    "height": "30%",
    "cuepoints": [],
    "created_at": "2017-06-30T21:53:24.130435",
    "background_opacity": "0.5",
    "background_color": "92,121,128",
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
type           | true      | string  |         | Cta type. Must be "CtaHtml".
asset_id       | true      | integer |         | The identifier of the asset.
html       | true      | string |         | Html code.
position   | false      | string  |  inside  | Position inside or outside the player. Must be "inside" or "outside"
left | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | true      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | true      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
background_color | false      | string  |  92,121,128  | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false      | string  |  0.5   | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
on_pause  | false      | boolean  |  false | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false   | Display cta on finish.
on_cuepoints | false      | boolean  |  false  | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  |  false  | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.


### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta html

```shell
curl http://localhost:3500/v1/ctas/7 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "cta": {
    "name": "new name",
    "position": "outside",
    "left": "99%",
    "width": "50%"
  }
}
```

> Example Response

```json
{
  "cta": {
    "width": "50%",
    "updated_at": "2017-06-30T21:55:00.923025",
    "type": "CtaHtml",
    "top": "30%",
    "smart": false,
    "skip": false,
    "project_id": 1,
    "position_order": 4,
    "position": "outside",
    "on_start": true,
    "on_pause": false,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "new name",
    "left": "99%",
    "id": 1,
    "height": "30%",
    "cuepoints": [],
    "created_at": "2017-06-30T21:53:24.130435",
    "background_opacity": "0.5",
    "background_color": "92,121,128",
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
id         | true      | integer |         | The identifier of the cta to be updated.
name           | false      | string  |         | Cta name
position   | false      | string  |  inside  | Position inside or outside the player. Must be "inside" or "outside"
left | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | false      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | false      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
background_color | false      | string  |  92,121,128  | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false      | string  |  0.5   | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
on_pause  | false      | boolean  |  false | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false   | Display cta on finish.
on_cuepoints | false      | boolean  |  false  | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  |  false  | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
