# Cta Social

## The cta social object

> Example Response

```json
{
  "id": 3,
  "name": "cta-3",
  "type": "CtaSocial",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "background_color": "255,255,255",
  "background_opacity": "0.5",
  "color": "255,255,255",
  "cuepoints": [],
  "font_size": "30px",
  "fullscreen": false,
  "height": "30%",
  "left": "30%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "opacity": "0.5",
  "popup_text": "text",
  "popup_text_color": "255,255,255",
  "popup_text_opacity": "0.5",
  "position": "inside",
  "share_button": "share_facebook",
  "share_caption": "caption",
  "share_description": "desc",
  "share_image": "http://google.com",
  "share_link": "http://google.com",
  "share_method": "page",
  "share_title": "share_title",
  "skip": false,
  "smart": false,
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
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
fullscreen | boolean | Fullscreen.
font_size | string | Text font size.
background_color | string | Background color.
background_opacity | string | Background opacity.
color | string | Text color.
opacity | string | Text opacity.
popup_text | string | Popup text.
popup_text_color | string | Popup text color.
popup_text_opacity | string | Popup text opacity.
share_button | string | Share button. Must be "facebook" or "twitter".
share_method | string | Buttons link to. Must be "page" or "embed".
share_title | string | Title text.
share_image | string | Image link.
share_description | string | Description text.
share_link | string | Share link if share_method is "page".
share_caption | string | Share caption.

<!-- /////////////////////////// CREATE CTA BUTTON /////////////////////////// -->

## Create a cta social

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-3",
  "type": "CtaSocial",
  "position_order": 1,
  "asset_id": 1,
  "options": {
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%",
    "font_size": "30px",
    "share_title": "share_title",
    "share_description": "desc",
    "share_link": "http://google.com",
    "share_image": "http://google.com",
    "share_caption": "caption",
    "share_button": "share_facebook",
    "share_method": "page",
    "popup_text": "text",
    "popup_text_color": "255,255,255",
    "popup_text_opacity": "0.5",
    "color": "255,255,255",
    "opacity": "0.5",
    "background_color": "255,255,255",
    "background_opacity": "0.5"
  }
}
```

> Example Response

```json
{
  "id": 3,
  "name": "cta-3",
  "type": "CtaSocial",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "background_color": "255,255,255",
  "background_opacity": "0.5",
  "color": "255,255,255",
  "cuepoints": [],
  "font_size": "30px",
  "fullscreen": false,
  "height": "30%",
  "left": "30%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "opacity": "0.5",
  "popup_text": "text",
  "popup_text_color": "255,255,255",
  "popup_text_opacity": "0.5",
  "position": "inside",
  "share_button": "share_facebook",
  "share_caption": "caption",
  "share_description": "desc",
  "share_image": "http://google.com",
  "share_link": "http://google.com",
  "share_method": "page",
  "share_title": "share_title",
  "skip": false,
  "smart": false,
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
type           | true      | string  |         | Cta type. Must be "CtaSocial".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left  | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | true      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | true      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
font_size  | true      | string  |         | Text font size. Must end with "px". Example: "30px".
background_color          | true      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity          | true      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
color | true | string |     | Text color. Must be in rgb format. Example: "100, 156, 144".
opacity | true | string |     | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
popup_text | false | string |    | Popup text.
popup_text_color | true | string |     | Popup text color. Must be in rgb format. Example: "100, 156, 144".
popup_text_opacity | true | string |     | Popup text opacity. Must be in range (0.0..1.0). Example: "0.5".
share_button | true | string |     | Share button. Must be "facebook" or "twitter".
share_method | true | string |     | Buttons link to. Must be "page" or "embed".
share_title | false | string |     | Title text.
share_image | false | string |     | Image link.
share_description | false | string |     | Description text.
share_link | false | string |     | Share link if share_method is "page".
share_caption | false | string |     | Share caption.
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

## Update a cta social

```shell
curl http://localhost:3500/api/v1/ctas/3 \
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
  "id": 3,
  "name": "new name",
  "type": "CtaSocial",
  "position_order": 1,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "background_color": "255,255,255",
  "background_opacity": "0.5",
  "color": "255,255,255",
  "cuepoints": [],
  "font_size": "30px",
  "fullscreen": false,
  "height": "30%",
  "left": "99%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "opacity": "0.5",
  "popup_text": "text",
  "popup_text_color": "255,255,255",
  "popup_text_opacity": "0.5",
  "position": "outside",
  "share_button": "share_facebook",
  "share_caption": "caption",
  "share_description": "desc",
  "share_image": "http://google.com",
  "share_link": "http://google.com",
  "share_method": "page",
  "share_title": "share_title",
  "skip": false,
  "smart": false,
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
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
position_order | false      | integer |         | Position in the queue when cta is displayed.
options        | false      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
position   | false      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left     | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top   | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | false      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | false      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
font_size | false      | string  |         | Text font size. Must end with "px". Example: "30px".
background_color  | false      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
color | false | string |     | Text color. Must be in rgb format. Example: "100, 156, 144".
opacity | false | string |     | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
popup_text | false | string |     | Popup text.
popup_text_color | false | string |     | Popup text color. Must be in rgb format. Example: "100, 156, 144".
popup_text_opacity | false | string |     | Popup text opacity. Must be in range (0.0..1.0). Example: "0.5".
share_button | false | string |     | Share button. Must be "facebook" or "twitter".
share_method | false | string |     | Buttons link to. Must be "page" or "embed".
share_title | false | string |     | Title text.
share_image | false | string |     | Image link.
share_description | false | string |     | Description text.
share_link | false | string |     | Share link if share_method is "page".
share_caption | false | string |     | Share caption.
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
