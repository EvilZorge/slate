# Accounts

<!-- /////////////////////////// CREATE ACCOUNT /////////////////////////// -->

## Create a account

```shell
curl http://localhost:3500/v1/accounts \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
        "account": {
          "name": "user_name",
          "email": "test@gmail.com"
        },
        "plan_remote_id": "test",
        "api_key": "thirdparty_api_key"
      }'
```

> Example Response

```json
201 CREATED
```

This endpoint create a specific account.

### HTTP Request

`POST http://localhost:3500/v1/accounts`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
plan_remote_id | true | string  |         | Plan remote id.
account  | true | hash |  | Account info.

Account

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
name | true | string  |         | User name.
email  | true | string |       | Email.
company_name  | false | string |       | Account name.

### Returns
Returns 201 CREATED status code on success.

<!-- /////////////////////////// UPDATE ACCOUNT /////////////////////////// -->

## Update an account

```shell
curl http://localhost:3500/v1/accounts/test@gmail.com \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
        "account": {
          "action": "update_plan",
          "plan_remote_id": "test"
        },
        "api_key": "thirdparty_api_key"
      }'
```

> Example Response

```json
200 OK
```

This endpoint updates a specific account.

### HTTP Request

`PATCH/PUT http://localhost:3500/v1/accounts/<EMAIL>`

### Request body parameters

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
email         | true      | string |         | The email of the account to be updated.
account       | true      | hash  |         | Account info.

Account

Parameter  | Required  | Type    | Default | Description
---------  | --------- | ------- | ------- | -----------
action         | true      | string |         | Action can be "block", "unblock", "lock", "unlock" or "update_plan".
plan_remote_id       | false      | string  |         | Plan remote id. Must be added only for "update_plan" action.


### Returns
Returns 200 OK status code on success.
