# Passo a passo: Como otimizar custos no Azure

## 1. Escolha o tamanho de VM adequado
- Utilize VMs com capacidade proporcional às suas necessidades. VMs superdimensionadas podem elevar os custos sem oferecer benefícios extras.
- **Use a calculadora de preços do Azure** para estimar o custo antes de escolher uma VM: [Calculadora de Preços Azure](https://azure.microsoft.com/pt-br/pricing/calculator/).

## 2. Utilize instâncias reservadas
- Para cargas de trabalho previsíveis e de longo prazo, utilize **Instâncias Reservadas**.
- Com as reservas, você pode economizar até **72%** em comparação às VMs pagas conforme o uso.
- Contratos podem ser feitos por **1 ou 3 anos**.

## 3. Desligue recursos não utilizados
- **Desligue as VMs** ou outros recursos (como App Services e bancos de dados) quando não estiverem em uso, especialmente em ambientes de desenvolvimento e teste.
- Use **Azure Automation** ou scripts PowerShell para agendar o desligamento automático de VMs fora do horário comercial.

## 4. Use escalabilidade automática (Auto-scaling)
- Configure o **Auto-scaling** para ajustar automaticamente a capacidade de suas VMs com base na demanda, evitando que você pague por capacidade ociosa.
- Para isso, vá para **Virtual Machine Scale Sets** e configure as políticas de escalabilidade.

## 5. Explore as camadas gratuitas e de baixo custo
- O Azure oferece uma **camada gratuita** para diversos serviços, como Azure App Service, bancos de dados SQL e VMs. Verifique se há serviços elegíveis para permanecer dentro do limite gratuito.
- Além disso, muitos serviços têm versões **Básica** ou **Dev/Test**, mais econômicas.

## 6. Monitore e gerencie seus custos com Azure Cost Management
- Utilize o **Azure Cost Management + Billing** para monitorar, analisar e otimizar seus gastos.
- Crie **alertas de orçamento** para ser notificado quando os custos ultrapassarem um determinado valor.
- Veja como estão os custos por assinatura, grupos de recursos ou até mesmo por departamento.

## 7. Use Azure Spot VMs
- As **Spot VMs** oferecem até **90% de economia**, pois utilizam capacidade não utilizada da nuvem Azure.
- Essas VMs são ideais para cargas de trabalho temporárias, tolerantes a falhas ou de curto prazo.

## 8. Optimize o armazenamento
- Use o **Azure Blob Storage** com camadas de armazenamento adequadas:
  - **Hot**: Para dados acessados frequentemente.
  - **Cool**: Para dados acessados raramente.
  - **Archive**: Para dados que podem ser arquivados a longo prazo.
- Ative a **política de expiração** para automaticamente mover ou excluir dados conforme o ciclo de vida do dado.

## 9. Analise o uso de redes
- Verifique se suas redes estão configuradas corretamente para evitar custos inesperados.
- Reduza os custos de **dados de saída** armazenando dados em regiões mais próximas dos usuários e consumidores do serviço.
- Utilize **Azure Traffic Manager** para otimizar o tráfego global e minimizar a latência, enquanto gerencia o uso de rede.

## 10. Verifique descontos por uso de licenças
- Se você já possui licenças do Windows Server ou SQL Server, ative o **Azure Hybrid Benefit**, que pode economizar até **40%** nos custos de licenciamento.
- Esse benefício pode ser aplicado ao criar novas VMs ou em VMs existentes.

## 11. Utilize ferramentas de automação
- Use **Azure DevTest Labs** para criar ambientes de desenvolvimento/teste otimizados, permitindo que você controle o custo e desligue recursos automaticamente.
- Automação pode ser usada para remover ou recriar recursos temporários após o uso, reduzindo custos de recursos ociosos.

## 12. Avalie o uso de contêineres
- Se você trabalha com aplicativos que podem ser containerizados, considere usar **Azure Kubernetes Service (AKS)** ou **Azure Container Instances (ACI)**.
- Contêineres podem ajudar a economizar custos, pois utilizam recursos com mais eficiência, cobrando apenas o uso efetivo.

## 13. Use a Calculadora de TCO
- A **Calculadora de TCO (Total Cost of Ownership)** ajuda a estimar o custo total de propriedade ao mover cargas de trabalho para o Azure, comparando os custos da infraestrutura local (on-premises) com os custos de rodar no Azure.
- Com essa ferramenta, você pode comparar gastos com hardware, licenciamento, consumo de energia e mão de obra.
- Acesse a **Calculadora de TCO** aqui: [Azure TCO Calculator](https://azure.microsoft.com/pt-br/pricing/tco-calculator/).

---

## Conclusão
Para otimizar os custos no Azure, é essencial:
- Monitorar o uso regularmente com **Azure Cost Management**.
- Ajustar recursos conforme a demanda.
- Implementar práticas de desligamento e escalabilidade automática.
- Usar instâncias reservadas, licenciamento híbrido e a **Calculadora de TCO** quando aplicável.
Essas estratégias ajudarão a maximizar a eficiência e reduzir os custos gerais na nuvem Azure.
