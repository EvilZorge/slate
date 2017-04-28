# Cta Optin

## The cta optin object

> Example Response

```json
{
  "id": 2,
  "name": "cta-2",
  "type": "CtaOptin",
  "position_order": 2,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "integration_id": 2
  "background_color": "255,255,255",
  "background_opacity": "0.6",
  "button_background_color": "255,255,255,255",
  "button_background_opacity": "0.5",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "form": nil,
  "fullscreen": false,
  "header_text": "header_text",
  "height": "30%",
  "left": "30%",
  "list": {
    id: "108c878f10",
    name: "Ecommerce Notebook"
  },
  "lists": nil,
  "name_field": false,
  "notice_text": "We promise not to send you any spam.",
  "notification_option": "none",
  "notification_text": "notification_text",
  "notification_url": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "sequence": nil,
  "skip": false,
  "smart": false,
  "tags": nil,
  "tags_names": nil,
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
created_at | string | The date and time the cta was updated.
integration_id | integer | The identifier of the integration.
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
font_family | string | Text font family.
font_style | string | Text font style.
font_size | string | Text font size.
text_color | string | Text color.
text_opacity | string | Text opacity.
background_color | string | Cta background color.
background_opacity | string | Cta background opacity.
button_background_color | string | Button background color.
button_background_opacity | string | Button background opacity.
text | string | Optin text.
header_text | string | Header text.
notice_text | string | Notice text.
notification_text | string | Notification text. Notification option must be "custom".
notification_url | string | Notification url. Notification option must be "url".
notification_option | string | Notification option. Must be "custom", "url" or "".
name_field | boolean | Add fields for first and last names.
list | hash | List integration field.
lists | array of hashes | Lists integration field.
tags_names | array of strings | Tags names integration field.
form | hash | Form integration field.
sequence | hash | Sequence integration field.
tags | array of hashes| Tags integration field.


<!-- /////////////////////////// CREATE CTA OPTIN /////////////////////////// -->

## Create a cta optin

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-2",
  "type": "CtaOptin",
  "position_order": 2,
  "asset_id": 1,
  "options": {
    "on_start": true,
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%",
    "text": "text",
    "font_family": "Roboto",
    "font_style": "none",
    "font_size": "30px",
    "text_color": "255,255,255",
    "text_opacity": "0.6",
    "background_color": "255,255,255",
    "background_opacity": "0.6",
    "button_background_color": "255,255,255,255",
    "button_background_opacity": "0.5",
    "header_text": "header_text",
    "notification_text": "notification_text",
    "notification_option": "none",
    "notification_url": "http://google.com",
    notice_text: "We promise not to send you any spam.",
    "name_field": false,
    "list": {id: "108c878f10", name: "Ecommerce Notebook"}
  }
}
```

> Example Response

