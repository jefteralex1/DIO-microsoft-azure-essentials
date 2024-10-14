# Passo a passo: Gerenciando Políticas de Acesso no Azure

## Introdução
No Azure, a gestão de políticas de acesso e governança é essencial para garantir a conformidade, segurança e controle sobre os recursos. As principais ferramentas incluem:
- **Azure Policy**: Para aplicar regras e garantir que os recursos estejam em conformidade com as normas corporativas.
- **Microsoft Purview**: Para governança de dados, permitindo a visibilidade e controle sobre o acesso a informações sensíveis.
- **RBAC (Role-Based Access Control)**: Para controlar o acesso com base em papéis de usuário.

## Parte 1: Configurando Azure Policy

### O que é Azure Policy?
O **Azure Policy** é uma ferramenta de governança que ajuda a definir e aplicar regras aos recursos do Azure, garantindo que as configurações estejam em conformidade com as políticas organizacionais.

### Passo 1: Criar uma Política no Azure Policy
1. **Acesse o [portal do Azure](https://portal.azure.com/)** e faça login.
2. No menu lateral, pesquise por **"Policy"** e clique na opção **"Política"**.
3. No painel do **Azure Policy**, clique em **"Atribuições"** e depois em **"Atribuir Política"**.
4. **Escolha o escopo**: Selecione a assinatura ou grupo de recursos onde a política será aplicada.
5. **Selecione a definição de política**: Escolha uma política predefinida ou crie uma nova política personalizada.
   - Exemplo de política predefinida: **"Permitir apenas máquinas virtuais com discos gerenciados"**.
6. **Defina parâmetros**, se necessário. Algumas políticas podem ter opções configuráveis, como limites ou regiões específicas.
7. Clique em **"Revisar + Criar"** para concluir a atribuição da política.

### Passo 2: Monitorando Conformidade
1. No painel do **Azure Policy**, vá para **"Conformidade"** para ver um resumo das políticas aplicadas e o status de conformidade dos seus recursos.
2. Corrija os recursos que estão fora de conformidade, ou crie exceções onde apropriado.

---

## Parte 2: Microsoft Purview para Governança de Dados

### O que é Microsoft Purview?
O **Microsoft Purview** é uma plataforma de governança de dados que fornece visibilidade, classificação e controle sobre dados sensíveis no Azure e em ambientes híbridos.

### Passo 1: Configurar Microsoft Purview
1. No **[portal do Azure](https://portal.azure.com/)**, busque por **Microsoft Purview**.
2. Crie um **Account Purview** ou selecione um já existente.
3. Defina **fontes de dados** que precisam ser escaneadas (ex.: Azure Storage, SQL Database, etc.).
4. Utilize **escanes automáticos** para descobrir e classificar dados sensíveis automaticamente, utilizando categorias como **PII (Informação Pessoal Identificável)**.

### Passo 2: Gerenciar Políticas de Acesso a Dados
1. Acesse o painel do **Microsoft Purview** e vá até **"Políticas de Acesso"**.
2. Defina políticas para controlar o acesso a dados classificados. Por exemplo:
   - Restringir acesso a dados PII a um grupo específico.
   - Criar políticas para mascaramento dinâmico de dados sensíveis.
3. Aplique a política a todos os recursos que lidam com dados críticos ou confidenciais.

---

## Parte 3: Controle de Acesso com RBAC (Role-Based Access Control)

### O que é RBAC?
O **RBAC (Controle de Acesso Baseado em Papéis)** no Azure permite que você atribua permissões específicas a usuários, grupos ou aplicativos com base em suas funções, garantindo que tenham apenas o nível necessário de acesso.

### Passo 1: Atribuir Funções de Acesso
1. No **[portal do Azure](https://portal.azure.com/)**, vá até o recurso ao qual deseja atribuir uma função.
2. No painel lateral, clique em **"Controle de Acesso (IAM)"**.
3. Clique em **"Atribuição de Função"** e depois em **"Adicionar"**.
4. Escolha uma função predefinida (como **Leitor**, **Contribuidor**, **Proprietário**) ou crie uma função personalizada.
5. Selecione os **usuários ou grupos** que receberão essa função e clique em **"Salvar"**.

### Passo 2: Revisar e Auditar Acessos
1. No mesmo painel de **IAM**, acesse a aba **"Atribuições de Funções"** para ver quais usuários têm acesso ao recurso e em qual nível.
2. Utilize logs de auditoria para revisar atividades de usuários e garantir que acessos desnecessários sejam removidos.

---

## Parte 4: Azure Blueprints para Governança de Nuvem

### O que é Azure Blueprints?
O **Azure Blueprints** permite criar modelos reutilizáveis que definem um conjunto de políticas, funções de acesso, e recursos, facilitando a governança e o cumprimento de normas.

### Passo 1: Criar um Blueprint
1. No portal do Azure, busque por **"Blueprints"**.
2. Clique em **"Criar Blueprint"** e selecione uma **política predefinida** ou comece do zero.
3. Defina os **artefatos** que serão incluídos, como:
   - Políticas do Azure Policy.
   - Atribuições de RBAC.
   - Grupos de recursos.
4. Publique e atribua o blueprint à assinatura ou grupo de recursos.

---

## Conclusão
Essas ferramentas — **Azure Policy**, **Microsoft Purview**, **RBAC**, e **Azure Blueprints** — permitem gerenciar de forma eficaz a governança e a segurança dos recursos e dados no Azure. O uso adequado dessas práticas melhora a conformidade com normas de segurança e simplifica o controle sobre o ambiente de nuvem.
