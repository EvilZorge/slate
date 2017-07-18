# Projects

## Connect

```shell
curl http://localhost:3500/v1/projects/connect \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
      "files": [
        {
          "url": "http://techslides.com/demos/sample-videos/small.mp4",
          "csn_type": "op_hosting"
        },
        {
          "url": "http://techslides.com/demos/sample-videos/small.mp4",
          "csn_type": "amazons3",
          "csn_id": 2
        }
      ],
      "api_key": "your_api_key"
  }'
```

> Example Response

```json
{
  "project_id": 1,
  "assets": [
    {
      "id": 1
    },
    {
      "id": 2
    }
  ]
}
```

This endpoint connect videos to a project or creates a new one.

### HTTP Request

`POST http://localhost:3500/v1/projects/connect`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
api_key | true | string | | Api key.
files | true | array of hashes   |           | Files.
project_id | false | integer  |           | Existing project id.
project_cid | false | string  |           | Existing project cid.

Files array.

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
url   | true      | string |         | Url with video content.
csn_type   | true      | string |         | Integration type. Can be op_hosting, amazons3 or youtube. One request can only contains an amazon's type videos or youtube.
csn_id   | false      | integer |         | Integration id. Required only for integration amazons3.
integration_file_id | false | integer |   | Earlier created integration file id.

### Returns
Returns a project id and assets ids if the call succeeded.

### Possible errors

 Errors |
 ---------- |
 Invalid parameters |
 Project is inaccessible |
 Csn type must be op_hosting, amazons3 or youtube. Files must have same csn type |
 Integration file with id=#{integration_file_id} is unavailable |
 Integration with #{csn_type} type is unavailable |
 #{url} content cannot be found or has been deleted |


## Upload

Max file size is 4GB. Max total size of all files is 20GB.

```shell
curl http://localhost:3500/v1/projects/upload \
  -X POST \
  -F csn_type=op_hosting \
  -F api_key=your_api_key \
  -F 'files[]=@/path/to/file/file.mp4' \
  -F 'files[]=@/path/to/file/some_file.mp4' \
```

> Example Response

```json
{
  "project_id": 2,
  "assets": [
    {
      "id": 1
    },
    {
      "id": 2
    }
  ]
}
```

This endpoint upload videos to a project or creates a new one.

### HTTP Request

`POST http://localhost:3500/v1/projects/connect`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
api_key | true | string | | Api key.
files | true | array |           | Files.
csn_type | true | string | | Integration type. Can be op_hosting or amazons3.
project_id | false | integer  |           | Existing project id.
project_cid | false | string  |           | Existing project cid.

### Returns
Returns a project id and assets ids if the call succeeded.

### Possible errors

 Errors |
 ---------- |
 Invalid parameters |
 Project is inaccessible |
 Csn type must be op_hosting or amazons3. |
 Integration with #{csn_type} type is unavailable |
 #{filename} content type is not a video |
 #{filename} size is too big |
