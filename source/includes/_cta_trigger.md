# Cta Trigger

## The cta Trigger object

> Example Response

```json
{
  "id": 8,
  "name": "cta-8",
  "type": "CtaTrigger",
  "position_order": 8,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "trigger_cuepoints": [
    {
      "id": 1,
      "action": "percentage_viewed",
      "cta_purchase_id": null,
      "parameter": "equals",
      "percentage": "1"
    }
  ],
  "trigger_providers": [
    {
      "id": 2,
      "action": "add_list",
      "event_name": null,
      "forms": null,
      "integration_id": 2,
      "integration_provider": "aweber",
      "js_code": null,
      "list": [
        {
          "id": 24,
          "name": "test_name"
        }
      ],
      "lists": null,
      "main_action": "automation",
      "sequences": null,
      "tags": null,
      "tags_list": null,
      "tags_names": null
    }
  ]
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
trigger_cuepoints | array of hashes | Trigger cuepoints.
trigger_providers | array of hashes | Trigger providers.

Trigger cuepoints

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the trigger cuepoint.
action | string | Trigger cuepoints action.
parameter | string | Trigger parameter.
percentage | string | Percentage.
cta_purchase_id | integer | The identifier of the cta purchase.

Trigger providers

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the trigger provider.
action | string | Trigger provider action.
main_action | string | Trigger main action.
event_name | string | Event name.
js_code | string | Javascript code.
integration_id | integer | The identifier of the integration.
integration_provider | string | Integration provider name.
list | hash | List integration field.
lists | array of hashes | Lists integration field.
tags_names | array of strings | Tags names integration field.
forms | array of hashes | Forms integration field.
sequences | array of hashes | Sequences integration field.
tags | array of hashes | Tags integration field.
tags_list | array of hashes | Tags list integration field.

<!-- /////////////////////////// CREATE CTA Trigger /////////////////////////// -->

## Create a cta trigger

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-8",
  "type": "CtaTrigger",
  "position_order": 8,
  "asset_id": 1,
  "options": {
    "trigger_cuepoints": [
      {
        "action": "percentage_viewed",
        "parameter": "equals",
        "percentage": "1"}
    ],
    "trigger_providers": [
      {
        "action": "add_list",
        "integration_id": 2,
        "integration_provider": "aweber",
        "main_action": "automation",
        "list":  [
          {
            "id": 24,
            "name": "test_name"
          }
        ]
      }
    ]
  }
}
```

> Example Response

```json
{
  "id": 8,
  "name": "cta-8",
  "type": "CtaTrigger",
  "position_order": 8,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "trigger_cuepoints": [
    {
      "id": 1,
      "action": "percentage_viewed",
      "cta_purchase_id": null,
      "parameter": "equals",
      "percentage": "1"
    }
  ],
  "trigger_providers": [
    {
      "id": 2,
      "action": "add_list",
      "event_name": null,
      "forms": null,
      "integration_id": 2,
      "integration_provider": "aweber",
      "js_code": null,
      "list": [
        {
          "id": 24,
          "name": "test_name"
        }
      ],
      "lists": null,
      "main_action": "automation",
      "sequences": null,
      "tags": null,
      "tags_list": null,
      "tags_names": null
    }
  ]
}
```

This endpoint create a specific cta.

### HTTP Request

`POST http://localhost:3500/api/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. List, lists, tags_names, forms, sequences, tags_list or tags must be included in trigger providers depends on integration if main action is membership or automation.
3. Js code must be included in trigger providers if main action is fire_js.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaTrigger".
position_order | true      | integer |         | Position in the queue when cta is displayed.
asset_id       | true      | integer |         | The identifier of the asset.
options        | true      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
trigger_cuepoints | true | array of hashes | | Trigger cuepoints.
trigger_providers | true | array of hashes | | Trigger providers.

Trigger cuepoints

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger cuepoints action. Must be "percentage_viewed" or "purchased".
parameter | true | string | | Trigger parameter. Must be "does_not_equal", "equal" or "equals".
percentage | true | string | | Percentage.
cta_purchase_id | false | integer | | The identifier of the cta purchase.

Trigger provides

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger providers action. Must be add_tag", "remove_tag", "add_tag_object", "remove_tag_object", "add_event", "add_form", "add_sequence", "add_list", "remove_list" or "add_member".
main_action | true | string | | Trigger main action. Must be "membership", "fire_js" or "automation".
event_name | false | string | | Event name.
js_code | false | string | | Javascript code. Must be
integration_id | false | integer | | The identifier of the integration.
integration_provider | false | string | | Integration provider name.
list | false | hash | | List integration field.
lists | false | array of hashes | | Lists integration field.
tags_names | false | array of strings | | Tags names integration field.
forms | false | array of hashes | | Forms integration field.
sequences | false | array of hashes | | Sequences integration field.
tags | false | array of hashes | | Tags integration field.
tags_list | false | array of hashes | | Tags list integration field.

### Returns
Returns a cta object if the call succeeded. If a parent cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta trigger

```shell
curl http://localhost:3500/api/v1/ctas/8 \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "new name"
}
```

> Example Response

```json
{
  "id": 8,
  "name": "new name",
  "type": "CtaTrigger",
  "position_order": 8,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "trigger_cuepoints": [
    {
      "id": 1,
      "action": "percentage_viewed",
      "cta_purchase_id": null,
      "parameter": "equals",
      "percentage": "1"
    }
  ],
  "trigger_providers": [
    {
      "id": 2,
      "action": "add_list",
      "event_name": null,
      "forms": null,
      "integration_id": 2,
      "integration_provider": "aweber",
      "js_code": null,
      "list": [
        {
          "id": 24,
          "name": "test_name"
        }
      ],
      "lists": null,
      "main_action": "automation",
      "sequences": null,
      "tags": null,
      "tags_list": null,
      "tags_names": null
    }
  ]
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT http://localhost:3500/api/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. List, lists, tags_names, forms, sequences, tags_list or tags must be included in trigger providers depends on integration if main action is membership or automation.
3. Js code must be included in trigger providers if main action is fire_js.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
position_order | false      | integer |         | Position in the queue when cta is displayed.
options        | false      | hash    |         | Cta options.

Options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
trigger_cuepoints | false | array of hashes | | Trigger cuepoints.
trigger_providers | false | array of hashes | | Trigger providers.

Trigger cuepoints

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger cuepoints action. Must be "percentage_viewed" or "purchased".
parameter | true | string | | Trigger parameter. Must be "does_not_equal", "equal" or "equals".
percentage | true | string | | Percentage.
cta_purchase_id | false | integer | | The identifier of the cta purchase.

Trigger provides

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger providers action. Must be add_tag", "remove_tag", "add_tag_object", "remove_tag_object", "add_event", "add_form", "add_sequence", "add_list", "remove_list" or "add_member".
main_action | true | string | | Trigger main action. Must be "membership", "fire_js" or "automation".
event_name | false | string | | Event name.
js_code | false | string | | Javascript code. Must be
integration_id | false | integer | | The identifier of the integration.
integration_provider | false | string | | Integration provider name.
list | false | hash | | List integration field.
lists | false | array of hashes | | Lists integration field.
tags_names | false | array of strings | | Tags names integration field.
forms | false | array of hashes | | Forms integration field.
sequences | false | array of hashes | | Sequences integration field.
tags | false | array of hashes | | Tags integration field.
tags_list | false | array of hashes | | Tags list integration field.

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
