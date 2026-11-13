# Segurança e privacidade

## Proteções implementadas
- Lançamentos criptografados antes de serem gravados no localStorage, usando AES-GCM com chave de 256 bits.
- Derivação da chave com PBKDF2-HMAC-SHA-256 e salt aleatório por instalação (310.000 iterações).
- Senha não é armazenada no navegador; a chave derivada permanece apenas em memória durante a sessão.
- Bloqueio automático após 10 minutos sem atividade e bloqueio manual.
- Backups exportados em formato criptografado; a senha é necessária para importá-los.
- Migração dos lançamentos legados em texto simples na primeira configuração da senha.

## Limitações e cuidados
- A senha esquecida não pode ser recuperada. Backups também dependem dela.
- A criptografia protege os dados armazenados quando a aplicação está bloqueada/fechada, mas não protege contra malware, extensões maliciosas ou scripts comprometidos enquanto os dados estão desbloqueados.
- Não armazene senhas bancárias, credenciais, números completos de cartão ou outros segredos.
- Proteja o computador e o perfil do navegador com senha e mantenha o sistema operacional atualizado.
- O GitHub Pages hospeda os arquivos estáticos, não os lançamentos. A aplicação não envia dados financeiros para um backend.
- O backup é um arquivo sensível, embora criptografado; mantenha uma cópia em local seguro.
- Limpar os dados do navegador sem backup pode causar perda definitiva dos registros.
- Esta implementação é uma proteção local de aplicação, não uma auditoria independente de segurança.

Para relatar uma vulnerabilidade, não publique dados financeiros ou detalhes exploráveis em uma issue pública.
