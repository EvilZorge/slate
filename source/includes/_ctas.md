# Ctas

## List all ctas

```shell
curl http://localhost:3500/api/v1/ctas \
  -d asset_id=1
  -d api_key=test_key
```

> Example Response

```json
{
  "ctas": [
    {
      "id": 1,
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
    },
    {
      "id": 2,
      "font_size": "24px",
      "button_background_opacity": "1",
      "tags": null,
      "on_finish": false,
      "on_pause": false,
      "on_start": true,
      "position": "inside",
      "form": null,
      "created_at": "2017-06-30T22:33:28.596150",
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
    },
    ...
  ]
}

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
  "cta": {
    "id": 2,
    "font_size": "24px",
    "button_background_opacity": "1",
    "tags": null,
    "on_finish": false,
    "on_pause": false,
    "on_start": true,
    "position": "inside",
    "form": null,
    "created_at": "2017-06-30T22:33:28.596150",
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
