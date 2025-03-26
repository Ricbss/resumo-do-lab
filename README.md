## Resumo do Lab - Infraestrutura como Código no Linux

Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab na DIO.

### O que eu aprendi?
Nesse lab, aprendi sobre a importância da automação na criação de usuários, grupos e permissões no Linux, utilizando scripts para simplificar e padronizar configurações em ambientes de infraestrutura como código.

### Criando e Gerenciando Usuários e Grupos no Linux

#### Domínio de Objetivo
- Automatizar a criação de usuários e grupos no Linux.
- Configurar permissões adequadas para diferentes usuários.
- Utilizar scripts para replicar configurações em múltiplas máquinas.
- Armazenar e versionar os scripts no GitHub para reutilizações futuras.

#### Criação de Usuários
- Comando `useradd` para criar usuários.
- Definição de senha com `passwd`.
- Configuração do shell padrão e diretório inicial.
- Adição de usuários a grupos específicos.

#### Gerenciamento de Grupos
- Uso do comando `groupadd` para criar grupos.
- Adição de usuários a grupos com `usermod -aG`.
- Verificação dos grupos de um usuário com `groups`.

#### Permissões e Diretórios
- Configuração de permissões com `chmod` e `chown`.
- Aplicação de políticas de acesso em diretórios compartilhados.
- Uso do comando `umask` para definir permissões padrão.

### Benefícios da Automação
- **Eficiência**: Redução de tempo na configuração manual.
- **Padronização**: Configurações uniformes em múltiplas máquinas.
- **Segurança**: Controle preciso sobre acessos e permissões.
- **Reutilização**: Scripts versionados no GitHub para fácil replicação.

### Ferramentas Utilizadas
- **Bash Script**: Automação dos comandos.
- **GitHub**: Armazenamento e versionamento dos scripts.
- **Linux**: Sistema operacional para a execução das configurações.

### Exemplo de Script
```bash
#!/bin/bash
# Criando usuários automaticamente
useradd -m -s /bin/bash usuario1
useradd -m -s /bin/bash usuario2

# Definindo senhas
echo "usuario1:senha123" | chpasswd
echo "usuario2:senha123" | chpasswd

# Criando grupos
groupadd desenvolvedores
groupadd administradores

# Adicionando usuários aos grupos
usermod -aG desenvolvedores usuario1
usermod -aG administradores usuario2

# Configurando permissões
chown -R usuario1:desenvolvedores /home/usuario1
chown -R usuario2:administradores /home/usuario2
chmod 770 /home/usuario1
chmod 770 /home/usuario2
```

**Armazenamento do Azure**

## Objetivos
- Comparar os serviços de armazenamento do Azure
- Descrever as camadas de armazenamento
- Descrever as opções de redundância
- Descrever as opções de conta de armazenamento e os tipos de armazenamento
- Identificar opções para mover arquivos, incluindo o AzCopy, o Gerenciador de Armazenamento do Azure e a Sincronização de Arquivos do Azure
- Descrever as opções de migração, incluindo as Migrações para Azure e o Azure Data Box

## Contas de Armazenamento (Storage Account)
- Deve ter um nome único globalmente
- Fornece acesso à Internet em todo o mundo
- Determina os serviços de armazenamento e as opções de redundância

## Redundância de Armazenamento
- **LRS (Local Redundant Storage)**: DC individual na região primária (11 noves)
- **ZRS (Zone Redundant Storage)**: Três zonas de disponibilidade na região primária (12 noves)
- **GRS (Geo-Redundant Storage)**: DC único no primário e região secundária (16 noves)
- **GZRS (Geo-Zone Redundant Storage)**: Três zonas de disponibilidade na região primária e um único DC na região secundária (16 noves)

## Redundância e Serviços de Armazenamento
- **Blob do Azure**: Armazena grandes volumes de dados não estruturados
- **Disco do Azure**: Fornece discos para máquinas virtuais
- **Fila do Azure**: Armazena mensagens de até 64KB
- **Arquivos do Azure**: Compartilhamento de arquivos de rede
- **Tabelas do Azure**: Armazena dados estruturados não relacionais

## Camadas de Acesso
- **Frequente**: Dados acessados com alta frequência
- **Esporádico**: Armazena dados por pelo menos 30 dias
- **Frio**: Armazena dados por pelo menos 90 dias
- **Arquivo Morto**: Armazena dados por pelo menos 180 dias

## Migrações para o Azure
- **Plataforma de migração unificada**
- **Azure Data Box**: Migração física de até 80TB de dados

## Opções de Gerenciamento de Arquivos
- **AzCopy**: Linha de comando para copiar arquivos
- **Gerenciador de Armazenamento do Azure**: Interface gráfica para gerenciamento
- **Sincronização de Arquivos do Azure**: Sincronização bidirecional entre nuvem e local

## Identidade, Acesso e Segurança
- **Microsoft Entra ID**: Gerenciamento de identidade e acesso
- **Microsoft Entra Domain Services**: Domínio baseado em nuvem sem necessidade de gerenciar DCs
- **Autenticação vs. Autorização**:
  - **Autenticação**: Identifica usuário/serviço
  - **Autorização**: Define permissões de acesso
- **Autenticação Multifator**: Requer dois ou mais fatores de autenticação
- **Acesso Condicional**: Baseado em grupo, IP, dispositivo, aplicativo e riscos
- **Controle de Acesso Baseado em Função (RBAC)**: Define permissões detalhadas
- **Confiança Zero**: Proteção em camadas contra ataques
- **Microsoft Defender para Nuvem**: Proteção contra ameaças

## Gerenciamento de Custos
- **Fatores que afetam custos**:
  - Tipo de recurso
  - Consumo
  - Manutenção
  - Localização geográfica
  - Tráfego de rede
  - Tipo de assinatura
- **Azure Marketplace**: Encontre e provisione serviços e aplicativos certificados
- **Calculadora de Preços**: Estima custo dos serviços do Azure
- **Calculadora TCO**: Compara custos locais vs. Azure
- **Orçamentos e Alertas**: Monitoramento de custos

## Governança e Conformidade
- **Azure Policy**: Impõe padrões e avalia conformidade
- **Bloqueios de Recursos**: Impedem modificações acidentais
- **Portal de Confiança do Serviço**: Informações sobre segurança e conformidade
- **Microsoft Purview**: Governança de dados


### Conclusão
Esse lab demonstrou como a automação pode facilitar o gerenciamento de usuários, grupos e permissões no Linux. Utilizando scripts e versionamento de código, é possível garantir eficiência, segurança e padronização em ambientes de infraestrutura como código.

