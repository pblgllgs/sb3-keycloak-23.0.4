# SPRING BOOT WITH KEYCLOAK

## Steps

- Creating Realm
- Creating Client
- Creating Roles
- Creating Users

## Test

### Get access token using keycloak endpoint, client_id, username and pass

In console

```bash
curl --location 'http://localhost:8080/realms/MySuperApplicationRealm/protocol/openid-connect/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'client_id=my-super-client' \
--data-urlencode 'username=user3' \
--data-urlencode 'password=pass'
```
In postman

```json
"item": [
		{
			"name": "getAccessToken",
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "urlencoded",
					"urlencoded": [
						{
							"key": "grant_type",
							"value": "password",
							"type": "text"
						},
						{
							"key": "client_id",
							"value": "my-super-client",
							"type": "text"
						},
						{
							"key": "username",
							"value": "user3",
							"type": "text"
						},
						{
							"key": "password",
							"value": "pass",
							"type": "text"
						}
					]
				},
				"url": {
					"raw": "http://localhost:8080/realms/MySuperApplicationRealm/protocol/openid-connect/token",
					"protocol": "http",
					"host": [
						"localhost"
					],
					"port": "8080",
					"path": [
						"realms",
						"MySuperApplicationRealm",
						"protocol",
						"openid-connect",
						"token"
					]
				}
			},
			"response": []
		}
```

## Others endpoints you can use similarly in postman.