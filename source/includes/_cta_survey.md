# Cta Survey

## The cta survey object

> Example Response

```json
{
  "cta": {
    "updated_at": "2017-07-03T17:07:41.000044",
    "type": "CtaSurvey",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "survey_questions": [
      {
        "text": "question",
        "survey_options": [
          {
            "text": "answer"
          },
          {
            "text": "answer"
          }
        ]
      }
    ],
    "submit_text": "Thanks for filling out the survey. Your responses are appreciated.",
    "submit_button": "Close survey",
    "smart": false,
    "skip": true,
    "project_id": 1,
    "position_order": 10,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-6",
    "id": 1,
    "header_color_opacity": "1",
    "header_color": "255,255,255",
    "cuepoints": [],
    "created_at": "2017-07-03T17:07:41.000002",
    "button_text_color_opacity": "1",
    "button_text_color": "255,255,255",
    "button_text": "Continue",
    "button_bg_color_opacity": "1",
    "button_bg_color": "23,109,61",
    "asset_id": 1,
    "answers_bg_color_opacity": "0.95",
    "answers_bg_color": "36,178,99"
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
text_color | string | Text color.
text_opacity | string | Text opacity.
answers_bg_color | string | Answers background color.
answers_bg_color_opacity | string | Answers background opacity.
button_bg_color | string | Button background color.
button_bg_color_opacity | string | Button background opacity.
button_text_color | string | Button text color.
button_text_color_opacity | string | Button text opacity.
header_color | string | Header text color.
header_color_opacity | string | Header text opacity.
button_text | string | Next question button text.
submit_button | string | Submit button text.
submit_text | string | Submit text.
survey_questions | hash | Survey questions

Survey questions

Parameter | Type | Description
--------- | ---- | -----------
text | string | Question text
survey_options | hash | Survey options

Survey options

Parameter | Type | Description
--------- | ---- | -----------
text | string | Answer text

<!-- /////////////////////////// CREATE CTA SURVEY /////////////////////////// -->

## Create a cta survey

```shell
curl https://api.optimizeplayer.com/v1/ctas \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
        "cta": {
          "name": "cta-6",
          "type": "CtaSurvey",
          "asset_id": 1,
          "on_pause": true,
          "survey_questions": [
            {
              "text": "question",
              "survey_options": [
                {
                  "text": "answer"
                },
                {
                  "text": "answer"
                }
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
    "updated_at": "2017-07-03T17:07:41.000044",
    "type": "CtaSurvey",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "survey_questions": [
      {
        "text": "question",
        "survey_options": [
          {
            "text": "answer"
          },
          {
            "text": "answer"
          }
        ]
      }
    ],
    "submit_text": "Thanks for filling out the survey. Your responses are appreciated.",
    "submit_button": "Close survey",
    "smart": false,
    "skip": true,
    "project_id": 1,
    "position_order": 10,
    "position": "inside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "cta-6",
    "id": 1,
    "header_color_opacity": "1",
    "header_color": "255,255,255",
    "cuepoints": [],
    "created_at": "2017-07-03T17:07:41.000002",
    "button_text_color_opacity": "1",
    "button_text_color": "255,255,255",
    "button_text": "Continue",
    "button_bg_color_opacity": "1",
    "button_bg_color": "23,109,61",
    "asset_id": 1,
    "answers_bg_color_opacity": "0.95",
    "answers_bg_color": "36,178,99"
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
type           | true      | string  |         | Cta type. Must be "CtaSurvey".
asset_id       | true      | integer |         | The identifier of the asset.
survey_questions | true | arrays of hashes |      | Survey questions.
position   | false      | string  | inside  | Position inside or outside the player. Must be "inside" or "outside"
on_pause  | false      | boolean  |  false  | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false  | Display cta on finish.
on_cuepoints | false      | boolean  |  false  | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  |  false   | Smart cta.
skip  | false      | boolean  |  true   | Opportunity to skip cta.
text_color | false | string | 255,255,255 | Text color.  Must be in rgb format. Example: "100, 156, 144".
text_opacity | false | string |  1   | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
answers_bg_color | false | string | 36,178,99 | Answers background color.  Must be in rgb format. Example: "100, 156, 144".
answers_bg_color_opacity | false | string | 0.95 | Answers background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | false | string | 23,109,61 | Button background color.  Must be in rgb format. Example: "100, 156, 144".
button_bg_color_opacity | false | string | 1 | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text_color | false | string | 255,255,255 | Button text color.  Must be in rgb format. Example: "100, 156, 144".
button_text_color_opacity | false | string | 1 | Button text opacity. Must be in range (0.0..1.0). Example: "0.5".
header_color | false | string | 255,255,255 | Header text color.  Must be in rgb format. Example: "100, 156, 144".
header_color_opacity | false | string | 1 | Header text opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text | false | string |  Continue | Next question button text.
submit_button | false | string |  Close survey | Submit button text.
submit_text | false | string | Thanks for filling out the survey.  Your responses are appreciated. | Submit text.

Survey questions

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | true | string | | Question text
survey_options | true | array of hashes | | Survey answers

Survey options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | true | string | | Answer text

### Returns
Returns a cta object if the call succeeded. If a cta id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE CTA /////////////////////////// -->

## Update a cta survey

```shell
curl https://api.optimizeplayer.com/v1/ctas/1 \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
        "cta": {
          "name": "new_name",
          "position": "outside",
          "survey_questions": [
            {
              "text": "new_question",
              "survey_options": [
                {
                  "text": "new_answer"
                }
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
    "updated_at": "2017-07-03T17:11:44.696666",
    "type": "CtaSurvey",
    "text_opacity": "1",
    "text_color": "255,255,255",
    "survey_questions": [
      {
        "text": "new_question",
        "survey_options": [
          {
            "text": "new_answer"
          }
        ]
      }
    ],
    "submit_text": "Thanks for filling out the survey. Your responses are appreciated.",
    "submit_button": "Close survey",
    "smart": false,
    "skip": true,
    "project_id": 1,
    "position_order": 10,
    "position": "outside",
    "on_start": false,
    "on_pause": true,
    "on_finish": false,
    "on_cuepoints": false,
    "name": "new_name",
    "id": 1,
    "header_color_opacity": "1",
    "header_color": "255,255,255",
    "cuepoints": [],
    "created_at": "2017-07-03T17:07:41.000002",
    "button_text_color_opacity": "1",
    "button_text_color": "255,255,255",
    "button_text": "Continue",
    "button_bg_color_opacity": "1",
    "button_bg_color": "23,109,61",
    "asset_id": 1,
    "answers_bg_color_opacity": "0.95",
    "answers_bg_color": "36,178,99"
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
id | true | integer | | The identifier of the cta.
name           | false      | string  |         | Cta name
survey_questions | false | arrays of hashes |      | Survey questions.
position   | false      | string  | inside  | Position inside or outside the player. Must be "inside" or "outside"
on_pause  | false      | boolean  |  false  | Display cta on pause.
on_start  | false      | boolean  |  false  | Display cta on start.
on_finish | false      | boolean  |  false  | Display cta on finish.
on_cuepoints | false      | boolean  |  false  | Display cta on cuepoints.
cuepoints  | false      | array of arrays  |  []  | Cuepoints timestamps.
smart  | false      | boolean  |  false   | Smart cta.
skip  | false      | boolean  |  true   | Opportunity to skip cta.
text_color | false | string | 255,255,255 | Text color.  Must be in rgb format. Example: "100, 156, 144".
text_opacity | false | string |  1   | Text opacity. Must be in range (0.0..1.0). Example: "0.5".
answers_bg_color | false | string | 36,178,99 | Answers background color.  Must be in rgb format. Example: "100, 156, 144".
answers_bg_color_opacity | false | string | 0.95 | Answers background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_bg_color | false | string | 23,109,61 | Button background color.  Must be in rgb format. Example: "100, 156, 144".
button_bg_color_opacity | false | string | 1 | Button background opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text_color | false | string | 255,255,255 | Button text color.  Must be in rgb format. Example: "100, 156, 144".
button_text_color_opacity | false | string | 1 | Button text opacity. Must be in range (0.0..1.0). Example: "0.5".
header_color | false | string | 255,255,255 | Header text color.  Must be in rgb format. Example: "100, 156, 144".
header_color_opacity | false | string | 1 | Header text opacity. Must be in range (0.0..1.0). Example: "0.5".
button_text | false | string |  Continue | Next question button text.
submit_button | false | string |  Close survey | Submit button text.
submit_text | false | string | Thanks for filling out the survey.  Your responses are appreciated. | Submit text.
survey_questions | false | arrays of hashes |      | Survey questions.

Survey questions

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | false | string | | Question text
survey_options | false | array of hashes | | Survey answers

Survey options

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
text | false | string | | Answer text

### Returns
Returns the cta object if the update succeeded. Returns an error if update parameters are invalid or the cta ID does not exist.
