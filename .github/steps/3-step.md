## Passo 3: Revisar e triar alertas do CodeQL

Com as mudanças do nosso pull request revisadas pelo CodeQL, agora temos alguns resultados para visualizar. Vamos aprender sobre a gestão de alertas.

O GitHub oferece a aba **Security and quality** para gerenciar com segurança todas as questões relacionadas à segurança. O CodeQL salva os alertas usando o mesmo padrão de muitas outras ferramentas de análise, e os resultados aparecem na área **Code scanning**.

<img width="600" alt="visão geral da aba security" src="../images/security-tab-overview.png" />

### Quais informações os alertas fornecem?

A área principal de um alerta mostra o status de resolução, a branch afetada, a localização no código e informações de classificação, como severidade e [número de identificação CVE](https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/about-repository-security-advisories#cve-identification-numbers).

Depois das informações de status, são apresentados uma descrição detalhada do problema, soluções recomendadas e sugestões de mudanças no código.

<img width="600" alt="informações adicionais" src="../images/additional-information.png"/>

### O que é CWE?

Muitos dos padrões que o CodeQL procura vêm de bases de dados existentes de vulnerabilidades, que são categorizadas para facilitar o entendimento.

O **Common Weakness Enumeration (CWE)** é um sistema de categorização de fragilidades e vulnerabilidades de hardware e software. Pense nele como uma forma de descrever e classificar problemas de segurança no código-fonte de uma aplicação. Para mais informações sobre CWEs, veja o artigo da Wikipédia [Common Weakness Enumeration](https://en.wikipedia.org/wiki/Common_Weakness_Enumeration).

### ⌨️ Atividade: Visualizar alertas existentes

1. Na navegação superior, selecione a aba **Security and quality**.

1. Na navegação lateral esquerda, localize a área **Findings** e selecione a opção **Code scanning**.
   - Note que não há alertas. Isso é esperado, já que o código vulnerável do pull request ainda não foi mesclado.

1. Volte ao pull request criado recentemente. Ignore o check que falhou e clique no botão **Merge pull request**.

   <img width="300" alt="botão de merge" src="../images/merge-button.png" />

1. Clique em **Delete branch**. Ela não é mais necessária.

1. Aguarde um momento para o CodeQL analisar as novas mudanças na branch `main`.

1. Volte para a aba **Security and quality**.

1. Na navegação lateral esquerda, note que a opção **Code Scanning** agora tem o número `1` ao lado, informando que há um alerta aberto.

   <img width="250" alt="contagem de alertas do code scanning" src="../images/code-scanning-alerts-count.png" />

### ⌨️ Atividade: Revisar um alerta

1. Na navegação lateral esquerda, selecione a opção **Code scanning**.

1. Clique no alerta aberto.

1. Observe a descrição, a explicação da vulnerabilidade e a solução recomendada.

   <img width="600" alt="visão geral do alerta" src="../images/alert-overview.png" />

1. Note que a trilha de auditoria mostra a origem da vulnerabilidade e indica que ela veio do nosso pull request.

### ⌨️ Atividade: Descartar e reabrir um alerta

1. No canto superior direito, clique no menu suspenso **Dismiss alert**.

1. Selecione a opção `Used in tests` e informe a descrição abaixo.

   ```md
   Este é um repositório de aprendizado para estudar alertas do CodeQL.
   ```

   <img width="300" alt="opções de descarte do alerta" src="../images/dismiss-alert-options.png" />

1. Clique no botão **Dismiss**.
   - O estado do alerta mudará para `Dismissed`.
   - Uma entrada somente leitura foi adicionada com a descrição na trilha de auditoria, mostrando quem o fechou.

   <img width="300" alt="entrada do log de auditoria mostrando o alerta descartado" src="../images/audit-log-alert-dismissed.png" />

1. No canto superior direito, clique no botão **Reopen alert**.
   - O estado do alerta voltará para `Open`.
   - Uma entrada somente leitura foi adicionada à trilha de auditoria mostrando quem o reabriu.

1. Com um alerta fechado e reaberto, adicione um comentário nesta issue pedindo para a Mona verificar nosso progresso e compartilhar os próximos passos.

   > ⚠️ **Importante:** mantenha o texto abaixo em inglês. O workflow verifica as palavras-chave `professortocat` e `alert` para liberar o próximo passo.

   ```md
   Hey @professortocat, I've closed an reopened an alert. What is the next step?
   ```
