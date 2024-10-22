# Ferramentas de Implantação no Azure

O Azure oferece várias ferramentas que ajudam na criação e gerenciamento de infraestruturas como código (IaC). As principais ferramentas são **Azure Resource Manager (ARM) Templates**, **Bicep** e outras opções que facilitam a automação e consistência na configuração de recursos.

## 1. Azure Resource Manager (ARM)

**Azure Resource Manager (ARM)** é o serviço que fornece o gerenciamento e implantação de recursos no Azure. Usar **ARM Templates** permite definir, provisionar e gerenciar recursos no Azure de maneira declarativa.

### ARM Templates
- **O que são?** ARM Templates são arquivos JSON que contêm a definição da infraestrutura necessária. 
- **Como funcionam?** Você descreve os recursos e suas propriedades em um arquivo, e a Azure utiliza esse template para criar ou modificar os recursos.
- **Vantagens**:
  - Permite automação e replicação de ambientes.
  - Suporta controle de versão de templates, facilitando o rastreamento de alterações.
  
### Exemplo de ARM Template (JSON):
```json
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "resources": [
    {
      "type": "Microsoft.Compute/virtualMachines",
      "apiVersion": "2019-07-01",
      "name": "myVM",
      "location": "[resourceGroup().location]",
      "properties": {
        "hardwareProfile": {
          "vmSize": "Standard_DS1_v2"
        },
        "osProfile": {
          "computerName": "myVM",
          "adminUsername": "azureuser",
          "adminPassword": "password123"
        }
      }
    }
  ]
}
