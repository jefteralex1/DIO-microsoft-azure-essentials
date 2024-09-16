# Resumo do Lab - Criando Máquinas Virtuais na Azure

Neste lab, exploramos o processo de criação e configuração de Máquinas Virtuais (VMs) no Microsoft Azure. O objetivo deste desafio é consolidar o conhecimento adquirido na prática de criar e gerenciar VMs, um dos principais serviços de computação na nuvem oferecidos pelo Azure.

## O que é uma Máquina Virtual?

Uma Máquina Virtual (VM) é um ambiente isolado e virtualizado que simula um computador físico. Ela permite que você execute aplicativos e serviços em um servidor virtual na nuvem, sem a necessidade de gerenciar a infraestrutura física.

## Passos para Criar uma Máquina Virtual no Azure

### 1. **Acesse o Portal do Azure**
   - Vá para [Portal do Azure](https://portal.azure.com/) e faça login com suas credenciais.

### 2. **Crie uma Nova Máquina Virtual**
   - No painel de navegação à esquerda, clique em **"Criar um recurso"**.
   - Selecione **"Máquina Virtual"**.

### 3. **Configuração Básica**
   - **Assinatura**: Selecione a assinatura do Azure que deseja usar.
   - **Grupo de Recursos**: Crie um novo grupo de recursos ou selecione um existente.
   - **Nome da Máquina Virtual**: Defina um nome único para sua VM.
   - **Região**: Escolha a região onde sua VM será hospedada.
   - **Imagem**: Selecione o sistema operacional desejado (por exemplo, Windows Server, Ubuntu, etc.).
   - **Tamanho**: Escolha o tamanho da VM com base nas suas necessidades de desempenho e capacidade.
   - **Nome de Usuário e Senha**: Defina um nome de usuário e senha para acessar a VM.

### 4. **Configuração de Rede**
   - Configure as opções de rede, como VNet (Rede Virtual) e IP Público, se necessário.
   - Selecione ou crie um grupo de segurança de rede para definir regras de firewall.

### 5. **Configurações Adicionais**
   - Configure opções adicionais, como armazenamento, monitoramento e backups.
   - Revise as configurações e ajuste conforme necessário.

### 6. **Revisão e Criação**
   - Revise todas as configurações.
   - Clique em **"Criar"** para iniciar a criação da sua VM.

## Conclusão

Durante este lab, aprendemos a criar e configurar máquinas virtuais no Microsoft Azure, o que inclui a escolha de uma imagem de sistema operacional, configuração de rede e gerenciamento de recursos. As VMs são essenciais para hospedar aplicativos e serviços, e o Azure oferece uma plataforma robusta para gerenciá-las de maneira eficiente.