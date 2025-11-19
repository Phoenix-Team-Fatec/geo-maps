# API-5 — GeoMaps (Visiona)

<span id="topo"></span>
<h1 align="center"> FATEC SJC - 5º Semestre ADS — Visiona </h1>
<br>

## 📍 Objetivo

<h4>Desenvolver um aplicativo móvel (Android/React Native) para endereçamento digital de imóveis do CAR, roteirização rural, registro colaborativo de condições de vias e exibição de alertas, com arquitetura de microsserviços e foco em usabilidade e evolução contínua.</h4>

<br><br>

## ➯ Backlog do Produto

| Rank | Prioridade | US | Estimativa | Sprint | Requisitos do parceiro |
|------|------------|----|------------|--------|--------------------------|
| #1 | Alta | Como proprietário rural, quero me cadastrar no aplicativo para acessar meus imóveis do CAR. | 8 | 1 | RF1 |
| #2 | Alta | Como usuário, quero conseguir entrar no aplicativo sem fazer log-in. | 5 | 1 | RF2 |
| #3 | Alta | Como proprietário rural, quero ver a lista de propriedades associadas ao meu CPF para escolher qual gerenciar. | 5 | 1 | RF3 |
| #4 | Alta | Como proprietário rural, quero visualizar minhas propriedades no mapa para entender sua localização. |  5 | 1 | RF4 |
| #5 | Alta | Como proprietário rural, quero atribuir um Plus Code ao ponto de acesso principal da propriedade para criar um endereço digital. |  8 | 1 | RF5 |
| #6 | Alta | Como proprietário rural, quero editar/atualizar o Plus Code da propriedade quando o ponto de acesso mudar. |  3 | 1 | RF7 |
| #7 | Alta | Como proprietário rural, quero receber um certificado digital toda vez que alterar/criar um Plus Code de uma propriedade. |  3 | 1 | RF6 |
| #8 | Alta | Como usuário, quero registrar condições de vias (tipo, severidade) georeferenciadas para informar a comunidade. | 8 | 2 | RF8 |
| #9 | Alta | Como usuário, quero visualizar no mapa as condições das vias reportadas para planejar deslocamentos. | 5 | 2 | RF12 |
| #10 | Baixa | Como usuário, quero ver o histórico de alterações do Plus Code/endereçamento da minha propriedade para controle. |  3 | 2 | RF7 |
| #12 | Alta | Como usuário, quero traçar rotas para outras propriedades. | 13 | 2 | RF14 |
| #13 | Alta | Como usuário, quero traçar rotas de forma fácil para a minha propriedade. | 13 | 2 | RF14 |
| #14 | Média | Como usuário, quero receber notificações push quando houver novos alertas ou mudanças relevantes nas vias que sigo. | 5 | 2 | RF12 |
| #15 | Média | Como usuário, quero sinalizar trechos intransitáveis e obter rota alternativa automaticamente. | 8 | 3 | RF15 |
| #16 | Alta | Como administrador, gostaria de ter um portal para observar logs e gerenciar usuários. | 5 | 3 |  |
| #17 | Média | Como administrador, quero revisar/recusar relatos de via para evitar abusos e informações falsas. | 8 | 3 | RF10 |
| #18 | Média | Como usuário, quero registrar relatos offline e sincronizar quando houver conexão para não perder informações. | 8 | 3 |  |
| #19 | Baixa | Como usuário, quero configurar preferências de notificação para evitar alertas indesejados. |  3 | 3 | RF13 |
| #20  | Média | Como usuário, quero poder acessar o serviço pelo servidor da AWS. | 3 | 3 |  |

<br><br>

## 🧭 Requisitos Funcionais

