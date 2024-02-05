{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "location": {
            "type": "string",
            "allowedValues" : [
                "eastus",
                "westus"
            ],
            "defaultValue": "eastus",
            "metadata": {
                "description": "description"
            }
        },
        "part": {
            "type": "string",
            "minLength":4,
            "maxLength":8,
            "metadata": {
                "description": "description"
            }
        }
    },
    "variables": {
        "name": "[concat(parameters('part'),'res')]"
    },
    "resources": [
        {
            "name": "[concat('st889',variables('name'))]",
            "type": "Microsoft.Storage/storageAccounts",
            "apiVersion": "2023-01-01",
            "tags": {
                "displayName": "[concat('st889',variables('name'))]"
            },
            "location": "[resourceGroup().location]",
            "kind": "StorageV2",
            "sku": {
                "name": "Standard_LRS",
                "tier": "Standard"
            }
        }
    ],
    "outputs": {}
}

