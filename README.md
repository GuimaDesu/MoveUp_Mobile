# MoveUp Connect · Aplicação móvel

![Expo SDK](https://img.shields.io/badge/Expo-SDK%2058-000020)
![Plataformas](https://img.shields.io/badge/Plataformas-Android%20%2F%20iOS-475569)

O MoveUp Connect é um projeto da Prova de Aptidão Profissional (PAP) do Curso Profissional de Técnico de Programação Informática, no ano letivo 2026/2027, em colaboração com o ginásio MoveUp Fitness Action, em Pombal, Portugal. O projeto inclui um website institucional em React, uma aplicação móvel e uma área de administração e gestão. Este repositório contém a aplicação móvel.

O responsável do ginásio identificou que os clientes passam demasiado tempo ao telemóvel enquanto ocupam as máquinas. A aplicação pretende reduzir esse tempo, tornando mais rápida a consulta de planos e exercícios, o registo de resultados e o acompanhamento da evolução.

## Estado atual

A versão de desenvolvimento **0.1.0** apresenta um ecrã provisório com a identificação MoveUp Connect. Utiliza React Native, Expo SDK 58, TypeScript em modo estrito, Expo Router e Hermes no ambiente nativo. O Git e o GitHub suportam o controlo de versões e a colaboração. As funcionalidades de treino, a ligação ao Firebase e as compilações de distribuição estão previstas para fases posteriores.

## Instalação e execução

É necessário ter Git, Node.js 22 LTS (22.13 ou superior nessa linha), npm e, para testar num telemóvel, uma versão do Expo Go compatível com o SDK 58.

```bash
git clone https://github.com/GuimaDesu/MoveUp_Mobile.git
cd MoveUp_Mobile
npm ci
npm start
```

Liga o telemóvel e o computador à mesma rede local e lê o código QR com o Expo Go no Android ou com a Câmara no iOS. Se a rede local impedir a ligação, usa `npm start -- --tunnel` com acesso à Internet. O [guia de desenvolvimento](docs/development.md) inclui emuladores, simuladores e o processo previsto de compilação.

As compilações independentes de Android e iOS serão feitas com EAS Build após aprovação dos identificadores, da conta e da assinatura. A versão final será instalável sem Expo Go.

## Arquitetura e próximos marcos

- `src/app/` contém as rotas e o layout do Expo Router. Os módulos de negócio serão adicionados à medida que as funcionalidades forem desenvolvidas.
- `docs/` descreve a [arquitetura](docs/architecture.md), o [desenvolvimento](docs/development.md), os [testes](docs/testing.md), a [segurança](docs/security.md) e o [roadmap](docs/roadmap.md).
- `.github/` contém a validação automática e os modelos de colaboração.

A primeira entrega funcional prevê autenticação, recuperação de palavra-passe, perfil e painel personalizado, seguidos dos planos atribuídos, biblioteca de exercícios e demonstrações. O registo de séries, repetições e cargas, temporizador, histórico e evolução completam o fluxo de treino. O roadmap inclui consulta e registo offline com SQLite, sincronização automática, informação sobre serviços do ginásio e notificações com Expo Notifications. A integração remota prevê Firebase Authentication, Cloud Firestore e Firebase Storage.

## Segurança e contribuição

O desenvolvimento usa dados fictícios. A integração com sistemas reais depende de autorização e de regras de acesso que isolem os dados de cada cliente. O [guia de segurança](docs/security.md) descreve os controlos previstos, incluindo proteção de dados pessoais. Consulta o [guia de contribuição](CONTRIBUTING.md) antes de abrir um pull request e a [política de segurança](SECURITY.md) para comunicar vulnerabilidades.

## Créditos

Projeto desenvolvido no âmbito da PAP do Curso Profissional de Técnico de Programação Informática, em colaboração com o MoveUp Fitness Action, em Pombal, Portugal.
