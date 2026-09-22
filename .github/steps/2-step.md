## Passo 2: Detectar vulnerabilidades em um Pull Request

Para ver como o Code Scanning funciona, vamos introduzir uma vulnerabilidade no arquivo `routes.py` para disparar um alerta.

### ⌨️ Atividade: Criar uma vulnerabilidade

1. Na navegação superior, selecione a aba **Code**.

1. Navegue até a pasta `server` e selecione o arquivo `routes.py`.

1. No canto superior direito da pré-visualização, clique no botão **Edit**.

   <img width="500" alt="botão de edição" src="../images/edit-button.png"/>

1. Vá até aproximadamente a **linha 16** e altere-a para o conteúdo abaixo.

   ```py
   "SELECT * FROM books WHERE name LIKE '%" + name + "%'"
   ```

1. Acima do editor, no canto superior direito, clique no botão **Commit changes...**. Na janela exibida, selecione a opção **Create a new branch**. **NÃO faça commit na branch main.**

1. Clique na opção **Propose changes** e depois em **Create pull request**. Use o nome de branch abaixo.

   ```txt
   learning-codeql
   ```

1. Na nova página, abaixo da descrição do pull request, clique no botão **Create pull request**.

### ⌨️ Atividade: Revisar o pull request

1. Se necessário, navegue até o pull request criado na atividade anterior.

1. Role até o final do pull request e procure por um check chamado `CodeQL`. Esse é o job de análise que está escaneando as mudanças propostas no pull request.

   <img width="500" alt="check do CodeQL em andamento" src="../images/codeql-check-in-progress.png" />

1. Se o job ainda estiver em execução, aguarde alguns minutos até que ele termine.

1. Procure nos comentários para encontrar os resultados da análise.
   - Note que os resultados encontraram uma vulnerabilidade de SQL injection. Também é sugerida uma correção.
   - Não se preocupe em responder ou resolver o problema (ainda).

   <img width="500" alt="resultados do code scan" src="../images/code-scan-results.png" />

   > 💡 Dica: Clicar no link **Show paths** fornece informações adicionais sobre o fluxo de dados do alerta, desde a entrada do usuário (source), passando pela aplicação, até o ponto em que é utilizado (sink).

### ⌨️ Atividade: Visualizar os logs de scanning do CodeQL

1. Na navegação superior, selecione a aba **Actions**.

1. Na navegação lateral esquerda, selecione a entrada **CodeQL** para filtrar as execuções do workflow.

   <img width="500" alt="filtro do codeql" src="../images/codeql-filter.png"/>

1. Clique na execução do workflow com o nome **PR #2** para abrir uma página com mais detalhes.

   <img width="500" alt="configuração do codeql" src="../images/codeql-pr2.png"/>

1. Expanda os jobs da execução clicando em **Show all jobs** e depois clique na entrada **Analyze (python)**. A lista de todos os steps do workflow será exibida.

   <img height="250" alt="jobs de matrix" src="../images/matrix-jobs.png" />

   <img height="250" alt="lista de jobs do codeql" src="../images/list-of-codeql-jobs.png" />

1. Encontre a entrada de análise e considere revisar os logs.

   <img width="500" alt="logs da análise em python" src="../images/python-analysis-logs.png" />

1. Com o pull request criado e o scan do CodeQL concluído, a Mona vai verificar seu progresso e compartilhar os próximos passos.

> [!TIP]
> Confira a página [Triage code scanning alerts in pull requests](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/triaging-code-scanning-alerts-in-pull-requests) para saber mais sobre a integração do code scanning com pull requests.
