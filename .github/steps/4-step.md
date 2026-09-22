## Passo 4: Corrigir vulnerabilidades de segurança

Por fim, vamos usar as informações fornecidas pelo CodeQL para entender melhor a vulnerabilidade e corrigi-la.

### ⌨️ Atividade: Resolver um alerta aberto

1. Revise o alerta aberto e familiarize-se com as mudanças recomendadas.

1. Na navegação superior, selecione a aba **Code**.

1. Certifique-se de estar na branch `main`, depois navegue até a pasta `server` e selecione o arquivo `routes.py`.

1. No canto superior direito da pré-visualização, clique no botão **Edit**.

   <img width="500" alt="botão de edição" src="../images/edit-button.png"/>

1. Vá até aproximadamente a **linha 16** e altere-a para o conteúdo abaixo.

   ```py
   "SELECT * FROM books WHERE name LIKE %s", name
   ```

1. Acima do editor, no canto superior direito, clique no botão **Commit changes...**. Use as opções padrão para fazer o commit diretamente na branch `main`.
   - O CodeQL iniciará um novo scan.

1. Aguarde um momento até o workflow do **CodeQL** terminar.

1. Volte para a aba **Security and quality**, na área **Code Scanning**.
   - Não deve haver nenhum alerta aberto e deve existir 1 alerta fechado. Bom trabalho! 🎉
   - Fique à vontade para revisar os alertas fechados, especialmente a trilha de auditoria.

1. Clique em **Closed** para exibir o alerta que acabamos de resolver.

   <img width="350" alt="botão de alertas fechados" src="../images/closed-alerts-button.png" />

1. Abra o alerta e note que a trilha de auditoria agora inclui como o alerta foi corrigido.

   <img width="350" alt="trilha de auditoria do alerta corrigido" src="../images/audit-trail-fixed-alert.png" />

1. Com o alerta corrigido, a Mona vai verificar seu progresso e compartilhar a revisão final. Bom trabalho! Você concluiu tudo! 🥳
