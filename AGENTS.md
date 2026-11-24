# Instruções para trabalhar no MoveUp Connect

O MoveUp Connect é uma PAP do Curso Profissional de Técnico de Programação Informática (2026/2027), em colaboração com o MoveUp Fitness Action, em Pombal, Portugal. O projeto inclui website institucional em React, aplicação móvel e área de administração. Este repositório contém a aplicação móvel Android e iOS. O objetivo é que os clientes passem menos tempo ao telemóvel enquanto ocupam uma máquina. Privilegia fluxos curtos para consultar planos e exercícios, registar resultados e acompanhar a evolução.

## Stack e documentação Expo

Usa React Native, Expo, TypeScript estrito, Expo Router e Hermes. A evolução prevê Firebase Authentication, Cloud Firestore, Firebase Storage, SQLite, Expo Notifications e EAS Build. Usa Git e GitHub para controlo de versões. A distribuição final é nativa e independente do Expo Go. Adiciona dependências quando a funcionalidade as exigir e dá preferência aos módulos recomendados pelo Expo.

Antes de alterar código que usa Expo, EAS ou React Native:

1. Confirma a versão principal de `expo` em `package.json`.
2. Consulta `https://docs.expo.dev/versions/v<major>.0.0/`.
3. Consulta o [índice Expo](https://docs.expo.dev/llms.txt) e segue a ligação para a referência da API em causa. Confirma o comportamento na versão instalada.

Instala dependências com `npx expo install <pacote>`. O repositório usa npm e mantém `package-lock.json`. Usa `bunx` em vez de `npx` se o projeto passar a usar Bun e tiver `bun.lock`. Consulta o [Expo Router](https://docs.expo.dev/router/introduction.md) e o [EAS](https://docs.expo.dev/eas/index.md). Usa `npx eas-cli@latest` para os comandos EAS. Os projetos nativos são gerados por Continuous Native Generation. Faz alterações em `app.json` ou config plugins. Usa uma compilação de desenvolvimento quando uma alteração exigir módulos nativos ausentes do Expo Go.

## Arquitetura e qualidade

- Coloca rotas e layouts em `src/app/` e mantém a lógica de negócio nos módulos em `src/features/` quando forem necessários. Importa `Link`, `router` e `useLocalSearchParams` de `expo-router`.
- Reutiliza componentes quando houver casos concretos. Separa interface, dados fictícios e lógica. Cria adaptadores de dados e migrações com os primeiros fluxos que os usarem.
- Escreve código e identificadores em inglês. Usa português de Portugal na interface e documentação. Prefere tipos explícitos nos limites do sistema e evita `any` sem justificação. Trata erros com mensagens acionáveis e sem dados pessoais.
- Usa padrões nativos, áreas seguras, contraste, texto escalável, leitores de ecrã e zonas de toque adequadas. Confirma Android e iOS e usa recursos visuais oficiais apenas após autorização.
- Prioriza o funcionamento offline das tarefas de treino, a cache por conta, a sincronização idempotente e o carregamento progressivo. Reduz animações, renderizações, pedidos de rede e ficheiros pesados. Mede o desempenho em dispositivos de referência, incluindo Android de baixo desempenho. Considera cerca de dois segundos para a abertura e 60 FPS como metas, preservando a segurança e a estabilidade.

## Dados e segurança

Usa dados fictícios e projetos de teste autorizados. Nunca ligues a sistemas reais sem autorização nem incluas dados pessoais reais, segredos, tokens, chaves privadas, certificados ou contas de serviço no Git ou no bundle. Usa `EXPO_PUBLIC_*` apenas para configuração pública do cliente. Aplica menor privilégio, regras Firestore e Storage que isolem contas e testes de acessos negados. Mantém a cache local isolada por utilizador. Antes de tratar dados reais, confirma os requisitos com o ginásio e segue o [guia de segurança](docs/security.md).

## Validação

Corre `npm ci`, `npm run lint`, `npm run typecheck`, `npm test --if-present` e `npx expo-doctor`. Se o SDK assinalar versões incompatíveis, revê o diagnóstico e usa `npx expo install --fix` quando adequado. Confirma os imports, a navegação e os recursos referenciados. Valida Android e iOS de acordo com a alteração e declara o que ficou por testar em dispositivos reais. Revê `git diff` e `git status`. Preserva o histórico e os conteúdos relevantes, e deixa o push para aprovação explícita.
