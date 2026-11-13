# Meu Financeiro — Controle Financeiro Pessoal

Aplicação web responsiva e local-first para registrar receitas e despesas, acompanhar o saldo e visualizar gastos por categoria.

## Funcionalidades iniciais
- Cadastro, edição e exclusão de receitas e despesas.
- Categorias, data, forma de pagamento e observações.
- Resumo de receitas, despesas, saldo e quantidade de lançamentos.
- Filtro por mês, tipo e busca textual.
- Gráfico simples de despesas por categoria.
- Exportação e importação de backup JSON.
- Layout adaptável a desktop e celular.

## Publicação gratuita no GitHub Pages
1. No repositório, abra **Settings → Pages**.
2. Em **Build and deployment**, selecione **Deploy from a branch**.
3. Escolha a branch `main` e a pasta `/ (root)`; salve.
4. Aguarde o Pages publicar. O endereço esperado é https://ldfgl.github.io/controle-financeiro/.

## Privacidade e limitações
Esta primeira versão não possui conta, autenticação, sincronização em nuvem nem backend. Os lançamentos ficam no `localStorage` do navegador e dispositivo usados. O GitHub Pages hospeda apenas os arquivos estáticos; não recebe os lançamentos. Qualquer pessoa com acesso ao mesmo perfil do navegador pode visualizar os dados. Não use em dispositivo compartilhado sem proteção.

Faça backups frequentes pelo botão **Exportar backup**. Limpar os dados do navegador pode apagar os registros. O backup JSON contém dados financeiros em texto legível; guarde-o em local protegido.

A aplicação agora criptografa os lançamentos localmente com AES-GCM (256 bits), usando uma chave derivada da senha por PBKDF2-SHA-256 (310.000 iterações). A senha não é armazenada. O bloqueio automático ocorre após 10 minutos sem atividade. Backups exportados também são criptografados e exigem a senha para importação. Se já existiam lançamentos em uma versão anterior, a primeira criação de senha migra esses dados para o formato criptografado. **A senha esquecida não pode ser recuperada**; mantenha-a em local seguro.\n\nAinda não há integração bancária, leitura automática de extratos, controle de faturas/parcelas, recorrência ou metas. Valores são tratados como números JavaScript nesta versão inicial; não utilizar como sistema contábil ou para decisões de investimento.

## Desenvolvimento
Abra `index.html` diretamente no navegador ou publique pelo GitHub Pages. Não há dependências externas nem etapa de build.

## Roadmap
1. Testes de uso e validação dos lançamentos.
2. Orçamento mensal, despesas recorrentes e parcelamentos.
3. Cartões de crédito e faturas.
4. Metas e projeções financeiras.
5. Relatórios e exportação CSV/Excel.
6. Evoluções futuras: autenticação/sincronização apenas com infraestrutura apropriada.
