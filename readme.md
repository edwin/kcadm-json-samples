# Using kcadm for Creating Various Resources in Keycloak

## Login to Keycloak
```shell
$ kcadm config credentials --server http://localhost:8080/auth --realm master --user admin --password password
```

## Create Groups
groups.json
```json
{
  "groups": 
  [
    {
      "id": "726511ba-a10f-4716-9ef5-120bb95d4467",
      "name": "my-group-2",
      "path": "/my-group-2",
      "attributes": {},
      "realmRoles": [],
      "clientRoles": {},
      "subGroups": []
    }
  ]
}
```

```shell
$ kcadm create partialImport -r (realm-name) -f groups.json -o
```

## Create Roles
roles.json
```json
{
  "roles": {
    "realm": [
      {
        "id": "def2f9ff-6671-46d8-9a89-b3fe0ff745dc",
        "name": "my-new-role",
        "description": "some random role",
        "composite": false,
        "clientRole": false,
        "containerId": "somethingnew",
        "attributes": {}
      }, 
	{
        "id": "abc2f9ff-6671-46d8-9a89-b3fe0ff74dca",
        "name": "my-new-role-2",
        "description": "some random role two",
        "composite": false,
        "clientRole": false,
        "containerId": "somethingnew",
        "attributes": {}
      }
    ]     
  }
}
```

```shell
$ kcadm create partialImport -r (realm-name) -f roles.json -o
```