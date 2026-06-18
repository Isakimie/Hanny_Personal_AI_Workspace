# Hanny - Personal AI Workspace
### Dashboard inteligente de produtividade integrado ao Google Workspace

---

## 📌 Sobre o Projeto

Este projeto foi desenvolvido durante a trilha de aprendizado da **PrograMaria** no **Sprint: IA no Trabalho**. 

O objetivo principal foi a criação de um dashboard inteligente voltado para produtividade. Sob a orientação e mentoria de **Gabriela Surita**, Staff Research Engineer no Google DeepMind, o projeto teve sua primeira versão estruturada de forma ágil e sem programação utilizando a ferramenta **Antigravity**.

---

## 📋 Passo a Passo para Execução

### 1.0 Preparação

#### 1.1 Instalação do Antigravity IDE
O Antigravity funciona como um assistente de código inteligente que entende todo o contexto do seu projeto.

1. Baixe e instale o **Antigravity**.
2. Durante a instalação, quando for exibida a pergunta *"How do you want to use the Antigravity Agent?"*, escolha a opção: **Agent-driven Development**.
   > 💡 *Selecionamos **Agent-driven Development** porque o projeto exige que a IA aja com autonomia e compreenda o contexto completo do escopo para criar a estrutura do código para você.*
4. Faça login utilizando a sua **Conta Google**.
5. **(Opcional) Alterar o idioma para Português:**
   * Caso prefira a interface em português, baixe a extensão **Portuguese (Brazil) Language Pack**.
   * O tutorial completo de configuração pode ser acessado em: [Agentpedia - Change Language](https://agentpedia.codes/pt/blog/change-language).

#### 1.2 Segurança da Conta Google
Para garantir a integração segura com as ferramentas do ecossistema de produtividade:

1. Acesse as configurações de segurança em [Google My Account - Security](https://myaccount.google.com/security).
2. Ative a **Verificação em 2 etapas (2FA)** na sua conta.

### 2.0 Mão na Massa

#### 2.1 Configuração Inicial
1. Crie uma nova pasta no seu computador para concentrar os arquivos do projeto.
2. No ambiente do Antigravity, selecione o modelo de linguagem desejado. 
   > 💡 *Neste projeto, foi utilizado o **Gemini 3.5 Flash Pro (Low)**, mas a escolha do modelo fica a seu critério.*

#### 2.2 Estrutura de Engenharia de Prompt
Para obter o melhor resultado do seu assistente de IA, estruture a sua conversa seguindo esta lógica:

* **a) Contexto:** Defina claramente qual é o objetivo geral do seu projeto.
* **b) Formato:** Especifique a entrega (ex: um dashboard aberto em um arquivo `index.html` que receberá dados do Gmail e Google Calendar).
* **c) Exemplos:** Dê referências. A IA pode ser criativa, mas quanto mais exemplos você fornecer, mais fidedigno ao seu gosto será o resultado.
* **d) Divisão de Tarefas:** Quebre o desenvolvimento em partes. O foco inicial deve ser criar a estrutura do `index.html`; foque em maiores detalhes como gráficos e dados reais apenas nas etapas seguintes.
* **e) Limites:** Estabeleça restrições claras para evitar que o escopo do projeto saia do controle.
* **f) Refinamento:** Peça pequenos ajustes incrementais até o layout ficar como deseja, antes de injetar os dados reais.

#### 2.3 Executando o Primeiro Teste (MVP)
É fundamental **começar pequeno**. Isso evita erros complexos logo no início e facilita a depuração caso algo dê errado. Primeiro, criamos um prompt simples focando apenas no **Contexto** e no **Formato** para validar a criação básica do arquivo HTML.

