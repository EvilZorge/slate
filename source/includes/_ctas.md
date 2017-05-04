# Ctas

## List all ctas

```shell
curl http://localhost:3500/api/v1/ctas \
  -d asset_id=1
  -d api_key=test_key
```

> Example Response

```json
[
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
  },
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
    "form": null,
    "fullscreen": false,
    "header_text": "header_text",
    "height": "30%",
    "left": "30%",
    "list": {
      "id": "108c878f10",
      "name": "Ecommerce Notebook"
    },
    "lists": null,
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
    "sequence": null,
    "skip": false,
    "smart": false,
    "tags": null,
    "tags_names": null,
    "text": "text",
    "text_color": "255,255,255",
    "text_opacity": "0.6",
    "top": "30%",
    "width": "30%"
  },
  ...
]
```

This endpoint retrieves all asset's or project's ctas.

### HTTP Request

`GET http://localhost:3500/api/v1/ctas`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
asset_id   | false      | integer |         | The identifier of the asset.
project_id | false      | integer |         | The identifier of the project.

### Returns
Returns a list of asset's or project's ctas if the call succeeded.

<!-- /////////////////////////// SPECIFIC CTA /////////////////////////// -->

## Retrieve a cta

```shell
curl http://localhost:3500/api/v1/ctas/2 \
  -d api_key=test_key
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
  "form": null,
  "fullscreen": false,
  "header_text": "header_text",
  "height": "30%",
  "left": "30%",
  "list": {
    "id": "108c878f10",
    "name": "Ecommerce Notebook"
  },
  "lists": null,
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
  "sequence": null,
  "skip": false,
  "smart": false,
  "tags": null,
  "tags_names": null,
  "text": "text",
  "text_color": "255,255,255",
  "text_opacity": "0.6",
  "top": "30%",
  "width": "30%"
}
```

This endpoint retrieves a specific cta.

### HTTP Request

`GET http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be updated.

### Returns
Returns a cta object if the call succeeded. If the cta ID does not exist, this call returns an error.

<!-- /////////////////////////// DELETE CTA /////////////////////////// -->

## Delete a cta

```shell
curl http://localhost:3500/api/v1/ctas/1 \
  -d api_key=test_key
  -X DELETE
```
> Example Response

```json
204 NO CONTENT
```

This endpoint deletes a specific cta.

### HTTP Request

`DELETE http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the cta to be deleted.

### Returns
Returns 204 NO CONTENT HTTP status code on success. If the cta ID does not exist, this call returns an error.
