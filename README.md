# SPRING BOOT WITH KEYCLOAK

## Dependencies

- Web
- OAuth2 Resource Server
- Security
- Lombok

```XML
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-security</artifactId>
    </dependency>
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <optional>true</optional>
    </dependency>
</dependencies>
```

## Steps

- Creating Realm
- Creating Client
- Creating Roles
- Creating Users

## Test

### Get access token using keycloak endpoint, client_id, username and pass

In console

```BASH
curl --location 'http://localhost:8080/realms/MySuperApplicationRealm/protocol/openid-connect/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=password' \
--data-urlencode 'client_id=my-super-client' \
--data-urlencode 'username=user3' \
--data-urlencode 'password=pass'
```

In postman

```JSON
{
  "info": {
    "_postman_id": "27bbc1d1-98f0-4289-a266-07f4269a325b",
    "name": "sb3-keycloak-23.0.4",
    "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
    "_exporter_id": "17450698"
  },
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
  ]
}
```

## Others endpoints you can use similarly in postman.