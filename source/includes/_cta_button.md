# Cta Button

## The cta button object

> Example Response

```json
{
  "cta": {
    "width": "30%",
    "updated_at": "2017-06-30T21:09:48.533288",
    "type": "CtaButton",
    "top": "75%",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "text": "Button Text",
    "smart": false,
    "skip": false,
    "project_id": 1,
    "position_order": 2,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "new_window": false,
    "name": "cta-1",
    "link": "http://google.com",
    "left": "35%",
    "id": 1,
    "height": "18%",
    "font_style": "300",
    "font_size": "26px",
    "font_family": "Roboto",
    "cuepoints": null,
    "created_at": "2017-06-30T21:09:48.533262",
    "button_style": "rounded",
    "button_bg_opacity": "1",
    "button_bg_color": "24,214,127",
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
curl https://api.optimizeplayer.com/v1/ctas \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
        "cta": {
          "name": "cta-1",
          "type": "CtaButton",
          "asset_id": 1,
          "link": "http://google.com",
          "on_pause": true
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "width": "30%",
    "updated_at": "2017-06-30T21:09:48.533288",
    "type": "CtaButton",
    "top": "75%",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "text": "Button Text",
    "smart": false,
    "skip": false,
    "project_id": 278,
    "position_order": 2,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "new_window": false,
    "name": "cta-1",
    "link": "http://google.com",
    "left": "35%",
    "id": 1,
    "height": "18%",
    "font_style": "300",
    "font_size": "26px",
    "font_family": "Roboto",
    "cuepoints": null,
    "created_at": "2017-06-30T21:09:48.533262",
    "button_style": "rounded",
    "button_bg_opacity": "1",
    "button_bg_color": "24,214,127",
    "asset_id": 1
  }
}
```

This endpoint create a specific cta.

### HTTP Request

`POST https://api.optimizeplayer.com/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaButton".
asset_id       | true      | integer |         | The identifier of the asset.
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
left | false      | string  | 35%  | Distance from the left edge to cta. Must be in range (0..100).
top  | false      | string  |  75% | Distance from the top edge to cta. Must be in range (0..100).
width  | false      | string  |  30%  | Cta width. Must be in range (0..100).
height  | false      | string  |  18%  | Cta height. Must be in range (0..100).
text  | false      | string  |  Button text  | Button text.
link  | true      | string  |         | The link by which user will be redirected if he clicks on the cta. Must begin with http or https.
font_family | false      | string  |  Roboto  | Text font family. Example: Roboto, Times New Roman.
font_style | false      | string  |  300   | Text font width. Example: none, 300, 400.
font_size | false      | string  |    26px   | Text font size. Must end with "px".
text_color | false      | string  |   255,255,255  | Text color. Must be in rgb format.
text_opacity | false      | string  |   1   | Text opacity. Must be in range (0.0..1.0).
button_bg_color | false      | string  | 24,214,127 | Button background color. Must be in rgb format.
button_bg_opacity | false      | string  |  1  | Button background opacity. Must be in range (0.0..1.0).
button_style | false      | string  |   rounded   | Button appearance. Must be "rounded", "square", "pill", "subtle", "double_light_border", "double_border", "dotted_border", "dashed_border", "black_border", "white_border", "bottom_border".
new_window  | false  | boolean  |  false  | Open link in new window if user clicks on the cta.
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

## Update a cta button

```shell
curl https://api.optimizeplayer.com/v1/ctas/1 \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
        "cta": {
          "name": "new name",
          "position": "outside",
          "left": "99%",
          "width": "50%"
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "width": "50%",
    "updated_at": "2017-06-30T21:13:53.579686",
    "type": "CtaButton",
    "top": "75%",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "text": "Button Text",
    "smart": false,
    "skip": false,
    "project_id": 1,
    "position_order": 3,
    "position": "outside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "new_window": false,
    "name": "new name",
    "link": "http://google.com",
    "left": "99%",
    "id": 1,
    "height": "18%",
    "font_style": "300",
    "font_size": "26px",
    "font_family": "Roboto",
    "cuepoints": [],
    "created_at": "2017-06-30T21:11:59.035839",
    "button_style": "rounded",
    "button_bg_opacity": "1",
    "button_bg_color": "24,214,127",
    "asset_id": 1
  }
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT https://api.optimizeplayer.com/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be updated.
name           | false      | string  |         | Cta name.
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
left | false      | string  | 35%  | Distance from the left edge to cta. Must be in range (0..100).
top  | false      | string  |  75% | Distance from the top edge to cta. Must be in range (0..100).
width  | false      | string  |  30%  | Cta width. Must be in range (0..100).
height  | false      | string  |  18%  | Cta height. Must be in range (0..100).
text  | false      | string  |  Button text  | Button text.
link  | false      | string  |         | The link by which user will be redirected if he clicks on the cta. Must begin with http or https.
font_family | false      | string  |  Roboto  | Text font family. Example: Roboto, Times New Roman.
font_style | false      | string  |  300   | Text font width. Example: none, 300, 400.
font_size | false      | string  |    26px   | Text font size. Must end with "px".
text_color | false      | string  |   255,255,255  | Text color. Must be in rgb format.
text_opacity | false      | string  |   1   | Text opacity. Must be in range (0.0..1.0).
button_bg_color | false      | string  | 24,214,127 | Button background color. Must be in rgb format.
button_bg_opacity | false      | string  |  1  | Button background opacity. Must be in range (0.0..1.0).
button_style | false      | string  |   rounded   | Button appearance. Must be "rounded", "square", "pill", "subtle", "double_light_border", "double_border", "dotted_border", "dashed_border", "black_border", "white_border", "bottom_border".
new_window  | false  | boolean  |  false  | Open link in new window if user clicks on the cta.
on_pause  | false      | boolean  |  false  | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false   | Display cta on finish.
on_cuepoints | false      | boolean  |   false   | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  [] | Cuepoints timestamps.
smart  | false      | boolean  |  false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
