# Hanny - Personal AI Workspace
## Dashboard inteligente de produtividade integrado ao Google Workspace

1.0 Preparação

 1.1 Instale o Antigravity (funciona como um assistente de código que entende o contexto do seu projeto)
 1.1.1 Na instalação quando perguntado "How do you want to use the Antigravity Agente?" Escolha: Agent-driven Development
 1.1.2 Entre com sua conta Google
 1.1.1 Caso queira que o progama fique em português é necessário baixar a extensão: Portuguese (Brazil) Language Pack (Tutorial completo em: https://agentpedia.codes/pt/blog/change-language)

 1.2 Ative a verificação em 2 etapas (2FA) na sua conta Google no https://myaccount.google.com/security

2.0 Mão na massa

 2.1 Crie uma pasta para começarmos
 2.2 Selecionei o "Gemini 3 Flash", mas fica a seu critério
 2.3 Agora vamos começar nosso prompt, seguindo a seguinte ideia:
 a) Contexto: qual será o objetivo do seu projeto
 b) Formato: um dahsboard que vai receber dados do Gmail e Google Calendar e será aberto em um index.html
 c) Exemplos: a IA pode ser criativa, mas quanto mais exemplos você der, mais fidedigno ao que você quer será
 d) Divida as tarefas: a principio o foco é criar o index.html e depois focar no design, então acrescentamos gráficos e dados reais
 e) Limites: defina limites para seu projeto não sair totalmente do controle
 f) Refinamento: pedir mais ajustes até ficar como deseja, antes de receber os dados reais.
 
 2.3.1 Primeiro vamos apenas cria um simples prompt para dar o Contexto e o Formato. Então verificar se tudo ocorreu bem na criação do index.html. É importante começarmos pequeno, para evitar erros logo no inicio e se case ocorra, seja de fácil solução.
 Exemplo utilizado:
 
 "
Olá! Vou criar um dashboard de início de dia que vai se conectar com Gmail e Google Calendar para me ajudar a não perder tempo quando chego no trabalho.

Por enquanto, me mostre um arquivo HTML simples com um cabeçalho de saudação "Bem-vinda de volta, Kimie!" "Seu dia já está organizado. Aqui está o que precisa da sua atenção hoje." e a data de hoje para garantir que tudo está funcionando. Use uma paleta escura, fonte bonita do Google Fonts, e deixa responsivo. Só isso por enquanto.
"

Apenas com esse pedido ele já me retornou um modelo de dashboard interessante.
Imagem_01

2.3.2 Tudo certo, então vamos dá Exemplos de cards que queremos, quanto mais detalhes melhor, mas não se esqueça que estamos Dividindo as tarefas, não peça tarefas muito complicadas agora, para evitar grandes erros e também já estabeleça Limites. Eu gostei da escolha de cores e fonte, mas caso queira mudar, essa é a hora!

 "
Adicione:
- Três cards de resumo: "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" — com números falsos por enquanto
- Uma lista de "Agenda de hoje"
- Um pomodoro
- Um card: "Foco do dia:" - — com números falsos por enquanto
- acrescente um quadro de tarefas pendentes no estilo Kanban
- crie uma sessão "Foco da semana:" e "Foco do dia"

Não precisa de JavaScript ainda — só HTML e CSS.
"
Obtive esse resultado:

Imagem_02
Imagem_03

Achei muito poluido, então vamos ao Refinamento: 
"
- Deixe os três cards "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" em quadrados lado a lado
- Suba o "Foco do dia" e o "Foco da semana" para ficar logo abaixo da saudação e também deixe os menor
- Diminua o quadro Pomodoro
- Retire o "Integrações Inteligentes"

"

Obtiver uma resposta satisfatória
Imagem_04

Agora de forma separada vamos acrescentar um gráfico de produtividade para sempre termos um overview mensal:

"
Ao final do dashboard, crie um heatmap mensal de produtividade inspirado no estilo do GitHub Contributions.

- Caso utilize alguma biblioteca auxiliar, importe via CDN (sem instalar nada).
- O heatmap principal deve ser construído com CSS Grid puro.
- Os dados podem ser mockados/inventados por enquanto.
- Cada célula deve representar um dia do mês.
- A intensidade da cor deve variar conforme o nível de produtividade/foco.
- Utilize tons de roxo e verde suaves combinando com o restante da interface.
- O componente deve parecer moderno, minimalista e integrado ao restante do layout.
- Adicione um pequeno título acima: “Consistência do mês”

"

3.0 Dados reais

3.1 Rodando o projeto em um sevidor local
Até agora, você estava abrindo o arquivo HTML diretamente pelo computador. Isso funciona para páginas simples, mas integrações com serviços do Google, como Gmail e Google Calendar, exigem que o projeto esteja rodando em um servidor local.

Como estamos fazendo tudo com vibecoding, vamos pedir para o Antigravity configurar e iniciar esse servidor para nós automaticamente.

"
Sirva este projeto usando um servidor na porta 8000.
"

3.2 Criando as credeciais no Google Cloud
Para acessar o Gmail e o Calendar com a conta do próprio usuário, vamos criar um ID de cliente OAuth no Google Cloud Console. É o que permite que o dashboard peça permissão à conta Google da pessoa que acessar. 

3.2.1 Acesse [console.cloud.google.com](https://console.cloud.google.com/) e faça login com sua conta Google.
3.2.2 My First Project -> Novo Projeto
3.2.3 De o nome ao seu projeto, no meu caso: HannyPersonalAI
3.2.4 Crie seu projeto

Projeto criado, agora vamos criar nossa API
3.2.5 No menu lateral, vá em APIs e Serviços → Biblioteca e ative a Gmail API, Google Calendar API e Google Tasks API.
3.2.6 No mesmo menu lateral na aba APIs e Serviços → Tela de permissão OAuth → Visão Geral e clique em Vamos começar
3.2.7 Preencha:
      Nome do app: [HannyPersonalAI]
      E-mail para suporte ao usuario: [seu e-mail]
      Público: Externo
      Endereços de e-mail: [seu e-mail]
3.2.8 Concorde com os termos de uso e crie

E então agora vamos criar nosssa credencial:
3.2.9 Ainda em Visão geral de OAuth, em Métricas clique em Criar um cliente OAuth
3.2.10 Em Tipo de aplicativo selecione Aplicativo da Web
3.2.11 Em Origens JavaScript autorizadas clique em Adicionar URI e preencha:
      URIs 1: http://localhost:8000
      URIs 2: http://127.0.0.1:8000
3.2.12 Criar e salva o ID do cliente

3.3 Integrando os dados reais

3.3.1 Agora vamos pedir para conectar as APIs do Google ao Client ID
"
Agora vamos integrar o Google Sign-In no dashboard para buscar dados reais.

Usa este Client ID: [cole seu Client ID]

Quero que você:
- Adicione um pequeno botão "Entrar com Google" no canto superior direito do dashboard.
- Após o login, substitua os dados falsos do dashboard (número de emails, reuniões) pelas informações reais da minha conta do Gmail, Google Calendar e Google Tasks para o dia de hoje.
- Use as bibliotecas oficiais do Google para a web (GSI e GAPI).

"

 
