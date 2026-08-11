## Passo 1: Olá Copilot

Bem-vindo ao seu exercício **"Primeiros Passos com GitHub Copilot"**! :robot:

Neste exercício, você usará diferentes recursos do GitHub Copilot para trabalhar em um site que permite que estudantes da Mergington High School se inscrevam em atividades extracurriculares. 🎻 ⚽️ ♟️

<img width="600" alt="screenshot of Mergington High School WebApp" src="../images/mergington-high-school-webapp.png" />

### 📖 Teoria: Conhecendo o GitHub Copilot

<img width="150" align="right" alt="copilot logo" src="../images/copilot-logo.png" />

O GitHub Copilot é um assistente de codificação com IA que ajuda você a escrever código mais rápido e com menos esforço, permitindo que você concentre mais energia na resolução de problemas e colaboração.

O GitHub Copilot comprovadamente aumenta a produtividade dos desenvolvedores e acelera o ritmo do desenvolvimento de software. Para mais informações, veja [Research: quantifying GitHub Copilot's impact on developer productivity and happiness no blog do GitHub.](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)

Ao trabalhar no seu IDE, você interagirá com o GitHub Copilot mais frequentemente das seguintes formas:

| Modo de Interação              | 📝 Descrição                                                                                                                                                     | 🎯 Melhor Para                                                                                                               |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **⚡ Inline suggestions**      | Sugestões de código com IA que aparecem enquanto você digita, oferecendo completações contextuais desde linhas únicas até funções inteiras.                      | Completar a linha atual, às vezes um bloco inteiro de código novo                                                            |
| **💭 Inline Chat**             | Chat interativo com escopo no seu arquivo atual ou seleção. Faça perguntas sobre blocos de código específicos.                                                   | Explicações de código, depuração de funções específicas, melhorias direcionadas                                              |
| **💬 Ask Mode**                | Otimizado para responder perguntas sobre sua base de código, programação e conceitos gerais de tecnologia.                                                       | Entender como o código funciona, fazer brainstorming de ideias, tirar dúvidas                                                |
| **🤖 Agent Mode**              | Modo recomendado por padrão para a maioria das tarefas de codificação: edições autônomas, uso de ferramentas e continuidade até concluir a tarefa.               | Tarefas diárias de codificação, desde correções pontuais até implementações maiores em múltiplos arquivos                   |
| **🧭 Plan Agent**              | Otimizado para elaborar um plano e fazer perguntas de esclarecimento antes de qualquer alteração de código.                                                      | Quando você quer revisar um plano primeiro e depois seguir para a implementação                                              |

Ao trabalhar, você descobrirá que o GitHub Copilot pode ajudar em vários lugares no site `github.com` e nos seus ambientes de codificação favoritos como VS Code, JetBrains e Xcode!

Para a codificação de hoje, vamos praticar com o VS Code em um ambiente de desenvolvimento pré-configurado conhecido como [GitHub Codespace](https://github.com/features/codespaces).

> [!TIP]
> Você pode aprender mais sobre recursos atuais e futuros na documentação [GitHub Copilot Features](https://docs.github.com/en/copilot/about-github-copilot/github-copilot-features).

### :keyboard: Atividade: Obtenha uma introdução ao projeto pelo Copilot Chat

Vamos iniciar nosso ambiente de desenvolvimento, usar o Copilot para aprender um pouco sobre o projeto e depois fazer um teste de execução.

1. Use o botão abaixo para abrir a página **Create Codespace** em uma nova aba. Use a configuração padrão.

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

1. Confirme que o campo **Repository** é a sua cópia do exercício, não o original, e clique no botão verde **Create Codespace**.

   - ✅ Sua cópia: `/{{full_repo_name}}`
   - ❌ Original: `/dev-pods/getting-started-with-github-copilot`

1. Aguarde um momento para o Visual Studio Code carregar no seu navegador.

1. Na barra lateral esquerda, clique na aba de extensões e verifique se as extensões `GitHub Copilot` e `Python` estão instaladas e habilitadas.

   <img width="350" alt="copilot extension for VS Code" src="../images/copilot-extension-vscode.png" />

   <img width="350" alt="python extension for VS Code" src="../images/python-extension-vscode.png" />

1. No topo do VS Code, localize e clique no ícone **Toggle Chat** para abrir um painel lateral do Copilot Chat.

   <img width="150" alt="image" src="../images/toggle-chat-icon.png" />

   > 🪧 **Nota:** Se esta é sua primeira vez usando o GitHub Copilot, você precisará aceitar os termos de uso para continuar.

1. Certifique-se de que está no **Ask Mode** para nossa primeira interação

   <img width="350" alt="screenshot showing Ask Mode selection in Copilot Chat" src="../images/ask-mode-selection.png" />

1. Digite o prompt abaixo para pedir ao Copilot que apresente o projeto para você.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Por favor, explique brevemente a estrutura deste projeto.
   > O que devo fazer para executá-lo?
   > ```

   > 🪧 **Nota:** Não é necessário seguir as instruções recomendadas pelo Copilot. Nós já preparamos o ambiente para você.

1. Agora que sabemos um pouco mais sobre o projeto, vamos realmente tentar executá-lo! Na barra lateral esquerda, selecione a aba `Run and Debug` e pressione o ícone **Start Debugging**.

   <img width="300" alt="image" src="../images/run-and-debug-tab.png" />

1. Queremos ver nossa página web rodando em um navegador, então vamos encontrar a URL e a porta. Se não estiver visível, expanda o painel inferior e selecione a aba **Ports**.

1. Na lista, encontre a porta `8000` e o link relacionado. Passe o mouse sobre o link e selecione o ícone **Open in browser**.

   ![image](../images/open-in-browser-icon.png)

### :keyboard: Atividade: Use o Copilot para ajudar a lembrar um comando de terminal 🙋

Ótimo trabalho! Agora que estamos familiarizados com o app e sabemos que funciona, vamos pedir ajuda ao Copilot para criar um branch para podermos fazer algumas personalizações.

1. No painel inferior do VS Code, selecione a aba **Terminal** e no lado direito clique no sinal de mais `+` para criar uma nova janela de terminal.

   > 🪧 **Nota:** Isso evitará parar a sessão de debug existente que está hospedando nosso serviço de aplicação web.

1. Dentro da nova janela de terminal, use o atalho de teclado `Ctrl + I` (Windows) ou `Cmd + I` (Mac) para abrir o **Copilot's Terminal Inline Chat**.

1. Vamos pedir ao Copilot para nos ajudar a lembrar um comando que esquecemos: criar um branch e publicá-lo.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Ei Copilot, como posso criar e publicar um novo branch Git chamado "accelerate-with-copilot"?
   > ```

   > 💡 **Dica:** Se o Copilot não der exatamente o que você quer, você sempre pode continuar explicando o que precisa. O Copilot lembrará o histórico da conversa para respostas de acompanhamento.

1. Pressione o botão `Run` para deixar o Copilot inserir o comando de terminal para nós. Não precisa copiar e colar!

1. Após um momento, olhe na barra de status inferior do VS Code, no lado esquerdo, para ver o branch ativo. Agora deve mostrar `accelerate-with-copilot`. Se sim, você terminou este passo!

1. Agora que seu branch foi enviado para o GitHub, a Mona já deve estar ocupada verificando seu trabalho. Dê a ela um momento e fique de olho nos comentários. Você verá ela responder com informações de progresso e a próxima lição.

<details>
<summary>Tendo problemas? 🤷</summary><br/>

Se você não receber feedback, aqui estão algumas coisas para verificar:

- Certifique-se de que criou o branch com o nome exato `accelerate-with-copilot`. Sem prefixos ou sufixos.
- Certifique-se de que o branch foi realmente publicado no seu repositório.

</details>
