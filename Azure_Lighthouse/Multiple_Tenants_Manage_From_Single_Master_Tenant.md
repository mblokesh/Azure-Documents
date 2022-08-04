# Azure Lighthouse allows you to manage multiple 'client' Azure tenants from a single 'master' tenant:

**Using** `Control service provider access`

`https://techcommunity.microsoft.com/t5/azure-paas-blog/azure-lighthouse-step-by-step-guidance-onboard-customer-to/ba-p/1793055`

# Lighhouse Template.json

```
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    "mspOfferName": {
      "value": "Subcription Name"
    },
    "mspOfferDescription": {
      "value": "Subcription Name"
    },
    "managedByTenantId": {
      "value": "67f98f7c-4b2b-0780-t490-65fcedsfds2d4b"
    },
    "authorizations": {
      "value": [
        {
          "principalId": "f8cc66bd-6k9u-7619-5e0e-22f11689304",
          "principalIdDisplayName": "Support_Co",
          "roleDefinitionId": "g30768ac-8995-78a0-ab21-29f782ud24c"
        }
      ]
    }
  }
}

```


