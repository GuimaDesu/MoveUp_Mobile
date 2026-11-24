# Segurança e privacidade

## Ambiente de desenvolvimento

Usa dados fictícios e projetos Firebase de teste autorizados. Qualquer ligação à base de dados real do ginásio exige autorização prévia. Mantém ficheiros de assinatura, tokens, chaves privadas e contas de serviço fora do Git, dos logs e do código distribuído. As variáveis `EXPO_PUBLIC_*` entram no bundle e servem apenas para a configuração pública do cliente. Em caso de exposição de um segredo, revoga-o ou roda-o e comunica o incidente pelo canal privado.

## Acesso e armazenamento previstos

- Usar Firebase Authentication para autenticação e recuperação de palavra-passe. Aplicar as permissões também no Firestore e Firebase Storage.
- Negar acessos por omissão. Autorizar leituras e escritas conforme a identidade autenticada, a propriedade do recurso e as atribuições do ginásio. Validar campos, intervalos e alterações a campos protegidos.
- Testar regras no Firebase Emulator Suite, incluindo pedidos anónimos, acessos cruzados entre clientes, alterações de propriedade e caminhos de media.
- Separar ambientes e limitar os privilégios de administração. Qualquer operação que use credenciais do Admin SDK corre num serviço de confiança.
- Isolar a cache SQLite e as operações pendentes por conta, definir a limpeza ao terminar sessão e considerar a proteção local necessária para os dados que persistem. Evitar dados pessoais em notificações, telemetria e relatórios de erro.

Consulta a [documentação das regras Firebase](https://firebase.google.com/docs/rules/basics).

## RGPD

Antes de tratar dados reais, documentar com o ginásio quem é responsável pelo tratamento, as finalidades, a base de licitude, os dados estritamente necessários, os prazos de conservação e as medidas de proteção. Definir como prestar informação aos clientes e responder a pedidos de exercício de direitos. Avaliar se algum dado recolhido revela informação sobre saúde e que requisitos adicionais se aplicam. Referência oficial no [Regulamento Geral sobre a Proteção de Dados](https://eur-lex.europa.eu/eli/reg/2016/679/oj).
