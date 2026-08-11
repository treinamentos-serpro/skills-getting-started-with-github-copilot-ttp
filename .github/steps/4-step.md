## Passo 4: Planeje sua implementação com o Plan Agent 🧭

No passo anterior, o Agent Mode nos ajudou a avançar rápido e entregar novas funcionalidades. 🚀

Agora vamos desacelerar por uma rodada e trabalhar como arquitetos: primeiro definir uma boa abordagem de testes e depois delegar a implementação. Isso traz mais clareza, menos surpresas e resultados mais limpos. 🧪

### 📖 Teoria: O que é o Copilot Plan Agent?

O [Plan Agent](https://code.visualstudio.com/docs/copilot/agents/planning) do Copilot ajuda você a desenhar uma solução antes de qualquer alteração de código.

Em vez de pular direto para edições, ele pesquisa sua solicitação, faz perguntas de esclarecimento e cria um plano de implementação que você pode refinar.

#### Plan Agent (visão rápida)

| Aspecto | 🧭 Plan Agent |
| --- | --- |
| Propósito | Cria um plano estruturado de implementação antes da codificação começar. |
| Coleta de contexto | Usa pesquisa somente leitura para entender requisitos e restrições. |
| Estilo de colaboração | Faz perguntas de esclarecimento e depois atualiza o plano com base nas suas respostas. |
| Iteração | Suporta múltiplas rodadas de refinamento antes da implementação. |
| Segurança | Não edita arquivos até você aprovar o plano e transferir para o **Agent Mode**. |
| Handoff | O botão **Start implementation** transfere o plano aprovado para o **Agent Mode** implementar o código. |

> [!TIP]
> Você pode começar com uma solicitação de alto nível e depois adicionar restrições e detalhes em prompts de acompanhamento.

### ⌨️ Atividade: Planeje e implemente testes de backend

Seu backend ainda tem cobertura de testes zero. Use o **Plan Agent** para criar um plano, responder perguntas e iniciar a implementação.

1. Abra o painel do **Copilot Chat** e troque para **Plan Agent**.

   <img width="350" alt="image" src="../images/plan-mode-dropdown.png" />


1. Vamos começar com um prompt amplo e o Copilot vai ajudar a preencher os detalhes:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > I want to add backend FastAPI tests in a separate tests directory.
   > ```

1. Aguarde o Copilot gerar o primeiro plano. Se ele fizer perguntas, responda da melhor forma possível.

   > 🪧 **Nota:** Não se preocupe em acertar tudo de primeira. Você sempre pode refinar o plano depois.

1. Você pode refinar o plano e fornecer detalhes adicionais em prompts de acompanhamento.

   Exemplos:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Let's use the AAA (Arrange-Act-Assert) testing pattern to structure our tests
   > ```

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Make sure we use `pytest` and add it to `requirements.txt` file
   > ```


1. Revise o plano proposto e, quando estiver satisfeito, clique em **Start implementation** para transferir para o **Agent Mode**.

   <img width="350" alt="image" src="../images/plan-mode-start-implementation.png" />

   Note que ao clicar no botão você mudou de **Plan** para **Agent Mode**. A partir daqui, o Copilot pode editar sua base de código, como antes.

1. Acompanhe o Copilot implementando o plano que você criou. Ele pode pedir permissões para usar algumas ferramentas (por exemplo, executar comandos ou criar ambientes virtuais). Aprove para permitir a continuidade.

1. Revise as mudanças e garanta que os testes executem com sucesso. Se necessário, continue guiando até a implementação ficar completa.

   **🎯 Objetivo: deixar todos os testes passando (verde) antes de avançar. ✅**

   > 🪧 **Nota:** O Agent Mode pode concluir isso em uma passada, ou pode precisar de prompts adicionais.

1. Faça **commit** e **push** de todas as mudanças no branch `accelerate-with-copilot`.

1. Aguarde a Mona verificar seu trabalho e compartilhar o próximo passo.

<details>
<summary>Tendo problemas? 🤷</summary><br/>

- Se os testes não rodarem, peça ao Copilot para executá-los.
- Verifique se `pytest` foi adicionado em `requirements.txt` e se existe um diretório `tests/`.

</details>
