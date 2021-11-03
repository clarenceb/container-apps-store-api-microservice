Demo script
===========

Additional steps for sample at: https://github.com/clarenceb/container-apps-store-api-microservice

```sh
source ./demo-env.sh

SUB_ID="$(az account show --query id -o tsv)"

az group create --name $RESOURCE_GROUP -l $LOCATION

az ad sp create-for-rbac --name "$AAD_APP_NAME" --role contributor \
    --scopes "/subscriptions/$SUB_ID/resourceGroups/$RESOURCE_GROUP" \
    --sdk-auth > azure_credentials-sp.json
```
