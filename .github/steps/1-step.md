## Passo 1: Habilitar o Code Scanning

Vamos começar aprendendo um pouco sobre code scanning com [CodeQL](https://codeql.github.com/) e como ele ajuda a proteger seu código.

### O que é o GitHub Code Scanning?

O [Code scanning](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning) faz parte do conjunto de produtos [GitHub Advanced Security (GHAS)](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security). Ele permite que times de desenvolvimento integrem ferramentas de teste de segurança diretamente no mesmo processo que já usam para entregar código. Há suporte a diversos tipos, como SAST, contêineres e infrastructure as code. E o melhor: os resultados ficam diretamente no GitHub, ao lado do seu código. Sem necessidade de trocar de contexto! 🎉

> [!TIP]
> Todos os recursos do GitHub Advanced Security são gratuitos para repositórios públicos. Já repositórios privados exigem uma [conta paga](https://docs.github.com/en/billing/managing-billing-for-your-products/managing-billing-for-github-advanced-security/about-billing-for-github-advanced-security) compatível.

### O que é o CodeQL?

O [CodeQL](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql) é uma ferramenta de análise estática que ajuda a identificar fragilidades de segurança, como SQL injection, cross-site scripting e problemas de code injection.

Normalmente, as [queries](https://codeql.github.com/docs/writing-codeql-queries/about-codeql-queries/) do CodeQL são reunidas em [query suites](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning-with-codeql#about-codeql-queries) para cobrir múltiplos padrões. Quando bem combinadas, isso pode ser muito poderoso! Para facilitar, times de especialistas em segurança já disponibilizam suites prontas para diversos cenários e linguagens de programação comuns.

Em muitos casos, aproveitar o CodeQL é tão simples quanto aceitar a suite padrão, mas você também pode selecionar a suite estendida ou personalizar a sua própria com [GitHub Actions]().

<img width="250" align="right" alt="caixa de configuração padrão do codeql" src="../images/codeql-default-configuration-box.png"/>

Estas são algumas das opções fornecidas pela configuração padrão:

- **Languages:** As linguagens suportadas serão detectadas automaticamente no seu repositório e o scanning será habilitado.

- **Query suites:** Uma lista das suites de padrões disponíveis que serão utilizadas. As opções **Default** ou **Extended** são fornecidas automaticamente.

- **Runner type:** Tipo de runner do GitHub Actions que executará a análise do CodeQL. O padrão são os Standard GitHub Hosted Runners, mas é possível personalizar para usar [self-hosted runners](https://docs.github.com/en/enterprise-cloud@latest/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/configuring-code-scanning-for-your-appliance).

- **Events:** Gatilhos para executar um scan do CodeQL. É comum executar antes do merge e de forma agendada para código de produção.

### ⌨️ Atividade: Habilitar code scanning com CodeQL

1. Abra uma segunda aba e navegue até este repositório. Certifique-se de estar na aba **Code**.

1. Na navegação superior, selecione a aba **Settings**.

1. Na navegação lateral esquerda, encontre a seção **Security** e selecione **Advanced Security**.

1. Role a página para baixo e localize a área **Code scanning**.

1. Na configuração do **CodeQL**, clique no menu suspenso **Set up** e escolha **Default**.

   <img width="400" alt="habilitar code scanning" src="../images/enable-code-scanning.png"/>

1. Clique em **Enable CodeQL**.

   > 💡 Dica: Isso vai disparar a primeira execução do CodeQL. Você pode acompanhar o progresso na aba **Actions**.

1. Com o CodeQL habilitado, a Mona vai verificar seu progresso e compartilhar os próximos passos.
