# Login with Google

| URL             | Requires Auth | HTTP Method |
| :-------------- | :------------ | :---------- |
| `/api/v1/login` | `no`          | `POST`      |

## Payload

| Argument      | Example                         | Required | Description                           |
| :---------    | :------------------------------ | :------- | :------------------------------------ |
| `serviceName` | `google`                        | Required | The desired OAuth service name        |
| `accessToken` | `hash`                          | Required | Access token provided by google oauth |
| `idToken`     | `hash`                          | Required | Id token provided by google auth      |
| `expiresIn`   | `200`                           | Required | Lifetime of token(in seconds)         |
| `scope`       | `profile`                       | Optional | Google scopes for API                 |
| `identity`    | `{id: '1', name: 'rocket.cat'}` | Optional | Google user identity                  |

## Example Call - As JSON

```bash
curl -H "Content-type:application/json" \
      http://localhost:3000/api/v1/login \
      -d '{ "serviceName": "google", accessToken": "hash",
      "idToken": "hash", "expiresIn": 200, "scope": "profile" }'
```

## Result

```json
{
  "status": "success",
  "data": {
      "authToken": "9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq",
      "userId": "aobEdbYhXfu5hkeqG"
   }
}
```

## Change Log

| Version | Description |
| :--- | :--- |
| 0.60.0 | Added |

