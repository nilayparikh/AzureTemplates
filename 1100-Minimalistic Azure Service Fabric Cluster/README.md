# Deploy a minimalistic Azure Service Fabric Cluster (for Test and Learn)

```

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-availability-set-create-3FDs-20UDs%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F101-availability-set-create-3FDs-20UDs%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

## Parameters

{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    //Admin
    "adminUserName": {
      "value": "admin",
      "metadata": {
        "description": "Remote desktop user Id"
      }
    },
    "adminPassword": {
      "reference": {
        "keyVault": {
          "id": "/subscriptions/00000000-0000-0000-000000000000/resourceGroups/xxxxxxxxxxxxxxx/providers/Microsoft.KeyVault/vaults/xxxxxxxxxxxxx"
        },
        "secretName": "###" /*Refer secret name storing password securely*/
      }
    },
    //VM
    "vmCount": {
      "value": 3,
      "metadata": {
        "description": "Node instance count (initial VM Scale Set size)."
      }
    },
    "vmType": {
      "value": "Standard_A0",
      "metadata": {
        "description": "VM Type, refer https://docs.microsoft.com/en-us/azure/virtual-machines/virtual-machines-windows-sizes."
      }
    },
    "vmTier": {
      "value": "Standard",
      "metadata": {
        "description": "VM Tier, refer https://docs.microsoft.com/en-us/azure/virtual-machines/virtual-machines-windows-sizes."
      }
    },
    //Key Vault - Node to Node
    "certificateThumbprint": {
      "value": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX", //Thumbprint of the certificate
            "metadata": {
        "description": "Certificate thumbprint - for Node to Node configuration."
      }
    },
    "sourceVaultResourceId": {
      "value": "/subscriptions/00000000-0000-0000-000000000000/resourceGroups/xxxxxxxxxxxxxxx/providers/Microsoft.KeyVault/vaults/xxxxxxxxxxxxx",
            "metadata": {
        "description": "Key Vault Referance."
      }
    },
    "certificateUrlValue": {
      "value": "https://xxxxxxxxxxx.vault.azure.net:443/secrets/xxxxxxxxxxxxxxxxx/xxxxxxxxxxxxxxxxxxx",
            "metadata": {
        "description": "Certificate Key Vault Resource Uri with Version."
      }
    }
  }
}
```
