# Deploy a minimalistic Azure Service Fabric Cluster

#### Note: This template is not suitable for production use. You may use as an initial starting template for production use.

This template creates a minimalist Service Fabric Cluster, ideal for learning, testing and blogging purposes. The template is not ideal for production use.

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnilayparikh%2FAzureTemplates%2Fmaster%2F1100-Minimalistic-Azure-Service-Fabric-Cluster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fnilayparikh%2FAzureTemplates%2Fmaster%2F1100-Minimalistic-Azure-Service-Fabric-Cluster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

## Parameters

``` json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
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
        "secretName": "###"
      }
    },
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
    "certificateThumbprint": {
      "value": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
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

Copyright (c) 2017 Nilay Parikh

Modifications Copyright (c) 2017 Nilay Parikh

B: https://blog.nilayparikh.com E: me@nilayparikh.com G: https://github.com/nilayparikh/

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
