# Folders

## The folder object

> Example Response

```json
{
  "folder": {
    "id": 1,
    "name": "First folder",
    "created_at": "2017-04-25T22:00:47.046700",
    "updated_at": "2017-04-25T22:00:47.046700",
    "subfolders": [
      {
        "id": 3,
        "name": "Subfolder",
        "created_at": "2017-04-25T22:00:47.046700",
        "updated_at": "2017-04-25T22:00:47.046700",
        "projects_count": 0
      }
    ],
    "projects_count": 5
  }
}
```

Parameter | Type | Description
--------- | ---- | -----------
id | integer | The identifier of the folder.
name | string | Folder name
created_at | string | The date and time the folder was created.
created_at | string | The date and time the folder was updated.
subfolders | array of hashes | Subfolders included in the folder
projects_count | integer | Projects count inside the folder

<!-- /////////////////////////// FOLDERS /////////////////////////// -->

## List all folders

```shell
curl http://localhost:3500/v1/folders \
  -d api_key=test_key
```

> Example Response

```json
{
  "folders": [
    {
      "id": 1,
      "name": "First folder",
      "created_at": "2017-04-25T22:00:47.046700",
      "updated_at": "2017-04-25T22:00:47.046700",
      "subfolders": [],
      "projects_count": 5
    },
    {
      "id": 2,
      "name": "Second folder",
      "created_at": "2017-04-25T22:00:47.047560",
      "updated_at": "2017-04-25T22:00:47.047560",
      "subfolders": [
        {
          "id": 3,
          "name": "Subfolder",
          "created_at": "2017-04-25T22:00:47.046700",
          "updated_at": "2017-04-25T22:00:47.046700",
          "projects_count": 0
        }
      ],
      "projects_count": 2
    }
  ]
}
```

This endpoint retrieves all folders.

### HTTP Request

`GET http://localhost:3500/v1/folders`

### Returns
Returns a list of your folders if the call succeeded.

<!-- /////////////////////////// SPECIFIC FOLDER /////////////////////////// -->

## Retrieve a folder

```shell
curl http://localhost:3500/v1/folders/2 \
  -d api_key=test_key
```

> Example Response

```json
{
  "folder": {
    "id": 2,
    "name": "Second folder",
    "created_at": "2017-04-25T22:00:47.047560",
    "updated_at": "2017-04-25T22:00:47.047560",
    "subfolders": [
      {
        "id": 3,
        "name": "Subfolder",
        "created_at": "2017-04-25T22:00:47.046700",
        "updated_at": "2017-04-25T22:00:47.046700",
        "projects_count": 0
      }
    ],
    "projects_count": 2
  }
}
```

This endpoint retrieves a specific folder.

### HTTP Request

`GET http://localhost:3500/v1/folders/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the folder to be retrived.

### Returns
Returns a folder object if the call succeeded. If the folder ID does not exist, this call returns an error.

<!-- /////////////////////////// CREATE FOLDER /////////////////////////// -->

## Create a folder

```shell
curl http://localhost:3500/v1/folders \
  -d api_key=test_key \
  -d name="Some folder"
```

> Example Response

```json
{
  "folder": {
    "id": 1,
    "name": "Some folder",
    "created_at": "2017-04-25T22:00:47.047560",
    "updated_at": "2017-04-25T22:00:47.047560",
    "projects_count": 0
  }
}
```

This endpoint create a specific folder.

### HTTP Request

`POST http://localhost:3500/v1/folders`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name       | true      | string  |         | Folder name
parent_id  | false     | integer | nil     | The identifier of the parent folder.

### Returns
Returns a folder object if the call succeeded. If a parent folder id is provided and does not exist or available, the call will return an error.

<!-- /////////////////////////// UPDATE FOLDER /////////////////////////// -->

## Update a folder

```shell
curl http://localhost:3500/v1/folders/1 \
  -d api_key=test_key \
  -d name="New name"
```

> Example Response

```json
{
  "folder": {
    "id": 1,
    "name": "New name",
    "created_at": "2017-04-25T22:00:47.047560",
    "updated_at": "2017-04-25T22:00:47.047560",
    "projects_count": 0
  }
}
```

This endpoint updates a specific folder.

### HTTP Request

`PATCH/PUT http://localhost:3500/v1/folders/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the folder to be updated.
name       | true      | string  |         | Folder name
parent_id  | false     | integer | nil     | The identifier of the parent folder.

### Returns
Returns the folder object if the update succeeded. Returns an error if update parameters are invalid or the folder ID does not exist.

<!-- /////////////////////////// DELETE FOLDER /////////////////////////// -->

## Delete a folder

```shell
curl http://localhost:3500/v1/folders/1 \
  -d api_key=test_key
  -X DELETE
```
> Example Response

```json
204 NO CONTENT
```

This endpoint deletes a specific folder.

### HTTP Request

`DELETE http://localhost:3500/v1/folders/<ID>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
id         | true      | integer |         | The identifier of the folder to be deleted.

### Returns
Returns 204 NO CONTENT HTTP status code on success. If the folder ID does not exist, this call returns an error.
