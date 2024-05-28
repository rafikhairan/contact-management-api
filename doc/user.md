# User API Spec

## Register User

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "rafi",
  "password": "password",
  "name": "Rafi Khairan"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "rafi",
    "name": "Rafi Khairan"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Username already registered"
}
```

## Login User

Endpoint: POST /api/users/login

Request Body:

```json
{
  "username": "rafi",
  "password": "password"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "rafi",
    "name": "Rafi Khairan",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Username or password is wrong"
}
```

## Get User

Endpoint: GET /api/users/current

Headers:

- Authorization: token

Response Body (Success):

```json
{
  "data": {
    "username": "rafi",
    "name": "Rafi Khairan"
  }
}
```

Response Body (Failed):

```json
{
  "errors": "Unauthorized"
}
```

## Update User

Endpoint: PATCH /api/users/current

Headers:

- Authorization: token

Request Body:

```json
{
  "password": "password", // optional, if want to change password
  "name": "Rafi Khairan" // optional, if want to change name
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "rafi",
    "name": "Rafi Khairan"
  }
}
```

## Logout User

Endpoint: DELETE /api/users/current

Headers:

- Authorization: token

Response Body (Success):

```json
{
  "data": true
}
```
