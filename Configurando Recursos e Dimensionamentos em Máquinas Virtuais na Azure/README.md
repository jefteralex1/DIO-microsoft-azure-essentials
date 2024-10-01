# Passo a passo: Como configurar recursos e dimensionamento em VMs no Azure

## 1. O que é dimensionamento de VM no Azure?
O dimensionamento de VMs no Azure envolve ajustar os recursos computacionais (CPU, memória, armazenamento) de uma máquina virtual para atender à demanda. Isso pode ser feito manualmente ou de forma automática com **escalabilidade automática (autoscaling)**.

### Tipos de Dimensionamento:
- **Vertical (Vertical Scaling)**: Alterar o tamanho da VM (por exemplo, aumentar a quantidade de CPU ou memória).
- **Horizontal (Horizontal Scaling)**: Adicionar mais instâncias da mesma VM para distribuir a carga de trabalho.

## 2. Acessando sua Máquina Virtual no Portal do Azure
1. **Vá para o [portal do Azure](https://portal.azure.com/)** e faça login.
2. No menu à esquerda, clique em **"Máquinas Virtuais"**.
3. Selecione a máquina virtual que deseja ajustar.

## 3. Configuração de Dimensionamento Vertical (Ajustar Tamanho)
### Alterando o tamanho de uma máquina virtual:
1. No painel da VM, clique em **"Tamanho"** no menu à esquerda.
2. Veja uma lista de tamanhos de VMs disponíveis. Cada tamanho especifica CPU, memória, e desempenho de disco.
3. Selecione o novo **tamanho** que deseja atribuir à VM.
4. Clique em **"Redimensionar"** para aplicar as alterações.

### Considerações:
- **Desempenho**: Ajuste o tamanho da VM de acordo com a necessidade de desempenho. VMs com mais CPU e memória são mais caras.
- **Tempo de inatividade**: Alterar o tamanho da VM pode exigir reinicialização, causando um pequeno tempo de inatividade.

## 4. Configuração de Dimensionamento Horizontal (Escalabilidade Automática)
Para escalar horizontalmente, você precisa configurar um **Conjunto de Escala de Máquinas Virtuais (VM Scale Set)**.

### Criando um Conjunto de Escala de VMs:
1. No painel principal, clique em **"Criar um recurso"** > **"Compute"** > **"Conjunto de Escala de Máquinas Virtuais"**.
2. Preencha as informações básicas:
   - **Nome do conjunto de escala**.
   - **Região**: Selecione a mesma região da sua VM.
   - **Tamanho da instância**: Escolha o tamanho da VM para as instâncias no conjunto de escala.
3. Defina a **Capacidade**:
   - **Número de instâncias**: Defina o número mínimo e máximo de VMs no conjunto.
   - **Modo de escalabilidade**: Escolha se deseja aumentar automaticamente de acordo com a demanda.
4. Configure as **Regras de escalabilidade**:
   - **Escalar com base na métrica** (ex: uso de CPU).
   - Defina o limite de utilização que aciona o aumento ou diminuição de VMs.
5. Revise e clique em **"Criar"**.

### Considerações:
- O escalonamento automático (autoscaling) permite ajustar automaticamente o número de instâncias da VM com base na carga de trabalho, ajudando a otimizar o custo e o desempenho.
  
## 5. Configuração de Disco e Armazenamento
### Adicionando discos à máquina virtual:
1. No painel da VM, clique em **"Discos"**.
2. Clique em **"Adicionar disco"**.
   - Selecione o **tipo de disco** (SSD, HDD) e a **tamanho**.
3. Clique em **"Salvar"** para aplicar a configuração.

### Dimensionamento de discos:
- **Discos de dados**: Podem ser adicionados conforme necessário, dependendo das suas necessidades de armazenamento.
- **Desempenho do disco**: VMs de nível superior oferecem suporte a discos de alto desempenho, como discos Premium SSD.

## 6. Gerenciamento de Rede e Tráfego
### Configurando a largura de banda e balanceamento de carga:
1. No painel da VM, vá para **"Configurações de rede"**.
2. Configure as **regras de balanceamento de carga** e largura de banda.
   - Adicione **regras de entrada/saída** para permitir o tráfego que você precisa (ex: porta 80 para HTTP, 443 para HTTPS).

### Adicionando uma interface de rede:
1. Na aba **"Rede"**, clique em **"Interfaces de rede"** e adicione interfaces conforme necessário.
2. Isso pode melhorar a conectividade e o desempenho de VMs que lidam com grandes volumes de tráfego.

## 7. Monitoramento e Otimização de Recursos
### Monitoramento de uso de recursos:
1. No painel da VM, clique em **"Monitoramento"**.
2. Use o **Azure Monitor** para visualizar métricas como uso de CPU, memória, e I/O de disco.
3. Configure alertas para notificar quando determinados limites de uso forem atingidos.

### Otimização de recursos:
- **Redimensione ou adicione mais VMs** conforme necessário para gerenciar picos de demanda.
- Use **autoscaling** para otimizar o custo ajustando automaticamente o número de VMs conforme a carga de trabalho.

## 8. Revisão Final e Aplicação
1. Revise todas as configurações feitas: **tamanho da VM, discos adicionais, balanceamento de carga, regras de escalabilidade**.
2. Certifique-se de que as configurações de rede e segurança estão corretas para garantir o bom funcionamento da VM.
3. Clique em **"Salvar"** ou **"Aplicar"** para finalizar as configurações.

## Conclusão
Configurar corretamente os recursos e o dimensionamento em máquinas virtuais no Azure é essencial para garantir o desempenho e a eficiência de custos. Seja ajustando manualmente ou configurando escalabilidade automática, o Azure oferece flexibilidade para dimensionar suas VMs de acordo com suas necessidades de carga de trabalho.
