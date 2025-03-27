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



_____________________________________________________________________//____________________________________________________

Este é um repositório que contém um resumo do que foi aprendido no lab de Computação e Rede da DIO

Serviços de computação

Máquinas virtuais
Aplicativos / Serviços
Contêuiner
Serviçoes de Kubernets do Azure
Área de trabalho virtual
Máquinas virtuais

Emulação de softwares de computadores físicos
Servidor baseado em nuvem que dá suporte a ambientes Windows ou Linux
Útil para migrações lift-and-shift
Inclui processador virtual, memória, armazenamento e rede
Oferta de IaaS que oferece personalização e controle
Conjunto de dimensionamento de VMs

oferecem oportunidade de balanceamento de carga para dimensionar recursos automaticamente
Conjunto de disponibilidade de VMs

Domínio de falha
Domnínio de atualização
Área de trabalho Virtual

Virtualização de área de trabalho e aplicativo na nuvem (semelhante a acesso remoto)
Reduzir risco perda de recurso
Implantações reais de várias sessões
Adicionar autenticação em 2 fatores
Controle de licenças para usuários
Contêineres

fornecem ambiente leve e virtualizado que não exige gerenciamento do sistema operacional e pode responder a alterações sob demanda
projetado para escalabilidade e resiliência
Azure Functions

Execução baseada em eventos
Modelo PaaS
Serviços de Aplicativo

Plataforma gerenciada para criar, implantar e dimensionar Web e APIs rapidamente
Trabalha com .NET, .NET Core, Node.js, Java, Python ou php
Oferta de Paas com requisitos de nível corporativo de desempenho, segurança e conformidade
Serviços de rede

permite comunicação entre os recursos dentro do Azure
emparelhamento de rede conecta sua redes privadas
sub-redes segmantam sua rede para atender às suas necessidades


__________________________________________________________________________________________________________________


Microsoft Azure Lab
Este repositório documenta minhas experiências e aprendizados com o Microsoft Azure, com base nas trilhas de estudos do Microsoft Docs e laboratórios práticos.

Resumo
Iniciei os estudos utilizando uma conta gratuita do Azure, previamente criada para fins acadêmicos. Durante as aulas, explorei os principais conceitos relacionados à computação em nuvem, incluindo:

Tipos de nuvem: Pública, privada e híbrida.
Modelos de custos: Diferenças entre CapEx (Capital Expenditure) e OpEx (Operational Expenditure), com exemplos práticos.
Benefícios da nuvem:
Alta disponibilidade
Escalabilidade
Elasticidade
Confiabilidade
Previsibilidade
Segurança
Governança
Gerenciabilidade
Experiências Práticas
Durante o laboratório, aprendi a:

Customizar a aparência do portal Azure.
Navegar e localizar serviços por categorias dentro da plataforma.
Benefícios da nuvem - Laboratório 19/09/2024 15:15
SLA (Service Level Agreement) e os 9's
No Azure, o SLA define o percentual de disponibilidade garantido para os serviços. A disponibilidade é medida com base no número de "9's", o que impacta diretamente o tempo de indisponibilidade permitido. Abaixo está uma tabela detalhando o tempo de inatividade máximo por nível de SLA em diferentes períodos (semana, mês e ano):

Nível de SLA	Disponibilidade	Tempo Máximo de Inatividade por Semana	Tempo Máximo de Inatividade por Mês	Tempo Máximo de Inatividade por Ano
99%	99%	1,68 hora	7,2 horas	3,65 dias
99.9%	99.9%	10,1 minutos	43,2 minutos	8,76 horas
99.95%	99.95%	5 minutos	21,6 minutos	4,38 horas
99.99%	99.99%	1,01 minutos	4,32 minutos	52,56 minutos
99.999%	99.999%	6 segundos	25,9 segundos	5,26 minutos
Zonas de Disponibilidade
A escolha da zona de disponibilidade é crucial para garantir alta disponibilidade e resiliência contra falhas regionais. Cada região do Azure pode ter várias zonas de disponibilidade, fisicamente separadas, para proteger contra falhas de energia, rede e hardware. É importante levar em consideração a redundância geográfica ao projetar aplicações e serviços para garantir que um incidente em uma zona não afete a operação.

Contas de Armazenamento
No Azure, existem diferentes tipos de contas de armazenamento, cada uma com sua própria precificação. A escolha do tipo de conta afeta o custo com base no desempenho e nas funcionalidades necessárias. Os principais tipos de contas são:

LRS (Locally Redundant Storage): Mantém três cópias dos dados dentro de um único datacenter na mesma região. É a opção mais econômica, mas oferece menor tolerância a falhas regionais.
GRS (Geo-Redundant Storage): Armazena três cópias localmente e mais três cópias em uma região secundária distante. Oferece maior resiliência em caso de desastres, com custo adicional.
ZRS (Zone-Redundant Storage): Replica os dados entre três zonas de disponibilidade diferentes dentro da mesma região, garantindo alta disponibilidade e proteção contra falhas de zona.
GZRS (Geo-Zone-Redundant Storage): Combina replicação entre zonas de disponibilidade e replicação geográfica, armazenando dados em várias zonas em uma região primária e em uma região secundária distante, oferecendo o nível mais alto de resiliência e disponibilidade.
A escolha do tipo de conta depende dos requisitos de disponibilidade, desempenho e custo do projeto.

#21/09/2024

Tipos de Serviço em Nuvem: IaaS, PaaS e SaaS
Na última aula, foram explorados os principais modelos de serviço em nuvem:

IaaS (Infrastructure as a Service)
PaaS (Platform as a Service)
SaaS (Software as a Service).
Cada modelo oferece diferentes níveis de gerenciamento e responsabilidade, conforme descrito abaixo:

IaaS (Infrastructure as a Service): Proporciona recursos de computação em nuvem, como servidores virtuais, armazenamento e redes. O usuário é responsável pela instalação e gerenciamento do sistema operacional e dos aplicativos, enquanto o provedor cuida da infraestrutura física.

PaaS (Platform as a Service): Oferece uma plataforma completa para desenvolvimento, testes e implantação de aplicações. O provedor gerencia a infraestrutura subjacente, permitindo que os desenvolvedores se concentrem no código e na funcionalidade do aplicativo, sem se preocupar com a manutenção do hardware ou do sistema operacional.

SaaS (Software as a Service): Fornece aplicativos prontos para uso, acessíveis pela internet. O provedor é responsável pela manutenção, atualizações e segurança do software. Ao escolher um serviço SaaS, como um banco de dados, o Azure permite selecionar um servidor que será gerenciado pela Microsoft, garantindo sua operação e manutenção.

Tabela de Modelo de Responsabilidade Compartilhada
A seguir, a tabela que ilustra o modelo de responsabilidade compartilhada entre o provedor de nuvem e o cliente, apresentada durante a aula: Modelo de Responsabilidade Compartilhada

Durante a aula, foi demonstrado no portal do Azure como, ao selecionar configurações e a região do serviço, é possível verificar imediatamente o custo associado. Essa funcionalidade permite que os usuários tomem decisões informadas sobre a utilização de serviços em nuvem, otimizando custos e recursos.

Este repositório será atualizado conforme avanço nos estudos e realizo novos laboratórios.
