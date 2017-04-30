# Cta Survey

## The cta survey object

> Example Response

```json
{
  "id": 6,
  "name": "cta-6",
  "type": "CtaSurvey",
  "position_order": 6,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "answers_bg_color": "255,255,255",
  "answers_bg_color_opacity": "0.5",
  "button_bg_color": "255,255,255",
  "button_bg_color_opacity": "0.5",
  "button_text_color": "255,255,255",
  "button_text_color_opacity": "0.5",
  "cuepoints": [],
  "fullscreen": false,
  "header_color": "255,255,255",
  "header_color_opacity": "0.5",
  "height": "30%",
  "left": "30%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "skip": false,
  "smart": false,
  "submit_button": "button",
  "submit_text": "text",
  "survey_questions": [
    {
      "id": 1,
      "text": "question",
      "survey_options": [
        {
          "id": 1,
          "text": "answer"
        },
        {
          "id": 2,
          "text": "answer"
        }
      ]
    }
  ]
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
answers_bg_color | string | Answers background color.
answers_bg_color_opacity | string | Answers background opacity.
button_bg_color | string | Button background color.
button_bg_color_opacity | string | Button background opacity.
button_text_color | string | Button text color.
button_text_color_opacity | string | Button text opacity.
header_color | string | Header text color.
header_color_opacity | string | Header text opacity.
submit_button | string | Submit button text.
submit_text | string | Submit text.
survey_questions | hash | Survey questions

Survey questions

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the survey question.
text | string | Question text
survey_options | hash | Survey options

Survey options

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the survey answer.
text | string | Answer text

<!-- /////////////////////////// CREATE CTA BUTTON /////////////////////////// -->

## Create a cta survey

```shell
curl http://localhost:3500/api/v1/ctas \
  -d api_key=test_key
