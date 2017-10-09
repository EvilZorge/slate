# Cta Optin

## The cta optin object

> Example Response

```json
{
  "cta": {
    "font_size": "24px",
    "button_background_opacity": "1",
    "tags": null,
    "on_finish": false,
    "on_pause": false,
    "on_start": true,
    "position": "inside",
    "form": null,
    "created_at": "2017-06-30T22:33:28.596150",
    "id": 1,
    "updated_at": "2017-06-30T22:33:28.596157",
    "background_opacity": "0.8",
    "name_field": false,
    "tags_names": null,
    "integration_id": 42,
    "sequence": null,
    "text_color": "255,255,255",
    "position_order": 6,
    "asset_id": 1,
    "smart": false,
    "lists": null,
    "notification_option": "none",
    "header_text": "header_text",
    "notice_text": "We promise not to send you any spam.",
    "project_id": 278,
    "cuepoints": [],
    "type": "CtaOptin",
    "skip": true,
    "text_opacity": "1",
    "name": "cta-2",
    "notification_text": "notification_text",
    "button_background_color": "36,178,99",
    "text": "Play Video",
    "background_color": "0,0,0",
    "notification_url": null,
    "list": {
      "name": "destin_owners",
      "id": "id"
    },
    "on_cuepoints": false
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
integration_id | integer | The identifier of the integration.
position | string | Position inside or outside the player.
cuepoints | array of arrays | Cuepoints timestamps.
skip | boolean | Opportunity to skip cta.
smart | boolean | Smart cta.
on_pause | boolean | Display cta on pause.
on_start | boolean | Display cta on start.
on_finish | boolean | Display cta on finish.
on_cuepoints | boolean | Display cta on cuepoints.
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
curl http://localhost:3500/v1/ctas \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
        "cta": {
          "name": "cta-2",
          "type": "CtaOptin",
          "asset_id": 1,
          "integration_id": 42,
          "on_start": true,
          "header_text": "header_text",
          "notification_text": "notification_text",
          "list": {
            "id": "id",
            "name": "destin_owners"
          }
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "font_size": "24px",
    "button_background_opacity": "1",
    "tags": null,
    "on_finish": false,
    "on_pause": false,
    "on_start": true,
    "position": "inside",
    "form": null,
    "created_at": "2017-06-30T22:33:28.596150",
    "id": 1,
    "updated_at": "2017-06-30T22:33:28.596157",
    "background_opacity": "0.8",
    "name_field": false,
    "tags_names": null,
    "integration_id": 42,
    "sequence": null,
    "text_color": "255,255,255",
    "position_order": 6,
    "asset_id": 1,
    "smart": false,
    "lists": null,
    "notification_option": "none",
    "header_text": "header_text",
    "notice_text": "We promise not to send you any spam.",
    "project_id": 1,
    "cuepoints": [],
    "type": "CtaOptin",
    "skip": true,
    "text_opacity": "1",
    "name": "cta-2",
    "notification_text": "notification_text",
    "button_background_color": "36,178,99",
    "text": "Play Video",
    "background_color": "0,0,0",
    "notification_url": null,
    "list": {
      "name": "destin_owners",
      "id": "id"
    },
    "on_cuepoints": false
  }
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/v1/ctas`

### Request body parameters

1. List, lists, tags_names, form, sequence or tags must be included depends on integration.
2. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaOptin".
asset_id       | true      | integer |         | The identifier of the asset.
integration_id | true      | integer  |         | The identifier of the integration.
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
font_size | false  | string  |  24px | Text font size. Must end with "px". Example: "30px".
text_color  | false  | string  |  255,255,255   | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | false      | string  |   1  | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
background_color | false  | string  |  0,0,0 | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false  | string  |   0.8   | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_background_color | false   | string  |  36,178,99   | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_background_opacity | false      | string  |  1  | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
text | false  | string  |   Play Video    | Optin text.
header_text  | false  | string  |  Enter your email address to play the video  | Header text.
notice_text | false  | string  |  We promise not to send you any spam.  | Notice text.
notification_text | false | string |  Thank you for submitting | Notification text. Notification option must be "custom".
notification_url | false | string |     | Notification url. Notification option must be "url".
notification_option | false | string | none | Notification option. Must be "custom", "url" or "none".
name_field | false | boolean |  false  | Add fields for first and last names.
list | false | hash |     | List integration field.
lists | false | array of hashes |     | Lists integration field.
tags_names | false | array of strings |     | Tags names integration field.
form | false | hash |     | Form integration field.
sequence | false | hash |     | Sequence integration field.
tags | false | array of hashes|     | Tags integration field.
on_pause  | false      | boolean  |  false   | Display cta on pause.
on_start  | false      | boolean  |  false   | Display cta on start.
on_finish | false      | boolean  |  false | Display cta on finish.
on_cuepoints | false      | boolean  |  false | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []   | Cuepoints timestamps.
smart  | false      | boolean  |  false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta optin