**Exemplo de prompt utilizado:**
```
Olá! Vou criar um dashboard de início de dia que vai se conectar com Gmail e Google Calendar para me ajudar a não perder tempo
quando chego do trabalho.

Por enquanto, me mostre um arquivo HTML simples com um cabeçalho de saudação "Bem-vinda de volta, Kimie!" "Seu dia já está
organizado. Aqui está o que precisa da sua atenção hoje." e a data de hoje para garantir que tudo está funcionando. Use uma
paleta escura, fonte bonita do Google Fonts, e deixa responsivo. Só isso por enquanto.
```
Apenas com essa instrução inicial, a IA já gera e estrutura um modelo de dashboard funcional e responsivo. Abra o arquivo `index.html` no seu navegador e verifique se a estrutura foi criada corretamente.

Lembre-se de que a IA gera código com certa espontaneidade e criatividade. O resultado obtido neste projeto foi este que você vê abaixo, mas o seu dashboard pode apresentar nuances, cores ou um layout ligeiramente diferentes mesmo usando o mesmo prompt.

Imagem_01

#### 2.3.2 Incrementando o Layout com Exemplos e Limites

Com a estrutura básica funcionando, o próximo passo é dar **Exemplos** dos componentes (cards) que queremos no painel. Quanto mais detalhes fornecermos, melhor será o resultado. 

Contudo, lembre-se da estratégia de **Dividir as tarefas**: não peça lógicas complexas de programação agora para evitar grandes erros, e estabeleça **Limites** claros. Se você gostou da escolha inicial de cores e fontes da IA, mantenha-as; caso queira mudar, este é o momento ideal.

**Prompt de incremento utilizado:**

```
Adicione ao dashboard:
- Três cards de resumo: "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" (com números fictícios por enquanto).
- Uma lista de "Agenda de hoje".
- Um cronômetro estilo Pomodoro.
- Um card: "Foco do dia:".
- Um quadro de tarefas pendentes no estilo Kanban.
- Uma seção para "Foco da semana:" e "Foco do dia".

Não adicione JavaScript ainda — foque apenas na estruturação em HTML e na estilização com CSS.
```
Ao analisar o resultado, o layout pareceu um pouco poluído visualmente. Entramos então na fase de **Refinamento**, onde detalhamos à IA as mudanças pontuais que desejamos para limpar a interface e ajustar as funcionalidades antes de receber os dados reais. No meu caso apenas um pequeno ajuste:

```
Diminua o cronometro do pomodoro e deixe time de 50 com intervalo de 10
```

Obtiver uma resposta satisfatória, então seguimos:
Imagem_02


*****************************
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

```
Adicione:
- Três cards de resumo: "Emails não lidos", "Reuniões hoje" e "Tarefas pendentes" — com números falsos por enquanto
- Uma lista de "Agenda de hoje"
- Um pomodoro
- Um card: "Foco do dia:" - — com números falsos por enquanto
- acrescente um quadro de tarefas pendentes no estilo Kanban
- crie uma sessão "Foco da semana:" e "Foco do dia"

Não precisa de JavaScript ainda — só HTML e CSS.
```
Achei um pouco poluido, então vamos ao Refinamento: 
```
Diminua o cronometro do pomodoro e deixe time de 50 com intervalo de 10
```

Obtiver uma resposta satisfatória
Imagem_02

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
apis e serviços -> Audience ->  Test users e digite seu email

Reinicie a tela e verifique se deu tudo certo
Se aidna assim estão mostrando dados falso apenas peça para substituirem todos os dados falsos pelos verdadeiros agora
Caso ocorrar mais erros, pode jogar no próprio chat o erro e pedi para ajudar a resolver.

ATENÇÃO
Esse projeto não é um incentivo a slops, nos orientou para criarmos nosso primeiro dashboard sem programação. Não descantando o estudo para entender mais profundamente sobre o projeto.....

## 🛠️ Próximos Passos (Roadmap)

- [x] Prototipagem inicial no Antigravity
- [x] Estruturação da documentação (README)
- [ ] Refatoração e reconstrução do código
- [ ] Integração final com APIs do Google Workspace


