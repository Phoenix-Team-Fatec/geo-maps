# Manual do Usuário - GeoMaps (Visiona)

## 📋 Índice


1. [📱 Sobre o Sistema](#-sobre-o-sistema)
2. [💻 Requisitos](#-requisitos)
3. [🚀 Instalação](#-instalação)
4. [🎯 Primeiros Passos](#-primeiros-passos)
5. [👥 Funcionalidades por Perfil](#-funcionalidades-por-perfil)
6. [📖 Guia de Uso](#-guia-de-uso)
7. [❓ Perguntas Frequentes](#-perguntas-frequentes)
8. [🆘 Suporte Técnico](#-suporte-técnico)
9. [📝 Notas da Versão](#-notas-da-versão)
10. [🏆 Créditos](#-créditos)

---

## 📱 Sobre o Sistema

O **GeoMaps** é um aplicativo móvel desenvolvido para endereçamento digital de imóveis rurais cadastrados no CAR (Cadastro Ambiental Rural), oferecendo recursos de roteirização rural, registro colaborativo de condições de vias e alertas meteorológicos em tempo real.

### Principais Objetivos

- Facilitar o endereçamento digital de propriedades rurais usando **Plus Codes**
- Fornecer roteirização inteligente para áreas rurais
- Permitir registro colaborativo de condições de estradas e vias
- Integrar alertas meteorológicos relevantes para propriedades e rotas
- Gerar certificados digitais de endereçamento

### Tecnologias Utilizadas

- **Frontend**: React Native com Expo
- **Backend**: FastAPI (Python)
- **Banco de Dados**: MongoDB (NoSQL)
- **Mapas**: Google Maps API
- **Autenticação**: JWT (JSON Web Tokens)

---

## 💻 Requisitos

### Requisitos Mínimos do Dispositivo

- **Sistema Operacional**: Android 8.0 (Oreo) ou superior
- **Memória RAM**: Mínimo 2 GB
- **Armazenamento**: 100 MB livres
- **Conectividade**: Internet móvel ou Wi-Fi (algumas funções offline disponíveis)
- **GPS**: Obrigatório para funcionalidades de localização

### Permissões Necessárias

O aplicativo solicitará as seguintes permissões:
- 📍 **Localização**: Para identificar sua posição e propriedades
- 📷 **Câmera**: Para captura de evidências de condições de vias
- 📁 **Armazenamento**: Para salvar certificados e dados offline
- 🔔 **Notificações**: Para alertas meteorológicos e atualizações

---

## 🚀 Instalação

### Instalação do Aplicativo

#### Frontend (React Native)

```bash
# Clone o repositório
git clone https://github.com/Phoenix-Team-Fatec/geo-maps-frontend.git
cd geo-maps-frontend

# Instale as dependências
npm install

# Inicie o servidor de desenvolvimento
npx expo start
```

#### Frontend (React Vite)

```bash
# Clone o repositório
git clone https://github.com/Phoenix-Team-Fatec/geomaps_admin_portal.git
cd app

# Instale as dependências
npm install

# Inicie o servidor de desenvolvimento
npm run dev
```

#### Backend (FastAPI)

```bash
# Clone o repositório
git clone https://github.com/Phoenix-Team-Fatec/geo-maps-backend.git
cd geo-maps-backend

# Crie um ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Instale as dependências
pip install -r requirements.txt

# Inicie o servidor
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

---

## 🎯 Primeiros Passos

### 1. Primeiro Acesso

Ao abrir o aplicativo pela primeira vez, você verá três opções:

#### Opção A: Acesso Público (Sem Cadastro)
- Toque em **"Continuar sem login"**
- Você terá acesso limitado às funcionalidades públicas:
  - Visualizar condições de vias reportadas
  - Traçar rotas
  - Ver alertas gerais

#### Opção B: Cadastro como Proprietário Rural
1. Toque em **"Cadastrar"**
2. Preencha os dados solicitados:
   - Nome completo
   - CPF (será usado para vincular propriedades do CAR)
   - E-mail
   - Telefone celular
   - Senha (mínimo 8 caracteres)
3. Aceite os termos de uso
4. Toque em **"Criar Conta"**
5. Confirme seu e-mail através do link enviado

#### Opção C: Login
1. Toque em **"Entrar"**
2. Digite seu CPF e senha
3. Toque em **"Acessar"**

### 2. Configuração Inicial

Após o login/cadastro:

1. **Permita o acesso à localização** quando solicitado
2. **Configure suas preferências de notificação**:
   - Alertas meteorológicos
   - Condições de vias
   - Atualizações de rotas salvas
3. **Sincronize seus dados** (se houver conexão disponível)

---

## 👥 Funcionalidades por Perfil

O sistema possui três perfis de usuário:

### 🌐 Usuário Público (Anônimo)

**Permissões**:
- ✅ Visualizar condições de vias reportadas no mapa
- ✅ Traçar rotas entre pontos
- ✅ Consultar alertas meteorológicos gerais
- ❌ Não pode registrar propriedades
- ❌ Não pode reportar condições de vias
- ❌ Não recebe notificações personalizadas

**Ideal para**: Visitantes, turistas ou usuários que desejam apenas consultar informações de rotas.

---

### 🏡 Proprietário Rural

**Permissões**:
- ✅ Todas as funcionalidades do Usuário Público
- ✅ Visualizar propriedades vinculadas ao CPF
- ✅ Criar endereço digital (Plus Code) para propriedades
- ✅ Editar e atualizar Plus Codes
- ✅ Gerar certificados digitais de endereçamento
- ✅ Registrar condições de vias (colaborativo)
- ✅ Receber notificações sobre propriedades e rotas
- ✅ Salvar rotas favoritas
- ✅ Acessar histórico de alterações de endereçamento
- ✅ Denunciar conteúdo indevido

**Ideal para**: Donos de propriedades rurais cadastradas no CAR.

---

### 👨‍💼 Administrador

**Permissões**:
- ✅ Acessar portal administrativo web
- ✅ Moderar e revisar relatos de condições de vias
- ✅ Aprovar, ocultar ou remover publicações
- ✅ Visualizar logs de ações sensíveis
- ✅ Acessar estatísticas gerais do sistema
- ✅ Gerenciar usuários

**Ideal para**: Gestores do sistema, moderadores e equipe técnica.

---

## 📖 Guia de Uso

### 🏠 Gerenciamento de Propriedades

#### Visualizar Minhas Propriedades

1. Acesse o menu principal
2. Toque em **"Minhas Propriedades"**
3. Você verá duas visualizações:
   - **Lista**: Exibe nome, código CAR e status do Plus Code
   - **Mapa**: Mostra a localização geográfica das propriedades

**Código de Cores no Mapa**:
- 🔵 **Azul**: Propriedade com Plus Code definido
- 🔴 **Vermelho**: Propriedade sem Plus Code

#### Criar Endereço Digital (Plus Code)

O Plus Code é um código curto que representa coordenadas geográficas, facilitando o endereçamento de áreas sem CEP tradicional.

**Método 1: Usando GPS no Local**
1. Vá até o ponto de acesso principal da sua propriedade
2. No app, selecione a propriedade
3. Toque em **"Definir Plus Code"**
4. Toque em **"Usar Minha Localização Atual"**
5. Confirme a localização no mapa
6. Toque em **"Salvar"**

**Método 2: Arrastando o Pino no Mapa**
1. Selecione a propriedade
2. Toque em **"Definir Plus Code"**
3. Toque em **"Marcar no Mapa"**
4. Arraste o pino vermelho até o local desejado
5. Toque em **"Confirmar Localização"**
6. Toque em **"Salvar"**

**Após salvar**:
- ✅ O Plus Code será gerado automaticamente
- ✅ Um certificado digital será enviado para seu e-mail
- ✅ A propriedade ficará azul no mapa

#### Certificado Digital de Endereçamento

O certificado contém:
- Nome do proprietário
- Identificação do imóvel (Código CAR)
- Plus Code gerado
- Coordenadas geográficas (latitude/longitude)
- Data e hora da criação
- Hash de validação (para autenticidade)

**Como acessar**:
1. Verifique seu e-mail cadastrado
2. O arquivo estará em formato PDF

#### Editar Plus Code

Se o ponto de acesso da propriedade mudou:

1. Selecione a propriedade
2. Toque em **"Editar Plus Code"**
3. Escolha o novo local (GPS ou mapa)
4. Toque em **"Atualizar"**
5. Um novo certificado será gerado e enviado

**Histórico de Alterações**:
- Acesse **"Minhas Propriedades" → Propriedade → "Histórico"**
- Visualize todas as alterações de Plus Code
- Veja data, hora e coordenadas anteriores

---

### 🛣️ Condições de Vias

#### Registrar Condição de Via

Ajude a comunidade reportando problemas nas estradas:

1. No mapa principal, toque no botão **"+"** (flutuante)
2. Ou toque em **"Reportar Via"** no menu
3. Selecione o **tipo de ocorrência**:
   - 🌊 Atoleiro
   - 🌉 Ponte danificada
   - 🚧 Estrada interditada
   - 🕳️ Buracos
   - 🚗 Tráfego lento
   - ⚠️ Outros perigos
4. Adicione **Nível de severidade** (Baixo/Médio/Alto)
5. Defina se a rota é transitavel ou não
7. Toque em **"Publicar"**

**Importante**:
- Relatos podem ser revisados por administradores
- Conteúdo indevido pode ser removido
- Abuse responsável desta funcionalidade

---

### 🗺️ Roteirização

#### Traçar Rota Simples

1. Toque na caixa de texto no menu superior
2. Digite ou selecione:
   - **Origem**: Sua localização, uma propriedade ou endereço
   - **Destino**: Propriedade, Plus Code ou endereço
3. Toque em **"Calcular Rota"**

O aplicativo mostrará:
- Traçado da rota no mapa
- Distância total
- Tempo estimado
- ⚠️ **Alertas no caminho** (vias com problemas)
- 🌦️ **Condições meteorológicas** previstas

#### Rotas para Minhas Propriedades

**Acesso Rápido**:
1. Na lista de propriedades, toque no ícone de **navegação** (🧭)
2. A rota será calculada automaticamente da sua localização atual

**Ou**:
1. Acesse **"Rotas"**
2. Em destino, toque em **"Minhas Propriedades"**
3. Selecione a propriedade desejada

#### Rotas com Trechos Problemáticos

Quando houver problemas na rota:

1. O app exibirá **avisos** em laranja/vermelho
2. Toque em **"Ver Detalhes do Alerta"**
3. Você verá:
   - Tipo e severidade do problema
   - Localização exata
4. Opções:
   - **"Seguir Mesmo Assim"**: Continua pela rota original
   - **"Rota Alternativa"**: Recalcula evitando o trecho
   - **"Ver no Mapa"**: Visualiza o problema antes de decidir

#### Tipos de Alertas Meteorológicos

O sistema integra alertas em tempo real:

- 🌧️ **Chuva intensa**: Risco de alagamento
- ⛈️ **Tempestades**: Raios e ventos fortes
- 🌊 **Enchentes**: Rios transbordando
- 🌪️ **Vendaval**: Ventos acima de 60 km/h
- ❄️ **Geada**: Temperaturas abaixo de 0°C
- 🔥 **Baixa umidade**: Risco de incêndio

**Como funcionam**:
- Alertas são relacionados às suas propriedades
- Você recebe notificação se houver risco
- O mapa exibe áreas afetadas
- Rotas mostram trechos com alerta ativo

---

### 📶 Uso Offline

#### Modo Offline

O app funciona **parcialmente sem internet**:

**O que funciona**:
- ✅ Visualizar propriedades já carregadas
- ✅ Ver rotas salvas (mapa básico em cache)
- ✅ Registrar condições de vias (sincroniza depois)
- ✅ Marcar Plus Codes (sincroniza depois)

**O que NÃO funciona**:
- ❌ Calcular novas rotas
- ❌ Ver alertas meteorológicos em tempo real
- ❌ Atualizar condições de vias de outros usuários
- ❌ Enviar certificados por e-mail
---

### 🔐 Segurança e Privacidade

#### Dados Pessoais

O GeoMaps leva sua privacidade a sério:

- 🔒 Senhas são criptografadas
- 🔑 Autenticação via JWT (token seguro)
- 📊 CPF usado apenas para vincular propriedades do CAR
- 📧 E-mail usado apenas para certificados e alertas
- 🚫 Não compartilhamos dados com terceiros

#### Controle de Acesso

**Usuários Públicos**:
- Veem apenas dados não sensíveis
- Não têm acesso a detalhes de propriedades

**Proprietários**:
- Acessam apenas **suas próprias** propriedades
- Não veem dados de outros proprietários

**Administradores**:
- Acesso completo para fins de gestão
- Todas as ações são **logadas** (auditoria)

#### Histórico e Auditoria

Todas as ações sensíveis são registradas:
- Criação/edição de Plus Codes
- Moderação de conteúdo
- Alterações em propriedades
- Acesso a dados sensíveis
---
### 🖥️ Portal Administrativo
O GeoMaps possui um **portal web administrativo** separado para gerenciamento avançado do sistema, acessível apenas para usuários com perfil de Administrador.

#### Funcionalidades do Portal
#### 👥 Gerenciamento de Usuários
**Menu: Usuários → Lista de Usuários**

**Funções disponíveis**:
1. **Buscar usuários**: Por CPF, nome, e-mail
2. **Bloquear usuários**: (Com confirmação e log)

#### 🛣️ Moderação de Vias

**Menu: Vias → Relatos Pendentes**

**Sistema de moderação**:
1. **Visualizar relato**:
   - Tipo de ocorrência
   - Localização no mapa
   - Data e hora de registro
   - Data e hora de expiração
---

## ❓ Perguntas Frequentes

### Sobre o Sistema

**P: O que é um Plus Code?**  
R: É um código curto baseado em coordenadas geográficas, desenvolvido pelo Google, que funciona como um "endereço digital" para locais que não têm CEP tradicional. Exemplo: `7QGW+2X São José dos Campos`

**P: Preciso ter propriedade no CAR para usar?**  
R: Não! Usuários públicos podem usar funções de rota e visualização. Mas para vincular propriedades e criar Plus Codes, você precisa estar cadastrado no CAR e ter CPF vinculado.

**P: O aplicativo funciona em iOS?**  
R: Por enquanto, apenas Android. Versão iOS em desenvolvimento.

**P: Posso usar em tablet?**  
R: Sim, desde que tenha GPS e Android 8.0+.

### Sobre Propriedades

**P: Minhas propriedades não aparecem no app. Por quê?**  
R: Verifique se:
- Seu CPF está correto no cadastro
- As propriedades estão ativas no CAR
- Você fez login (não é usuário público)
- Há conexão com a internet para sincronizar

**P: Posso ter mais de um Plus Code por propriedade?**  
R: Não. Cada propriedade tem um único Plus Code que representa o ponto de acesso principal. Mas você pode editar sempre que necessário.

**P: O certificado digital tem validade jurídica?**  
R: O certificado serve como comprovante de endereçamento digital. Para fins jurídicos, consulte órgãos competentes como INCRA e cartórios.

**P: Posso deletar uma propriedade?**  
R: Não pelo app. Propriedades vêm do CAR. Para remover, você deve atualizar no sistema oficial do CAR.

### Sobre Rotas e Vias

**P: O app funciona sem internet para rotas?**  
R: Rotas **salvas** podem ser visualizadas offline (com mapa básico em cache). Para calcular **novas rotas**, é necessário internet.

**P: Por que minha rota não evita trechos ruins?**  
R: O algoritmo prioriza segurança, mas pode não haver rota alternativa viável. Você pode verificar manualmente e escolher outro caminho.

### Sobre Segurança

**P: Esqueci minha senha. Como recuperar?**  
R: Na tela de login, toque em **"Esqueci minha senha"**, digite seu CPF ou e-mail, e siga as instruções enviadas para seu e-mail cadastrado.

**P: Posso trocar o CPF vinculado?**  
R: Não. O CPF é fixo pois vincula você às propriedades do CAR. Se houver erro, entre em contato com o suporte.

---

## 🆘 Suporte Técnico

### Recursos Adicionais

**📚 Documentação Técnica**:
- [API Backend](https://github.com/Phoenix-Team-Fatec/geo-maps-backend)
- [Frontend React Native](https://github.com/Phoenix-Team-Fatec/geo-maps-frontend)
- [Projeto Principal](https://github.com/Phoenix-Team-Fatec/geo-maps)

---

## 📝 Notas da Versão

### Versão Atual: 1.0.0

**Funcionalidades Implementadas**:
- ✅ Autenticação JWT e perfis de usuário
- ✅ Visualização de propriedades do CAR
- ✅ Criação e edição de Plus Codes
- ✅ Geração de certificados digitais
- ✅ Registro colaborativo de condições de vias
- ✅ Roteirização com alertas
- ✅ Integração com alertas meteorológicos
- ✅ Notificações push
- ✅ Modo offline básico
- ✅ Portal administrativo
- ✅ Sistema de moderação

---

## 🏆 Créditos

**Desenvolvido por**: Phoenix Team - FATEC São José dos Campos  
**Parceiro**: Visiona Tecnologia Espacial  
**Licença**: Proprietária  

---

**Última atualização deste manual**: Novembro de 2025  
**Versão do manual**: 1.0

---

*Este é um documento vivo e será atualizado conforme novas funcionalidades forem implementadas. Sugestões de melhorias são bem-vindas!*