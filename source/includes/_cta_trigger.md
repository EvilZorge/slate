# Cta Trigger

## The cta Trigger object

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-04T13:03:26.430839",
    "type": "CtaTrigger",
    "trigger_providers": [
      {
        "tags_names": [
          "tag"
        ],
        "tags_list": null,
        "tags": null,
        "sequences": null,
        "main_action": "automation",
        "lists": [
          {
            "name": "list_name",
            "id": 3847967
          }
        ],
        "list": null,
        "js_code": null,
        "integration_provider": "aweber",
        "integration_id": 19,
        "id": 1499172736406,
        "forms": null,
        "event_name": null,
        "action": "add_list"
      }
    ],
    "trigger_cuepoints": [
      {
        "percentage": "10",
        "parameter": "equals",
        "id": 1499172736406,
        "cta_purchase_id": null,
        "action": "percentage_viewed"
      }
    ],
    "project_id": 1,
    "position_order": 13,
    "name": "CtaTrigger 5701",
    "id": 1,
    "created_at": "2017-07-04T13:03:26.430833",
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
curl https://api.optimizeplayer.com/v1/ctas \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
        "cta": {
          "name": "CtaTrigger 5701",
          "asset_id": 1,
          "type": "CtaTrigger",
          "trigger_cuepoints": [
            {
              "id": 1499172736406,
              "action": "percentage_viewed",
              "parameter": "equals",
              "percentage": "10"
            }
          ],
          "trigger_providers": [
            {
              "id": 1499172736406,
              "main_action": "automation",
              "integration_id": 19,
              "integration_provider": "aweber",
              "action": "add_list",
              "lists": [
                {
                  "id": 3847967,
                  "name": "list_name"
                }
              ],
              "tags_names": [
                "tag"
              ]
            }
          ]
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-04T13:03:26.430839",
    "type": "CtaTrigger",
    "trigger_providers": [
      {
        "tags_names": [
          "tag"
        ],
        "tags_list": null,
        "tags": null,
        "sequences": null,
        "main_action": "automation",
        "lists": [
          {
            "name": "list_name",
            "id": 3847967
          }
        ],
        "list": null,
        "js_code": null,
        "integration_provider": "aweber",
        "integration_id": 19,
        "id": 1499172736406,
        "forms": null,
        "event_name": null,
        "action": "add_list"
      }
    ],
    "trigger_cuepoints": [
      {
        "percentage": "10",
        "parameter": "equals",
        "id": 1499172736406,
        "cta_purchase_id": null,
        "action": "percentage_viewed"
      }
    ],
    "project_id": 1,
    "position_order": 13,
    "name": "CtaTrigger 5701",
    "id": 1,
    "created_at": "2017-07-04T13:03:26.430833",
    "asset_id": 1
  }
}
```

This endpoint create a specific cta.

### HTTP Request

`POST https://api.optimizeplayer.com/v1/ctas`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. List, lists, tags_names, forms, sequences, tags_list or tags must be included in trigger providers depends on integration if main action is membership or automation.
3. Js code must be included in trigger providers if main action is fire_js.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name           | true      | string  |         | Cta name
type           | true      | string  |         | Cta type. Must be "CtaTrigger".
asset_id       | true      | integer |         | The identifier of the asset.
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

Trigger providers

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger providers action. Must be add_tag", "remove_tag", "add_tag_object", "remove_tag_object", "add_event", "add_form", "add_sequence", "add_list", "remove_list", "add_member", "add_campaign" or "remove_campaign".
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
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta trigger

```shell
curl https://api.optimizeplayer.com/v1/ctas/1 \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
        "cta": {
          "name": "new_name",
          "trigger_providers": [
            {
              "id": 1499172736406б
              "main_action": "fire_js",
              "js_code": "console.log(123)"
            }
          ],
          "trigger_cuepoints": [
            {
              "id": 1499172736406,
              "percentage": "40",
              "parameter": "equals",
              "action": "percentage_viewed"
            }
          ]
        },
        "api_key": "your_api_key"
      }'
```

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-04T17:17:26.451009",
    "type": "CtaTrigger",
    "trigger_providers": [
      {
        "tags_names": null,
        "tags_list": null,
        "tags": null,
        "sequences": null,
        "main_action": "fire_js",
        "lists": null,
        "list": null,
        "js_code": "console.log(123)",
        "integration_provider": null,
        "integration_id": null,
        "id": 1499172736406,
        "forms": null,
        "event_name": null,
        "action": null
      }
    ],
    "trigger_cuepoints": [
      {
        "percentage": "40",
        "parameter": "equals",
        "id": 1499172736406,
        "cta_purchase_id": null,
        "action": "percentage_viewed"
      }
    ],
    "project_id": 1,
    "position_order": 13,
    "name": "new_name",
    "id": 1,
    "created_at": "2017-07-04T13:03:26.430833",
    "asset_id": 1
  }
}
```

This endpoint updates a specific cta.

### HTTP Request

`PATCH/PUT https://api.optimizeplayer.com/v1/ctas/<ID>`

### Request body parameters

1. on_pause or on_start or on_finish or on_cuepoints and cuepoints must be included.
2. List, lists, tags_names, forms, sequences, tags_list or tags must be included in trigger providers depends on integration if main action is membership or automation.
3. Js code must be included in trigger providers if main action is fire_js.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
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

Trigger providers

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | Current unix timestamp.
action | true | string | | Trigger providers action. Must be add_tag", "remove_tag", "add_tag_object", "remove_tag_object", "add_event", "add_form", "add_sequence", "add_list", "remove_list", "add_member", "add_campaign" or "remove_campaign".
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
