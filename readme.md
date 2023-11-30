# Using kcadm for Creating Various Resources in Keycloak

## Create Groups
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