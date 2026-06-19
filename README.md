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

### 2.0 Estruturação

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
<br><br>
 ![image alt](https://github.com/Isakimie/Hanny_Personal_AI_Workspace/blob/87b93d151708bf1f8157e536cbf5312eca21eee3/Imagens/Imagem_01.png)
 <br><br>
#### 2.4 Incrementando o Layout com Exemplos e Limites

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
<br><br>
 ![image alt](https://github.com/Isakimie/Hanny_Personal_AI_Workspace/blob/87b93d151708bf1f8157e536cbf5312eca21eee3/Imagens/Imagem_02.png)
<br><br>
Agora, de forma separada, vamos acrescentar um gráfico de produtividade para termos sempre um *overview* mensal do nosso desempenho. A ideia é criar um componente visualmente impactante e integrado.

**Prompt de incremento utilizado:**

```
Abaixo do Foco da Semana, crie um heatmap mensal de produtividade inspirado no estilo do GitHub Contributions.

- Caso utilize alguma biblioteca auxiliar, importe via CDN (sem instalar nada).
- O heatmap principal deve ser construído com CSS Grid puro.
- Os dados podem ser mockados/inventados por enquanto.
- Cada célula deve representar um dia do mês.
- A intensidade da cor deve variar conforme o nível de produtividade/foco.
- Utilize tons de roxo e verde suaves combinando com o restante da interface.
- O componente deve parecer moderno, minimalista e integrado ao restante do layout.
- Adicione um pequeno título acima: “Consistência do mês”
```
O meu resultado ficou assim! Sinta-se à vontade para acrescentar ou modificar qualquer componente que achar necessário para ajudar na sua organização diária, antes de seguirmos para o passo 3.
<br><br>
![Interface do Dashboard Refinado](https://github.com/Isakimie/Hanny_Personal_AI_Workspace/blob/78f4354cfc1aff6887426f29621bb29ba4f6e53c/Imagens/Imagem_03.png)
<br><br>
### 3.0 Implementando Dados Reais

#### 3.1 Rodando o Projeto em um Servidor Local

Até agora, você estava abrindo o arquivo `index.html` diretamente pelo computador (dando dois cliques nele). Isso funciona perfeitamente para páginas estáticas e simples, mas integrações seguras com serviços do Google, como Gmail e Google Calendar, exigem obrigatoriamente que o projeto esteja rodando dentro de um **servidor local** (localhost).

Como estamos fazendo todo o desenvolvimento na abordagem de *vibecoding*, vamos delegar essa configuração de infraestrutura e pedir para o Antigravity configurar e iniciar esse servidor para nós de forma automática.

**Prompt utilizado para iniciar o servidor:**

```
Sirva este projeto usando um servidor na porta 8000.
```

#### 3.2 Criando as Credenciais no Google Cloud

Para que o dashboard acesse o Gmail e o Google Calendar com a conta do próprio usuário de forma segura, precisamos criar um **ID de cliente OAuth** no Google Cloud Console. É essa configuração que permite que o painel peça a permissão necessária à conta Google da pessoa que o estiver acessando.

**Passo a Passo:**

1. Acesse o site [console.cloud.google.com](https://console.cloud.google.com/) e faça login com a sua conta Google.
2. No menu superior esquerdo, clique no seletor de projetos (geralmente nomeado como *My First Project*) e selecione a opção **Novo Projeto**.
3. Dê um nome de identificação ao seu projeto. *No meu caso, utilizei o nome:* `HannyPersonalAI`.
4. Clique no botão **Criar** para concluir a abertura do projeto no painel.

#### 3.3 Ativando as APIs necessárias
Para que o assistente consiga ler as suas informações, precisamos habilitar o acesso aos serviços correspondentes na biblioteca do Google:

1. No menu lateral esquerdo, navegue até **APIs e Serviços** → **Biblioteca**.
2. Na barra de pesquisa, busque e clique em **Ativar** para cada uma das seguintes APIs:
   * **Gmail API**
   * **Google Calendar API**
   * **Google Tasks API**

#### 3.4 Configurando a Tela de Consentimento OAuth
Esta é a tela de segurança que avisa ao usuário quais dados o dashboard vai acessar antes de fazer o login.

1. No menu lateral, acesse **APIs e Serviços** → **Tela de consentimento OAuth**.
2. Na seção de visão geral, clique no botão **Vamos começar**.
3. Preencha o formulário de identificação do app com as seguintes informações:
   * **Nome do app:** `HannyPersonalAI`
   * **E-mail para suporte ao usuário:** *[Insira o seu e-mail da conta Google]*
   * **Público:** Selecione a opção **Externo**
   * **Informações de contato do desenvolvedor (Endereços de e-mail):** *[Insira o seu e-mail novamente]*
4. Avance pelas etapas subsequentes aceitando as configurações padrão, concorde com os termos de uso e conclua a criação da tela.

#### 3.5 Gerando o ID do Cliente OAuth
Com a tela de consentimento salva, o próprio painel do Google mostrará uma página de resumo. É através dela que vamos gerar as chaves de acesso para o dashboard:

1. Ainda na tela de **Visão geral de OAuth**, na seção **Métricas** clique no botão **Criar um cliente OAuth**.
4. No campo **Tipo de aplicativo**, selecione a opção: **Aplicativo da Web**.
5. Vá até a seção **Origens JavaScript autorizadas**, clique no botão **Adicionar URI** e preencha com os dois endereços locais abaixo:
   * **URIs 1:** `http://localhost:8000`
   * **URIs 2:** `http://127.0.0.1:8000`
6. Clique no botão **Criar** no final da página.
7. Uma janela pop-up será exibida com as suas chaves. Copie e salve com segurança o **ID do cliente** (Client ID), pois precisaremos dele na próxima etapa.

### 3.6 Conectando o Painel às APIs do Google
Com o seu Client ID em mãos, vamos instruir a IA a criar a lógica de autenticação e substituir todos os elementos fictícios do dashboard por informações dinâmicas do seu dia.

**Prompt de integração utilizado:**

```
Agora vamos integrar o Google Sign-In no dashboard para buscar dados reais.

Usa este Client ID: [Cole aqui o seu Client ID gerado no passo anterior]

Quero que você:
- Adicione um pequeno botão "Entrar com Google" no canto superior direito do dashboard.
- Após o login, substitua todos os dados falsos do dashboard (número de e-mails, reuniões...) pelas informações reais da minha conta do Gmail, Google Calendar e Google Tasks para o dia de hoje.
- Use as bibliotecas oficiais do Google para a web (GSI e GAPI).
```
#### 3.7 Configuração de Usuários de Teste

Como o projeto está em ambiente de desenvolvimento, o Google exige que você autorize explicitamente quem pode fazer login:

1. No menu lateral do Google Cloud Console, acesse **APIs e Serviços** → **Audience** → **Test users**.
2. Clique em adicionar usuários e digite o seu e-mail do Google.
3. Reinicie a tela do seu dashboard (`http://localhost:8000`) e verifique se o login ocorreu com sucesso.

> 💡 **Dica de Debug:** Se mesmo após o login o painel ainda mostrar dados fictícios, envie um prompt direto à IA: *"Substitua todos os dados falsos remanescentes pelas variáveis reais que vêm da API agora."* Caso ocorram outros erros no console, copie a mensagem, jogue no próprio chat do assistente e peça ajuda para resolver.

#### 3.8 Resultado Final 🎉

Assim ficou o meu dashboard, agora totalmente funcional e integrado com as minhas informações reais em tempo real!
<br><br>
![Dashboard Final com Dados Reais Integrados](https://github.com/Isakimie/Hanny_Personal_AI_Workspace/blob/82adcaecbdd7285c6cda6518f67664866109362f/Imagens/Imagem_04.png)
<br><br>
Parabéns! Se você chegou até aqui, o seu **Personal AI Workspace** está pronto, configurado e rodando localmente de forma segura. 🚀
<br><br>
## ⚠️ ATENÇÃO:
Este projeto **não é um incentivo à criação de *slops*** (códigos superficiais ou descartáveis gerados por IA sem critérios). A proposta aqui foi guiar o desenvolvimento do seu primeiro dashboard funcional utilizando engenharia de prompt e *vibecoding*, permitindo que você tire uma ideia do papel sem travar nas barreiras iniciais da sintaxe da programação.

**Isso não descarta a necessidade do estudo aprofundado.** Usar a IA para estruturar a base é uma excelente alavanca de produtividade, mas compreender o HTML, CSS e JavaScript por trás do código é o que vai te diferenciar.
<br>

---
<p align="center">
  <small>Projeto de <b>Isabela Ota</b>, realizado no curso PrograMaria Sprint IA no trabalho 2026 com a mentoria de <b>Gabriela Surita</b> - Staff Research Engineer no Google DeepMind.</small>
</p>