```shell
curl http://localhost:3500/v1/ctas/1 \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
        "cta": {
          "name": "new name",
          "position": "outside",
          "notice_text": "Notice text"
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "font_size": "24px",
    "button_background_opacity": "1",
    "tags": null,
    "on_finish": false,
    "on_pause": false,
    "on_start": true,
    "position": "outside",
    "form": null,
    "created_at": "2017-06-30T22:33:28.596150",
    "id": 1,
    "updated_at": "2017-06-30T22:36:52.051609",
    "background_opacity": "0.8",
    "name_field": false,
    "tags_names": null,
    "integration_id": 42,
    "sequence": null,
    "text_color": "255,255,255",
    "position_order": 6,
    "asset_id": 1,
    "smart": false,
    "lists": null,
    "notification_option": "none",
    "header_text": "header_text",
    "notice_text": "Notice text",
    "project_id": 1,
    "cuepoints": [],
    "type": "CtaOptin",
    "skip": true,
    "text_opacity": "1",
    "name": "new name",
    "notification_text": "notification_text",
    "button_background_color": "36,178,99",
    "text": "Play Video",
    "background_color": "0,0,0",
    "notification_url": null,
    "list": {
      "name": "destin_owners",
      "id": "id"
    },
    "on_cuepoints": false
  }
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/v1/ctas/<ID>`

### Request body parameters

1. List, lists, tags_names, form, sequence or tags must be included depends on integration.
2. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be updated.
name           | false      | string  |         | Cta name
integration_id | false      | integer  |         | The identifier of the integration.
position   | false      | string  |  inside   | Position inside or outside the player. Must be "inside" or "outside"
font_size | false  | string  |  24px | Text font size. Must end with "px". Example: "30px".
text_color  | false  | string  |  255,255,255   | Text color. Must be in rgb format. Example: "100, 156, 144".
text_opacity | false      | string  |   1  | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
background_color | false  | string  |  0,0,0 | Background color. Must be in rgb format. Example: "100, 156, 144".
background_opacity | false  | string  |   0.8   | Background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_background_color | false   | string  |  36,178,99   | Button background color. Must be in rgb format. Example: "100, 156, 144".
button_background_opacity | false      | string  |  1  | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
text | false  | string  |   Play Video    | Optin text.
header_text  | false  | string  |  Enter your email address to play the video  | Header text.
notice_text | false  | string  |  We promise not to send you any spam.  | Notice text.
notification_text | false | string |  Thank you for submitting | Notification text. Notification option must be "custom".
notification_url | false | string |     | Notification url. Notification option must be "url".
notification_option | false | string | none | Notification option. Must be "custom", "url" or "none".
name_field | false | boolean |  false  | Add fields for first and last names.
list | false | hash |     | List integration field.
lists | false | array of hashes |     | Lists integration field.
tags_names | false | array of strings |     | Tags names integration field.
form | false | hash |     | Form integration field.
sequence | false | hash |     | Sequence integration field.
tags | false | array of hashes|     | Tags integration field.
on_pause  | false      | boolean  |  false   | Display cta on pause.
on_start  | false      | boolean  |  false   | Display cta on start.
on_finish | false      | boolean  |  false | Display cta on finish.
on_cuepoints | false      | boolean  |  false | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []   | Cuepoints timestamps.
smart  | false      | boolean  |  false | Smart cta.
skip  | false      | boolean  | true | Opportunity to skip cta.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