```json
{
  "id": 2,
  "name": "cta-2",
  "type": "CtaOptin",
  "position_order": 2,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "integration_id": 2
  "background_color": "255,255,255",
  "background_opacity": "0.6",
  "button_background_color": "255,255,255,255",
  "button_background_opacity": "0.5",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "form": nil,
  "fullscreen": false,
  "header_text": "header_text",
  "height": "30%",
  "left": "30%",
  "list": {
    id: "108c878f10",
    name: "Ecommerce Notebook"
  },
  "lists": nil,
  "name_field": false,
  "notice_text": "We promise not to send you any spam.",
  "notification_option": "none",
  "notification_text": "notification_text",
  "notification_url": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "sequence": nil,
  "skip": false,
  "smart": false,
  "tags": nil,
  "tags_names": nil,
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

1. List, lists, tags_names, form, sequence or tags must be included depends on integration.
2. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaOptin".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
integration_id | true      | integer  |         | The identifier of the integration.
position   | true      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left | true      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top | true      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | true      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height | true      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
font_family | true      | string  |         | Text font family. Example: Roboto, Times New Roman.
font_style | true      | string  |         | Text font width. Example: none, 300, 400.
font_size | true      | string  |         | Text font size. Must end with "px". Example: "30px".
text_color  | true      | string  |         | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | true      | string  |         | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
background_color | true      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | true      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_background_color | true      | string  |         | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_background_opacity | true      | string  |         | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
text | false      | string  |         | Optin text.
header_text  | false      | string  |         | Header text.
notice_text | false      | string  |         | Notice text.
notification_text | false | string |     | Notification text. Notification option must be "custom".
notification_url | false | string |     | Notification url. Notification option must be "url".
notification_option | false | string |     | Notification option. Must be "custom", "url" or "".
name_field | false | boolean |     | Add fields for first and last names.
list | false | hash |     | List integration field.
lists | false | array of hashes |     | Lists integration field.
tags_names | false | array of strings |     | Tags names integration field.
form | false | hash |     | Form integration field.
sequence | false | hash |     | Sequence integration field.
tags | false | array of hashes|     | Tags integration field.
on_pause  | false      | string  |         | Display cta on pause.
on_start  | false      | string  |         | Display cta on start.
on_finish | false      | string  |         | Display cta on finish.
fullscreen | false      | string  |         | Fullscreen.
cuepoints  | false      | string  |         | Cuepoints timestamps.
on_cuepoints | false      | string  |         | Display cta on cuepoints.
smart  | false      | string  |         | Smart cta.

### Returns
Returns a cta object if the call succeeded. If a parent cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta optin

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
  "id": 2,
  "name": "new name",
  "type": "CtaOptin",
  "position_order": 2,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "integration_id": 2
  "background_color": "255,255,255",
  "background_opacity": "0.6",
  "button_background_color": "255,255,255,255",
  "button_background_opacity": "0.5",
  "cuepoints": [],
  "font_family": "Roboto",
  "font_size": "30px",
  "font_style": "none",
  "form": nil,
  "fullscreen": false,
  "header_text": "header_text",
  "height": "30%",
  "left": "99%",
  "list": {
    id: "108c878f10",
    name: "Ecommerce Notebook"
  },
  "lists": nil,
  "name_field": false,
  "notice_text": "We promise not to send you any spam.",
  "notification_option": "none",
  "notification_text": "notification_text",
  "notification_url": "http://google.com",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "outside",
  "sequence": nil,
  "skip": false,
  "smart": false,
  "tags": nil,
  "tags_names": nil,
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

1. List, lists, tags_names, form, sequence or tags must be included depends on integration.
2. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be updated.
name           | false      | string  |         | Cta name
position_order | false      | integer |         | Position in the queue when cta is displayed.
options        | false      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
integration_id | false      | integer  |         | The identifier of the integration.
position   | false      | string  |         | Position inside or outside the player. Must be "inside" or "outside"
left  | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | false      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height   | false      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
font_family    | false      | string  |         | Text font family. Example: Roboto, Times New Roman.
font_style  | false      | string  |         | Text font width. Example: none, 300, 400.
font_size  | false      | string  |         | Text font size. Must end with "px". Example: "30px".
text_color | false      | string  |         | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | false      | string  |         | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
background_color  | false      | string  |         | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity  | false      | string  |         | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_background_color          | false      | string  |         | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_background_opacity          | false      | string  |         | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
text  | false      | string  |         | Optin text.
header_text  | false      | string  |         | Header text.
notice_text  | false      | string  |         | Notice text.
notification_text | false | string |    | Notification text. Notification option must be "custom".
notification_url | false | string |     | Notification url. Notification option must be "url".
notification_option | false | string |     | Notification option. Must be "custom", "url" or "".
name_field | false | boolean |    | Add fields for first and last names.
list | false | hash |     | List integration field.
lists | false | array of hashes |     | Lists integration field.
tags_names | false | array of strings |     | Tags names integration field.
form | false | hash |     | Form integration field.
sequence | false | hash |     | Sequence integration field.
tags | false | array of hashes|     | Tags integration field.
on_pause  | false      | string  |         | Display cta on pause.
on_start  | false      | string  |         | Display cta on start.
on_finish | false      | string  |         | Display cta on finish.
fullscreen | false      | string  |         | Fullscreen.
cuepoints  | false      | string  |         | Cuepoints timestamps.
on_cuepoints | false      | string  |         | Display cta on cuepoints.
smart  | false      | string  |         | Smart cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
