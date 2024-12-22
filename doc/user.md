# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username" : "username",
  "password" : "password",
  "name" : "name"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "username",
    "name" : "name"
  }
}
```

Response Body (Error) :

```json
{
  "errors" : "Username or email already registered!"
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username" : "username",
  "password" : "password"
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "username",
    "name" : "name",
    "token" : "generated_token"
  }
}
```

Response Body (Error) :

```json
{
  "errors" : "Incorrect username or password!"
}
```

## Update User

Endpoint : PATCH /api/users/current

Headers :
- Authorization : token

Request Body :

```json
{
  "password" : "password", //optional
  "name" : "name" //optional
}
```

Response Body (Success) :

```json
{
  "data" : {
    "username" : "username",
    "name" : "name"
  }
}
```

## Logout User

Endpoint : DELETE /api/users/current

Headers :
- Authorization : token

Response Body (Success) :

```json
{
  "data" : "Logout Success"
}
```



