# Contribuir

1. Cria uma branch curta a partir de `main`, como `feat/registo-treino`, `fix/rota-inicial` ou `docs/desenvolvimento`.
2. Instala com `npm ci`. Mantém o âmbito da alteração claro e atualiza a documentação afetada.
3. Corre `npm run typecheck`, `npm run lint`, `npm test --if-present` e `npx expo-doctor`. Indica o que verificaste manualmente.
4. Faz commits pequenos, usando `tipo: descrição`. Exemplos em inglês: `feat: record workout sets`, `fix: handle expired sessions`, `docs: describe offline behavior`. Usa também `chore`, `refactor` ou `test` quando adequado.
5. Abre um pull request para `main`, liga a issue se existir e pede revisão. Integra após revisão e validação da CI.

Mantém a interface e os documentos em português de Portugal. Usa dados fictícios, retira informação pessoal de capturas e logs e segue a [política de segurança](SECURITY.md) ao comunicar vulnerabilidades. O [guia de desenvolvimento](docs/development.md) descreve a configuração local.
