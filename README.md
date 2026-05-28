# Hanny - Personal AI Workspace
## Dashboard inteligente de produtividade integrado ao Google Workspace

### 1.0 Preparação

 1.1 Instale o Antigravity (funciona como um assistente de código que entende o contexto do seu projeto)
 1.1.1 Na instalação quando perguntado "How do you want to use the Antigravity Agente?" Escolha: Agent-driven Development
 1.1.2 Entre com sua conta Google
 1.1.1 Caso queira que o progama fique em português é necessário baixar a extensão: Portuguese (Brazil) Language Pack (Tutorial completo em: https://agentpedia.codes/pt/blog/change-language)

 1.2 Ative a verificação em 2 etapas (2FA) na sua conta Google no https://myaccount.google.com/security

 ### 2.0 Mão na massa

 2.1 Crie uma pasta para começarmos
 2.2 Agora vamos começar nosso prompt, seguindo a seguinte ideia:
 a) Contexto: qual será o objetivo do seu projeto
 b) Formato: um dahsboard que vai receber dados do Gmail e Google Calendar e será aberto em um index.html
 c) Exemplos: a IA pode ser criativa, mas quanto mais exemplos você der, mais fidedigno ao que você quer será
 d) Divida as tarefas: por enquanto é foco no design, depois acrescentamos os dados reais através das APIs
 e) Limites: defina limites para seu projeto não sair totalmente do controle
 
 Exemplo utilizado no meu:
 """ texto
Olá! Vou criar um dashboard de início de dia que vai se conectar com Gmail e Google Calendar para me ajudar a não perder tempo quando chego no trabalho.
Crie um index.html num dashboard de início de dia com visual moderno e escuro. O objetivo é que eu abra essa página quando chego no trabalho e saiba imediatamente por onde começar.

Quero ver:
- Um cabeçalho com a saudação "Por onde começo hoje?" e a data de hoje
- Três cards de resumo: "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" — com números falsos por enquanto
- Usa uma paleta escura, fonte bonita do Google Fonts, e deixa responsivo
ransforma o index.html num dashboard de início de dia com visual moderno e escuro. O objetivo é que eu abra essa página quando chego no trabalho e saiba imediatamente por onde começar.

Quero ver:
- Um cabeçalho com a saudação "Por onde começo hoje?" e a data de hoje
- Três cards de resumo: "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" — com números falsos por enquanto
- Usa uma paleta escura, fonte bonita do Google Fonts, e deixa responsivo

Não precisa de JavaScript ainda — só HTML e CSS.
"""
Imagem_01

f) Refinamento: agora vamos pedindo mais ajustes até ficar como deseja, antes de receber os dados reais.
Exemplo no meu caso:
"""
- escolha uma fonte mais arredonda
- escolha um fundo menos solido
- acrescente um quadro de tarefas pendentes
- crie um pomodoro
- crie uma sessão "Foco da semana:" e "Foco do dia"
- crie um quadro kanban
"""

 
