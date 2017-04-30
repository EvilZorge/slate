# Cta Html

## The cta html object

> Example Response

```json
{
  "id": 7,
  "name": "cta-7",
  "type": "CtaHtml",
  "position_order": 7,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "html": "<div>Htmlcode</div>",
  "position": "inside",
  "left": "30%",
  "top": "30%",
  "width": "30%",
  "height": "30%",
  "background_color": "255,255,255",
  "background_opacity": "0.5"
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
fullscreen | boolean | Fullscreen.
background_color | string | Background color.
background_opacity | string | Background opacity.

<!-- /////////////////////////// CREATE CTA HTML /////////////////////////// -->

## Create a cta html

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-7",
  "type": "CtaHtml",
  "position_order": 7,
  "asset_id": 1,
  "html": "<div>Htmlcode</div>"
  "options": {
    "on_start": true,
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%",
    "background_color": "255,255,255",
    "background_opacity": "0.5"
  }
}
```

> Example Response

```json
{
  "id": 7,
  "name": "cta-7",
  "type": "CtaHtml",
  "position_order": 7,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "html": "<div>Htmlcode</div>",
  "position": "inside",
  "left": "30%",
  "top": "30%",
  "width": "30%",
  "height": "30%",
  "background_color": "255,255,255",
  "background_opacity": "0.5"
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
type           | true      | string  |         | Cta type. Must be "CtaHtml".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
html       | true      | string |         | Html code.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | true      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | true      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
background_color | true      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | true      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
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

## Update a cta html

```shell
curl http://localhost:3500/api/v1/ctas/7 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "new name",
  "options": {
    "position": "outside",
    "left": "99%",
    "width": "50%"
  }
}
```

> Example Response

```json
{
  "id": 7,
  "name": "new name",
  "type": "CtaHtml",
  "position_order": 7,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "html": "<div>Htmlcode</div>",
  "position": "outside",
  "left": "99%",
  "top": "30%",
  "width": "50%",
  "height": "30%",
  "background_color": "255,255,255",
  "background_opacity": "0.5"
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be updated.
name           | false      | string  |         | Cta name
position_order | false      | integer |         | Position in the queue when cta is displayed.
options        | false      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | false      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left  | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top   | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width | false      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | false      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
background_color | false      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.


### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
