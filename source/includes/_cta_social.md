# Cta Social

## The cta social object

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:07:20.806118",
    "type": "CtaSocial",
    "smart": false,
    "skip": true,
    "share_title": "share_title",
    "share_method": "embed",
    "share_link": "http://google.com",
    "share_image": "http://google.com",
    "share_description": "desc",
    "share_caption": null,
    "share_button": "share_facebook",
    "project_id": 1,
    "position_order": 7,
    "position": "inside",
    "popup_text_opacity": "1",
    "popup_text_color": "255,255,255",
    "popup_text": "Please Share This Video",
    "popup_notice_text": "The video will continue playing once you click the button below",
    "button_text": null,
    "opacity": "1",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-3",
    "id": 1,
    "font_size": "14px",
    "cuepoints": [],
    "created_at": "2017-07-01T00:07:20.806074",
    "color": "130,196,236",
    "background_opacity": "0.9",
    "background_color": "29,161,242",
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
position | string | Position inside or outside the player.
cuepoints | array of arrays | Cuepoints timestamps.
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
font_size | string | Text font size.
background_color | string | Background color.
background_opacity | string | Background opacity.
color | string | Text color.
opacity | string | Text opacity.
popup_text | string | Popup text.
popup_notice_text | string | Popup notice text.
button_text | string | Button text.
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
 "cta": {
    "name": "cta-3",
    "type": "CtaSocial",
    "asset_id": 1,
    "share_title": "share_title",
    "share_description": "desc",
    "share_link": "http://google.com",
    "share_image": "http://google.com",
    "share_button": "share_facebook",
    "on_pause": true
  }
}
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:07:20.806118",
    "type": "CtaSocial",
    "smart": false,
    "skip": true,
    "share_title": "share_title",
    "share_method": "embed",
    "share_link": "http://google.com",
    "share_image": "http://google.com",
    "share_description": "desc",
    "share_caption": null,
    "share_button": "share_facebook",
    "project_id": 1,
    "position_order": 7,
    "position": "inside",
    "popup_text_opacity": "1",
    "popup_text_color": "255,255,255",
    "popup_text": "Please Share This Video",
    "popup_notice_text": "The video will continue playing once you click the button below",
    "button_text": null,
    "opacity": "1",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-3",
    "id": 1,
    "font_size": "14px",
    "cuepoints": [],
    "created_at": "2017-07-01T00:07:20.806074",
    "color": "130,196,236",
    "background_opacity": "0.9",
    "background_color": "29,161,242",
    "asset_id": 1
  }
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
asset_id       | true      | integer |         | The identifier of the asset.
position   | false      | string  |  inside | Position inside or outside the player. Must be "inside" or "outside"
font_size  | false      | string  |  14px   | Text font size. Must end with "px". Example: "30px".
background_color  | false      | string  |  29,161,242   | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity  | false      | string  |  0.9 | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
color | false | string |  130,196,236 | Text color. Must be in rgb format. Example: "100, 156, 144".
opacity | false | string | 1  | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
popup_text | false | string |  Please Share This Video | Popup text.
popup_notice_text | false | string | The video will continue playing once you click the button below | Popup notice text.
button_text | false | string | | Button text.
popup_text_color | false | string |  255,255,255  | Popup text color. Must be in rgb format. Example: "100, 156, 144".
popup_text_opacity | false | string |  1  | Popup text opacity. Must be in range (0.0..1.0). Example: "0.5".
share_button | true | string |     | Share button. Must be "facebook" or "twitter".
share_title | true | string |     | Title text.
share_image | true | string |     | Image link.
share_method | false | string |  embed   | Buttons link to. Must be "page" or "embed".
share_description | false | string |     | Description text.
share_link | false | string |     | Share link if share_method is "page".
share_caption | false | string |     | Share caption.
on_pause  | false      | boolean  | false | Display cta on pause.
on_start  | false      | boolean  | false | Display cta on start.
on_finish | false      | boolean  | false | Display cta on finish.
on_cuepoints | false      | boolean  |  false | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  | false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.


### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta social

```shell
curl http://localhost:3500/api/v1/ctas/1 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
 "cta": {
    "name": "new name",
    "position": "outside",
    "share_button": "share_twitter"
  }
}
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-01T00:09:31.795840",
    "type": "CtaSocial",
    "smart": false,
    "skip": true,
    "share_title": "share_title",
    "share_method": "embed",
    "share_link": "http://google.com",
    "share_image": "http://google.com",
    "share_description": "desc",
    "share_caption": null,
    "share_button": "share_twitter",
    "project_id": 1,
    "position_order": 7,
    "position": "outside",
    "popup_text_opacity": "1",
    "popup_text_color": "255,255,255",
    "popup_text": "Please Share This Video",
    "popup_notice_text": "The video will continue playing once you click the button below",
    "button_text": null,
    "opacity": "1",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "new name",
    "id": 1,
    "font_size": "14px",
    "cuepoints": [],
    "created_at": "2017-07-01T00:07:20.806074",
    "color": "130,196,236",
    "background_opacity": "0.9",
    "background_color": "29,161,242",
    "asset_id": 1
  }
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
position   | false      | string  |  inside | Position inside or outside the player. Must be "inside" or "outside"
font_size  | false      | string  |  14px   | Text font size. Must end with "px". Example: "30px".
background_color  | false      | string  |  29,161,242   | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity  | false      | string  |  0.9 | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
color | false | string |  130,196,236 | Text color. Must be in rgb format. Example: "100, 156, 144".
opacity | false | string | 1  | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
popup_text | false | string |  Please Share This Video | Popup text.
popup_notice_text | false | string | The video will continue playing once you click the button below | Popup notice text.
button_text | false | string | | Button text.
popup_text_color | false | string |  255,255,255  | Popup text color. Must be in rgb format. Example: "100, 156, 144".
popup_text_opacity | false | string |  1  | Popup text opacity. Must be in range (0.0..1.0). Example: "0.5".
share_button | false | string |     | Share button. Must be "facebook" or "twitter".
share_title | false | string |     | Title text.
share_image | false | string |     | Image link.
share_method | false | string | embed | Buttons link to. Must be "page" or "embed".
share_description | false | string |     | Description text.
share_link | false | string |     | Share link if share_method is "page".
share_caption | false | string |     | Share caption.
on_pause  | false      | boolean  | false | Display cta on pause.
on_start  | false      | boolean  | false | Display cta on start.
on_finish | false      | boolean  | false | Display cta on finish.
on_cuepoints | false      | boolean  |  false | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  | false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
