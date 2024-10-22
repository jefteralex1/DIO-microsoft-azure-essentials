# Ferramentas de Implantação no Azure

O Azure oferece várias ferramentas que ajudam na criação e gerenciamento de infraestruturas como código (IaC). As principais ferramentas são **Azure Resource Manager (ARM) Templates**, **Bicep** e outras opções que facilitam a automação e consistência na configuração de recursos.

---

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
```
### Principais Comandos
#### Implantar um ARM Template:
```bash
az deployment group create --resource-group <nome-grupo> --template-file <template.json>
```
---

## 2. Bicep
**Bicep** é uma linguagem declarativa que simplifica a criação de templates de infraestrutura no Azure, sendo uma alternativa mais legível e menos verbosa aos ARM Templates.

### Por que usar Bicep?
- Sintaxe simplificada: Menos verboso que JSON.
- Melhor integração: Possui suporte nativo e a paridade completa com ARM Templates.
- Fácil de manter: Com menos código, o desenvolvimento e a manutenção se tornam mais simples.
### Exemplo de Código Bicep:
```bicep
resource myVM 'Microsoft.Compute/virtualMachines@2021-07-01' = {
  name: 'myVM'
  location: resourceGroup().location
  properties: {
    hardwareProfile: {
      vmSize: 'Standard_DS1_v2'
    }
    osProfile: {
      computerName: 'myVM'
      adminUsername: 'azureuser'
      adminPassword: 'password123'
    }
  }
}
```
### Principais Comandos
#### Compilar um arquivo Bicep para um ARM Template:
```bash
bicep build <arquivo.bicep>
```
#### Implantar um Bicep diretamente:
```bash
az deployment group create --resource-group <nome-grupo> --template-file <arquivo.bicep>
```
---

## 3. Azure CLI

**Azure CLI** é uma interface de linha de comando multiplataforma para gerenciar os recursos do Azure. Ela permite a criação e gerenciamento de recursos sem a necessidade de ARM Templates ou Bicep, usando comandos diretos.

### Exemplo de uso da Azure CLI para criar uma VM:
```bash
az vm create \
  --resource-group myResourceGroup \
  --name myVM \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
```
### Vantagens:
- Comandos rápidos e diretos.
- Pode ser automatizada via scripts.

---

## 4. Azure PowerShell
Azure PowerShell é um módulo que você pode usar para automatizar e gerenciar recursos do Azure. É uma alternativa à Azure CLI, mais voltada para quem está acostumado com ambientes Windows e scripts PowerShell.

Exemplo de uso:
```powershell
New-AzVm `
  -ResourceGroupName "myResourceGroup" `
  -Name "myVM" `
  -Image "UbuntuLTS" `
  -Credential (Get-Credential)
```

### Vantagens:
- Integração com scripts PowerShell.
- Útil para quem trabalha em ambientes Windows.

---

## 5. Terraform
**Terraform** é uma ferramenta de código aberto para infraestrutura como código que permite a criação e gerenciamento de recursos no Azure (e em outros provedores de nuvem). Ele usa uma linguagem declarativa chamada HCL.

### Exemplo de Código Terraform:
```hcl
provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "example" {
  name     = "myResourceGroup"
  location = "West Europe"
}

resource "azurerm_virtual_network" "example" {
  name                = "myVnet"
  address_space       = ["10.0.0.0/16"]
  resource_group_name = azurerm_resource_group.example.name
  location            = azurerm_resource_group.example.location
}
```
### Vantagens:
- Suporta múltiplos provedores (não só Azure).
- Facilita o gerenciamento de infraestrutura em ambientes complexos.

---

## 6. Ansible
**Ansible** é uma ferramenta de automação que pode ser usada para provisionar e configurar recursos no Azure. Ele é baseado em arquivos YAML e é popular por sua simplicidade e facilidade de uso.

### Exemplo de Playbook Ansible para criar uma VM no Azure:
```yaml
---
- name: Criar VM no Azure
  hosts: localhost
  tasks:
    - name: Criar grupo de recursos
      azure_rm_resourcegroup:
        name: myResourceGroup
        location: eastus

    - name: Criar máquina virtual
      azure_rm_virtualmachine:
        resource_group: myResourceGroup
        name: myVM
        vm_size: Standard_DS1_v2
        admin_username: azureuser
        admin_password: password123
        image:
          offer: UbuntuServer
          publisher: Canonical
          sku: 18.04-LTS
          version: latest
```
---
| Ferramenta          | Formato   | Propósito Principal                                    |
|---------------------|-----------|--------------------------------------------------------|
| ARM Templates        | JSON      | Definir infraestrutura no Azure de forma declarativa.  |
| Bicep               | Bicep     | Alternativa simplificada para ARM Templates.           |
| Azure CLI           | Comandos  | Gerenciar recursos com comandos diretos.               |
| Azure PowerShell    | PowerShell| Gerenciar recursos em ambientes Windows.               |
| Terraform           | HCL       | Gerenciar infraestruturas em múltiplos provedores.     |
| Ansible             | YAML      | Automação e provisionamento de infraestrutura.         |
