# Sprint 3 - Documentação

## 📌 Objetivo
Refinar funcionalidades do sistema, e implementar portal do administrador:
- Ajustar bugs e padronizar layouts.
- Adicionar um portal para o administrador poder gerenciar dados.
- Adicionar sincronização offline.
- Realizar o deploy da aplicação na AWS.


### Backlog da Sprint

| RANK   | ITEM   | STATUS |
| :----: | :----: | :----: |
|#1|Backlog do produto. | ✅ |
|#2|Backlog da sprint. |✅  |
|#3|Documentação. |  ✅|
|#4|Refinar telas. |  ✅|
|#5|Sinalizar trechos intransitáveis. |  ✅|
|#6|Criar portal do administrador. |  ✅|
|#7|Realizar o login com email e senha no portal do administrador. |  ✅|
|#8|Gerenciar usuários no portal do administrador. |  ✅|
|#9|Revisar relatos no portal do administrador. |  ✅|
|#10|Sincronizar dados. |  ✅|
|#11|Realizar o deploy da aplicação na AWS. |  ✅|

### Críterios de Aceitação

| RANK   | ITEM   | STATUS |
| :----: | :----: | :----: |
#4|Padronizar os designs das telas gerais, remover telas sem uma utilidade definida, utilizar somente um mapa e consertar bugs visuais como a linha para traçar rotas no mapa.| ✅ |
#5|Ao emitir um alerta de estado grave, perguntar se o trecho é intransitável; caso o usuário responda que sim, as rotas não poderão passar mais por aquele ponto, caso possível; caso não seja possível, ao traçar a rota, deve exibir um alerta avisando que o trecho provavelmente está inacessível, mostrando qual o tipo de alerta e as coordenadas dele.| ✅ |
#6|Criar um portal com interface simples, sobria e com navegação intuitiva não necessita de ser algo bonito visualmente, apenas funcional, que apresenta dados gerais em espaços curtos, dando preferência a gráficos e tabelas, tentando seguir padrão de CRMs.|✅  |
|#7|Permitindo o usuário alterar a senha caso tenha esquecido, seguindo o mesmo padrão do aplicativo.|  ✅|
|#8|Ter a possibilidade de ver os dados dos usuários, bem como enviar um e-mail para modificar a senha, ou bloquear/desbloquear um usuário.|  ✅|
|#9|Permitir que o administrador verifique todos os relatos ativos e inativos em uma tabela, na qual deve estar indicado qual o relato, a gravidade dele, o tempo para expirar, quando foi relatado, por quem foi relatado, onde foi relatado (mostrar coordenada, que, ao clicar, vai abrir uma nova aba com um pin do Google Maps no local) e se está expirado ou não.|  ✅|
|#10|Ao emitir um relato, caso o usuário não tenha internet, o relato deve ser enviado para o servidor assim que o usuário tiver uma conexão, ao mesmo ponto que, sempre que o usuário tiver uma conexão, é necessário atualizar os dados das propriedades, para que ele possa utilizá-los offline e assim navegar sem internet.|  ✅|
|#11|Realizar o deploy da API e do portal do administrador na AWS, além de buildar o app.|  ✅|


[⬅️ Voltar para o README principal](../../README.md)