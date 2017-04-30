# Cta Button

## The cta button object

> Example Response

```json
{
  "id": 1,
  "name": "cta-1",
  "type": "CtaButton",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "button_style": "rounded",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "fullscreen": false,
  "height": "30%",
  "left": "30%",
  "link": "http://google.com",
  "new_window": false,
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "skip": false,
  "smart": false,
  "text": "text",
  "text_color": "255,255,255",
  "text_opacity": "0.6",
  "top": "30%",
  "width": "30%"
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
width | string | Cta width.
height | string | Cta height.
position | string | Position inside or outside the player.
cuepoints | array of arrays | Cuepoints timestamps.
link | string | The link by which user will be redirected if he clicks on the cta.
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
fullscreen | boolean | Fullscreen.
text | string | Button text.
font_family | string | Text font family.
font_style | string | Text font style.
font_size | string | Text font size.
text_color | string | Text color.
text_opacity | string | Text opacity.
button_bg_color | string | Button background color.
button_bg_opacity | string | Button background opacity.
button_style | string | Button appearance.
new_window | boolean | Open link in new window if user clicks on the cta.

<!-- /////////////////////////// CREATE CTA BUTTON /////////////////////////// -->

## Create a cta button

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-1",
  "type": "CtaButton",
  "position_order": 1,
  "asset_id": 1,
  "options": {
    "on_start": true,
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%",
    "text": "text",
    "link": "http://google.com",
    "font_family": "Roboto",
    "font_style": "none",
    "font_size": "30px",
    "text_color": "255,255,255",
    "text_opacity": "0.6",
    "button_bg_color": "255,255,255",
    "button_bg_opacity": "0.5",
    "button_style": "rounded"
  }
}
```

> Example Response

```json
{
  "id": 1,
  "name": "cta-1",
  "type": "CtaButton",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "button_style": "rounded",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "fullscreen": false,
  "height": "30%",
  "left": "30%",
  "link": "http://google.com",
  "new_window": false,
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "skip": false,
  "smart": false,
  "text": "text",
  "text_color": "255,255,255",
  "text_opacity": "0.6",
  "top": "30%",
  "width": "30%"
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
type           | true      | string  |         | Cta type. Must be "CtaButton".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | true      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | true      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
text  | true      | string  |         | Button text.
link  | true      | string  |         | The link by which user will be redirected if he clicks on the cta. Must begin with http or https.
font_family | true      | string  |         | Text font family. Example: Roboto, Times New Roman.
font_style | true      | string  |         | Text font width. Example: none, 300, 400.
font_size | true      | string  |         | Text font size. Must end with "px". Example: "30px".
text_color | true      | string  |         | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | true      | string  |         | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | true      | string  |         | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | true      | string  |         | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_style | true      | string  |         | Button appearance. Must be "rounded", "square", "pill", "subtle", "double_light_border", "double_border", "dotted_border", "dashed_border", "black_border", "white_border", "bottom_border".
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

## Update a cta button

```shell
curl http://localhost:3500/api/v1/ctas/1 \
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
  "id": 1,
  "name": "cta-1",
  "type": "CtaButton",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:10:00.046700",
  "button_bg_color": "255,255,255",
  "button_bg_opacity": "0.5",
  "button_style": "rounded",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "fullscreen": false,
  "height": "30%",
  "left": "99%",
  "link": "http://google.com",
  "new_window": false,
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "outside",
  "skip": false,
  "smart": false,
  "text": "text",
  "text_color": "255,255,255",
  "text_opacity": "0.6",
  "top": "30%",
  "width": "50%"
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
text | false      | string  |         | Button text.
link  | false      | string  |         | The link by which user will be redirected if he clicks on the cta. Must begin with http or https.
font_family  | false      | string  |         | Text font family. Example: Roboto, Times New Roman.
font_style | false      | string  |         | Text font width. Example: none, 300, 400.
font_size  | false      | string  |         | Text font size. Must end with "px". Example: "30px".
text_color | false      | string  |         | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | false      | string  |         | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | false      | string  |         | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_bg_opacity | false      | string  |         | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_style | false      | string  |         | Button appearance. Must be "rounded", "square", "pill", "subtle", "double_light_border", "double_border", "dotted_border", "dashed_border", "black_border", "white_border", "bottom_border".
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