```
> Example Request Body Parameters

```json
{
  "name": "cta-6",
  "type": "CtaSurvey",
  "position_order": 6,
  "asset_id": 1,
  "options": {
    "position": "inside",
    "left": "30%",
    "top": "30%",
    "width": "30%",
    "height": "30%",
    "header_color": "255,255,255",
    "header_color_opacity": "0.5",
    "answers_bg_color": "255,255,255",
    "answers_bg_color_opacity": "0.5",
    "button_bg_color": "255,255,255",
    "button_bg_color_opacity": "0.5",
    "button_text_color": "255,255,255",
    "button_text_color_opacity": "0.5",
    "submit_text": "text",
    "submit_button": "button",
    "survey_questions": [
      {
        "text": "question",
        survey_options: [
          {
            "text": "answer"
          },
          {
            "text": "answer"
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
  "id": 6,
  "name": "cta-6",
  "type": "CtaSurvey",
  "position_order": 6,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "answers_bg_color": "255,255,255",
  "answers_bg_color_opacity": "0.5",
  "button_bg_color": "255,255,255",
  "button_bg_color_opacity": "0.5",
  "button_text_color": "255,255,255",
  "button_text_color_opacity": "0.5",
  "cuepoints": [],
  "fullscreen": false,
  "header_color": "255,255,255",
  "header_color_opacity": "0.5",
  "height": "30%",
  "left": "30%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "skip": false,
  "smart": false,
  "submit_button": "button",
  "submit_text": "text",
  "survey_questions": [
    {
      "id": 1,
      "text": "question",
      "survey_options": [
        {
          "id": 1,
          "text": "answer"
        },
        {
          "id": 2,
          "text": "answer"
        }
      ]
    }
  ]
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
type           | true      | string  |         | Cta type. Must be "CtaSurvey".
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
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.
answers_bg_color | true | string |       | Answers background color.  Must be in rgb format. Example: "100, 156, 144".
answers_bg_color_opacity | true | string |      | Answers background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | true | string |      | Button background color.  Must be in rgb format. Example: "100, 156, 144".
button_bg_color_opacity | true | string |      | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text_color | true | string |      | Button text color.  Must be in rgb format. Example: "100, 156, 144".
button_text_color_opacity | true | string |      | Button text opacity. Must be in range (0.0..1.0). Example: "0.5".
header_color | true | string |      | Header text color.  Must be in rgb format. Example: "100, 156, 144".
header_color_opacity | true | string |      | Header text opacity. Must be in range (0.0..1.0). Example: "0.5".
submit_button | false | string |      | Submit button text.
submit_text | false | string |      | Submit text.
survey_questions | true | arrays of hashes |      | Survey questions.

Survey questions

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | true | string | | Question text
survey_options | true | array of hashes | | Survey answers

Survey questions

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | true | string | | Answer text

### Returns
Returns a cta object if the call succeeded. If a parent cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta survey

```shell
curl http://localhost:3500/api/v1/ctas/6 \
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
  "id": 6,
  "name": "new name",
  "type": "CtaSurvey",
  "position_order": 6,
  "asset_id": 1,
  "project_id": 1,
  "created_at": "2017-04-25T22:00:47.046700",
  "updated_at": "2017-04-25T22:00:47.046700",
  "answers_bg_color": "255,255,255",
  "answers_bg_color_opacity": "0.5",
  "button_bg_color": "255,255,255",
  "button_bg_color_opacity": "0.5",
  "button_text_color": "255,255,255",
  "button_text_color_opacity": "0.5",
  "cuepoints": [],
  "fullscreen": false,
  "header_color": "255,255,255",
  "header_color_opacity": "0.5",
  "height": "30%",
  "left": "99%",
  "on_cuepoints": false,
  "on_finish": false,
  "on_pause": false,
  "on_start": true,
  "position": "inside",
  "skip": false,
  "smart": false,
  "submit_button": "button",
  "submit_text": "text",
  "survey_questions": [
    {
      "id": 1,
      "text": "question",
      "survey_options": [
        {
          "id": 1,
          "text": "answer"
        },
        {
          "id": 2,
          "text": "answer"
        }
      ]
    }
  ]
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
left  | false      | string  |         | Distance from the left edge to cta. Must be in range (0..100). Example: "10%", "25%".
top  | false      | string  |         | Distance from the top edge to cta. Must be in range (0..100). Example: "10%", "25%".
width  | false      | string  |         | Cta width. Must be in range (0..100). Example: "10%", "25%".
height  | false      | string  |         | Cta height. Must be in range (0..100). Example: "10%", "25%".
on_pause  | false      | boolean  |         | Display cta on pause.
on_start  | false      | boolean  |         | Display cta on start.
on_finish | false      | boolean  |         | Display cta on finish.
fullscreen | false      | boolean  |         | Fullscreen.
cuepoints  | false      | array of arrays  |         | Cuepoints timestamps.
on_cuepoints | false      | boolean  |         | Display cta on cuepoints.
smart  | false      | boolean  |         | Smart cta.
answers_bg_color | false | string |       | Answers background color.  Must be in rgb format. Example: "100, 156, 144".
answers_bg_color_opacity | false | string |      | Answers background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | false | string |      | Button background color.  Must be in rgb format. Example: "100, 156, 144".
button_bg_color_opacity | false | string |      | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text_color | false | string |      | Button text color.  Must be in rgb format. Example: "100, 156, 144".
button_text_color_opacity | false | string |      | Button text opacity. Must be in range (0.0..1.0). Example: "0.5".
header_color | false | string |      | Header text color.  Must be in rgb format. Example: "100, 156, 144".
header_color_opacity | false | string |      | Header text opacity. Must be in range (0.0..1.0). Example: "0.5".
submit_button | false | string |      | Submit button text.
submit_text | false | string |      | Submit text.
survey_questions | false | arrays of hashes |      | Survey questions.

Survey questions

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the question.
text | false | string | | Question text
survey_options | false | array of hashes | | Survey answers

Survey options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id | true | integer | | The identifier of the answer.
text | false | string | | Answer text

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
