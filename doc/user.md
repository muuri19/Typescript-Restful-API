# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username" : "muuri",
  "password" : "rahasia",
  "name" : "Muhammad Sadri"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "muuri",
    "name" : "Muhammad Sadri"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username" : "muuri",
  "password" : "rahasia"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "muuri",
    "name" : "Muhammad Sadri",
    "token" : "uuid"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Username or password wrong, ..."
}
```

## Get User

Endpoint : GET /api/users/current

Request Header :
- X-API-TOKEN : token

Response Body (Success) :

```json
{
  "data" : {
    "username" : "muuri",
    "name" : "Muhammad Sadri"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Unauthorized, ..."
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header :
- X-API-TOKEN : token

Request Body :

```json
{
  "password" : "rahasia",
  "name" : "Muhammad Sadri"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "muuri",
    "name" : "Muhammad Sadri"
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Unauthorized, ..."
}
```

## Logout User

Endpoint : DELETE /api/users/current

Request Header :
- X-API-TOKEN : token

Response Body (Success) :

```json
{
  "data" : "OK"
}
```

Response Body (Failed) :

```json
{
  "errors" : "Unauthorized, ..."
}
```
