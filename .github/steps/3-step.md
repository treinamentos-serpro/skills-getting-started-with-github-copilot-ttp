## Passo 3: Engate o Hyperdrive - Copilot Agent Mode 🚀

### 📖 Teoria: O que é o Copilot Agent Mode?

O [Agent Mode](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode) do Copilot é a próxima evolução da codificação assistida por IA. Atuando como um par programador autônomo, ele executa tarefas de codificação em múltiplas etapas com base no seu comando.

O Agent Mode reage a erros de compilação e lint, monitora saída de terminal e testes, e corrige em loop até a tarefa ser concluída.

#### Agent Mode (visão rápida)

| Aspecto | 👩‍🚀 Agent Mode |
| --- | --- |
| Autonomia e planejamento | Quebra solicitações de alto nível em trabalho de múltiplas etapas e itera até concluir a tarefa. |
| Coleta de contexto | Usa seu contexto atual e pode descobrir arquivos adicionais relevantes quando necessário. |
| Uso de ferramentas | Seleciona e invoca ferramentas automaticamente; você também pode direcionar ferramentas com menções como `#codebase`. |
| Aprovação e segurança | Ações sensíveis podem exigir aprovação antes da execução, ajudando você a manter o controle. |

#### 🧰 Ferramentas do Agent Mode

O Agent Mode usa ferramentas para executar tarefas especializadas enquanto processa seu pedido. Exemplos:

- Encontrar arquivos relevantes para concluir seu prompt
- Buscar o conteúdo de uma página web
- Executar testes ou comandos de terminal

> [!TIP]
> Embora o VS Code ofereça várias ferramentas nativas, você também pode dar ao Agent Mode recursos mais específicos de domínio por meio de **MCP tools**.
>
> Saiba mais em [MCP servers](https://code.visualstudio.com/docs/copilot/customization/mcp-servers) e [GitHub MCP Server](https://github.com/github/github-mcp-server)

Agora vamos testar o **Agent Mode**! 👩‍🚀

### :keyboard: Atividade: Use o Copilot para adicionar uma nova funcionalidade! :rocket:

Nosso site lista atividades, mas mantém a lista de inscritos em segredo 🤫

Vamos usar o Copilot para atualizar o site e exibir os estudantes inscritos em cada atividade!

1. Na parte inferior da janela do Copilot Chat, use o seletor para trocar para o modo **Agent**.

   <img width="350" alt="image" src="../images/agent-mode-dropdown.png" />

1. Abra os arquivos relacionados à página web e arraste cada aba (ou arquivo) para o painel de chat, informando ao Copilot que eles devem ser usados como contexto.

   - `src/static/app.js`
   - `src/static/index.html`
   - `src/static/styles.css`

   > 🪧 **Nota:** Adicionar arquivos como contexto é opcional. Se você pular isso, o Copilot Agent Mode ainda pode usar ferramentas como `#codebase` para buscar arquivos relevantes a partir do seu prompt. Adicionar arquivos específicos ajuda a apontar o Copilot na direção certa, especialmente em bases de código maiores.

   <img width="400" alt="image showing files added to context" src="../images/files-added-to-context.png" />

   > 💡 **Dica:** Você também pode usar o botão **Add Context...** para fornecer outras fontes de contexto, como uma issue do GitHub ou o resultado de um terminal.

1. Peça ao Copilot para atualizar o projeto e exibir os participantes atuais das atividades. Aguarde os edits chegarem e serem aplicados.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Hey Copilot, can you please edit the activity cards to add a participants section.
   > It will show what participants that are already signed up for that activity as a bulleted list.
   > Remember to make it pretty!
   > ```

   Quando o Copilot terminar, você decide o que permanece.

   Com os botões **Keep** mostrados abaixo, você pode aceitar/descartar todas as mudanças ou revisar uma a uma. Isso pode ser feito no painel de chat ou ao inspecionar cada arquivo editado.

      <img width="900" alt="buttons to keep or discard changes" src="../images/review-changes-buttons.png" />

1. Antes de simplesmente aceitar as alterações, abra o site novamente e verifique se tudo foi atualizado conforme esperado.

   Aqui está um exemplo de card de atividade atualizado. Pode ser necessário reiniciar o app ou atualizar a página.

   <img width="350" alt="Activity card with participant info" src="../images/activity-card-with-participants.png" />

   > 🪧 **Nota:** Seu card pode ficar diferente. O Copilot nem sempre gera o mesmo resultado.

   <details>
   <summary>Precisa de ajuda? 🤷</summary><br/>
   Se o site não estiver carregando, verifique:

   - Reinicie o depurador do VS Code para garantir que a versão mais recente do site está sendo servida.
   - Se esqueceu a URL, ou fechou a janela, revise o passo 1.
   - Faça um hard refresh da página ou abra em janela privada para baixar uma cópia nova.

   </details>

1. Agora que confirmamos que as mudanças estão boas, use o painel para passar por cada edição sugerida e clique em **Keep** para aplicar.

   > 💡 **Dica:** Você pode aceitar as mudanças diretamente, modificá-las, ou dar instruções adicionais no chat para refiná-las.

### :keyboard: Atividade: Use Agent mode para adicionar botões funcionais de "cancelar inscrição"

Vamos experimentar pedidos mais abertos para adicionar novas funcionalidades à aplicação web.

Se não obtiver o resultado desejado, tente outros modelos ou envie feedback de acompanhamento para refinar o resultado.

1. Verifique se o Copilot ainda está no modo **Agent**.

   <img width="250" alt="agent mode" src="../images/agent-mode-dropdown.png" />

1. Clique no ícone de **Tools** e explore todas as ferramentas disponíveis para o Copilot Agent Mode.

   <img width="250"  alt="tools icon" src="../images/tools-icon.png" />

1. Hora do teste! Vamos pedir ao Copilot para adicionar a funcionalidade de remover participantes.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > #codebase Please add a delete icon next to each participant and hide the bullet points.
   > When clicked, it will unregister that participant from the activity.
   > ```

   A ferramenta `#codebase` é usada pelo Copilot para encontrar arquivos e trechos relevantes para a tarefa.

   > 🪧 **Nota:** Neste laboratório incluímos `#codebase` explicitamente para ter resultados mais repetíveis.
   > Fique à vontade para testar o prompt **sem** `#codebase` e observar se o Agent Mode decide coletar contexto mais amplo por conta própria.

1. Quando o Copilot terminar, inspecione as mudanças de código e os resultados no site. Se gostar do resultado, clique em **Keep**. Caso contrário, envie feedback para o Copilot refinar.

   > 🪧 **Nota:** Se não vir atualizações no site, pode ser necessário reiniciar o depurador.

1. Peça ao Copilot para corrigir um bug de registro.

   > 💡 **Dica:** Recomendamos testar o fluxo de registro por conta própria para observar com clareza o comportamento antes/depois.

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > I've noticed there seems to be a bug.
   > When a participant is registered, the page must be refreshed to see the change on the activity.
   > ```

1. Quando o Copilot terminar, revise o resultado e valide o fluxo de inscrição no site.

   Se gostar do resultado, clique em **Keep**. Se não, forneça feedback adicional ao Copilot.

1. Faça **commit** e **push** de todas as mudanças no branch `accelerate-with-copilot`.

1. Aguarde a Mona verificar seu trabalho e compartilhar o próximo passo.
