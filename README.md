# 🌤️ Chatbot Telegram --- Consulta de Clima com IA (n8n + OpenWeather + Gemini)

Este projeto implementa um **Chatbot inteligente de clima no Telegram**,
desenvolvido no **n8n**, que consulta a **OpenWeather API** e utiliza
**Google Gemini AI** para gerar respostas educadas, amigáveis e com
humor.

O usuário informa uma cidade brasileira no formato:

Cidade,UF

Exemplo:

Atibaia,SP

------------------------------------------------------------------------

## 📌 Funcionalidades

-   Integração com Telegram Bot
-   Validação inteligente de entrada
-   Consulta em tempo real OpenWeather
-   Respostas humanizadas com Gemini AI
-   Tratamento completo de erros
-   Workflow contínuo após publicação

------------------------------------------------------------------------

## 🗂️ Fluxo do Workflow

Workflow:

Avaliacao1

### Fluxo:

1.  TelegramInTxt --- recebe mensagens.
2.  VariaveisGlobais --- define país BR.
3.  Extrai Dados --- valida Cidade,UF.
4.  dados extraidos? --- IF valida entrada.
5.  pesquisa temperatura --- consulta OpenWeather.
6.  Google Gemini Chat Model --- IA responsável pela linguagem.
7.  Formata Msg Retorno --- gera resposta amigável.
8.  Mensagem Sucesso --- envia resposta Telegram.

Tratamento de erros:

-   formato inválido
-   cidade inexistente
-   erro API
-   erro Gemini

------------------------------------------------------------------------

## 🚀 Importar Workflow

1.  Workflows → Import From File.
2.  Selecione workflow-chatbot-telegram.json.
3.  Salve.

------------------------------------------------------------------------

## 🔐 Configuração Telegram

1.  Abra @BotFather.
2.  Execute /newbot.
3.  Copie Bot Token.

No n8n:

Credentials → New Credential → Telegram API.

Associe aos nodes:

-   TelegramInTxt
-   Mensagem Sucesso
-   Mensagem de Falha

------------------------------------------------------------------------

## 🌤️ Configurar OpenWeather (HTTP Custom Auth)

1.  Credentials → New Credential.
2.  Escolha HTTP Custom Auth.
3.  Nome que deve salvar: openweathermap_key
4.  No campo Json informe: { "qs": { "appid": "SUA_OPENWEATHER_TOKEN" } }
5. Pronto, o workflow irá funcionar com isso.

------------------------------------------------------------------------

## 🤖 Configurar Google Gemini

1.  Gere API Key:

https://aistudio.google.com/app/apikey

No n8n:

Credentials → New Credential → Google Palm API.

Associe ao node:

Google Gemini Chat Model.

------------------------------------------------------------------------

## ▶️ Publicar

Clique Publish ou Active.

------------------------------------------------------------------------

## 🧪 Uso

Enviar:

Cidade,UF

Exemplos:

Atibaia,SP 
Curitiba,PR

------------------------------------------------------------------------