| Código | Descrição (derivada das US) |
|:-----:|:------------------------------|
| RF1 | O sistema deve permitir autenticação usando JWT. Perfis: Público (anônimo/sem login), Proprietário (cadastro simples), Administrador (cadastro simples). |
| RF2 | O sistema deve aplicar controle de acesso por perfil: Público: acesso apenas a dados não sensíveis (traçar rotas, visualizar alertas gerais). Proprietário: acesso aos dados sensíveis apenas dos seus imóveis, criar alertas gerais de rotas. Administrador: acesso a todos os dados para fins de gestão. |
| RF3 | Listar Imóveis do Proprietário: Após login, o usuário deve visualizar todos os imóveis rurais associados ao seu CPF (lista e mapa). |
| RF4 | No mapa/lista, imóveis com Plus Code aparecem em azul e sem Plus Code em vermelho. |
| RF5 | Definir Endereço Digital O usuário deve definir o Plus Code do imóvel: arrastando um pino no mapa ou usando a localização GPS do dispositivo no local. |
| RF6 | Geração de Certificado. Ao definir/atualizar o Plus Code, o app deve gerar um “certificado de endereço digital” (PDF/arquivo) e enviar por e-mail ao proprietário. O certificado deve conter: nome do proprietário, identificação do imóvel (CAR/ID), Plus Code, coordenadas, data/hora, e hash/ID de validação. |
| RF7 | Edição/Atualização de Plus Code. O proprietário pode atualizar o ponto/Plus Code do imóvel, com histórico de alterações (auditoria). |
| RF8 | Publicar Condições de Via. Usuários podem cadastrar pontos/trechos com informações de condição da via (ex.: atoleiro, ponte danificada, estrada interditada, buracos, tráfego lento). |
| RF9 | Classificação e Metadados Cada publicação deve ter: tipo de ocorrência, data/hora e validade (expira em X horas/dias (ainda está aí?)). |
| RF10 | Proprietários e Admins podem sinalizar conteúdo indevido; Admin pode aprovar/ocultar/remover. |
| RF11 | O app deve consumir alertas meteorológicos em tempo (quase) real para a região dos imóveis e das vias cadastradas. |
| RF12 | O app deve relacionar trechos de via e imóveis afetados por um alerta (ex.: chuva intensa → risco de alagamento na estrada X). |
| RF13 | Proprietários podem ativar notificações push/e-mail para alertas que afetem seus imóveis/rotas salvas. |
| RF14 | O app deve traçar rotas entre dois pontos usando a API do Google Maps. |
| RF15 | Ao traçar a rota, o app deve exibir avisos sobre trechos: Com alertas meteorológicos ativos; Com ocorrências colaborativas recentes. |
| RF16 | Admin pode visualizar estatísticas (nº de imóveis endereçados, alertas ativos). |
| RF17 | Todas as ações sensíveis (definir/alterar Plus Code, moderação, vinculações) devem ser logadas. |

<br><br>

## 🔐 Requisitos Não Funcionais (RNF)

- Manual de Instalação (no repositório).
- Manual do Usuário (no repositório).
- Documentação de API.
- Modelagem de dados (BD ou arquivo).
- Autenticação com JWT.
- Interface simples, responsiva e intuitiva.
- Navegação com GPS integrada a Mapas e suporte a uso offline/sincronização.
- Arquitetura de microsserviços.

<br><br>

## 🗺️ MVP

![MVP Placeholder](.assets/MVP.png)

<br>

## 🗂️ Documentos das Sprints

- [Sprint 1](./documentos/Sprint%201/README.md) — Autenticação, propriedades (lista/detalhe), Plus Code (criar/editar), base de UI e dados.
- [Sprint 2](/documentos/Sprint2/README.md) — Registro/visualização de vias no mapa, rotas, histórico, notificações.
- [Sprint 3](/documentos/Sprint3/README.md) — Portal admin/moderação, preferências de notificação, offline/sync.

<br>

## 🛠️ Tecnologias

- React Native, TypeScript/JavaScript
- Android/Android SDK
- Django (APIs e serviços)
- Banco NoSQL (MongoDB) / Persistência JSON
- Microsserviços, JWT, GPS/Mapas

<br>

## 👥 Equipe

| Função | Nome | LinkedIn | GitHub |
|:-----:|:----:|:--------:|:------:|
| Product Owner | João Victor Menezes | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/jvictormo) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/jvictormo) |
| Scrum Master | Vinicius Peretta | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/vinicius-assis-peretta-5a2436227) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/Peretta) |
| Dev Team | 	Gabriel Silva | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/gabriel-silva--cs) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/gabrielfelip) |
| Dev Team | Guilherme Sato | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/guilherme-sato-42b609292) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/gsatocode) |
| Dev Team | 	Gustavo Villela | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/gustavo-villela-a9314b268) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/TaldoGus) |
| Dev Team | Larissa Colucci | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/larissa-colucci-996393295) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/LarissaCGomes) |
| Dev Team | 	Matheus Andrade | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/matheus-santos-b1a65b1ba) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/MatheusAndrade1999) |
| Dev Team | 	Matheus Marques | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/matmarquesx) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/matmarquesx) |
| Dev Team | 	Samuel Alkmin | [<img height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/LinkedIn.svg">](https://www.linkedin.com/in/samuel-alkmin-machado-52743a292) | [<img align="center" height="30px" src="https://github.com/tandpfun/skill-icons/blob/main/icons/Github-Dark.svg"/>](https://github.com/samekmd) |

<br>

→ [Voltar ao topo](#topo)

---
