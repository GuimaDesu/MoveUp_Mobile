# Desenvolvimento

## Ambiente

Usa Node.js 22 LTS a partir da versão 22.13, npm e Git. Depois de clonar o repositório, corre `npm ci` na raiz. O ecrã atual pode ser executado sem ficheiro `.env`. O ficheiro `.env.example` indica as futuras variáveis públicas do cliente Firebase.

| Comando | Utilização |
| --- | --- |
| `npm start` | Iniciar o Metro em rede local. |
| `npm start -- --go --lan` | Selecionar explicitamente o Expo Go em rede local. |
| `npm start -- --go --tunnel` | Testar via túnel se a rede local impedir a ligação. O CLI pode pedir a instalação do adaptador ngrok. |
| `npm run android` | Abrir num emulador Android configurado pelo Android Studio. |
| `npm run ios` | Abrir no simulador iOS em macOS com Xcode. |
| `npm run web` | Pré-visualização de desenvolvimento no navegador. |
| `npm run typecheck` | Validar TypeScript em modo estrito. |
| `npm run lint` | Executar ESLint através do Expo CLI. |
| `npx expo-doctor` | Diagnosticar a configuração e as dependências. |

Num dispositivo real, instala um Expo Go compatível com o SDK 58 e usa o QR apresentado pelo Metro. Em rede local, confirma que os dois dispositivos estão na mesma rede e que a firewall permite a ligação. Para testar uma alteração que dependa de módulos nativos ausentes do Expo Go, usa uma compilação de desenvolvimento. Consulta a [referência do SDK 58](https://docs.expo.dev/versions/v58.0.0/) e o [guia do Expo CLI](https://docs.expo.dev/more/expo-cli/).

## Compilação Android e iOS prevista

1. Validar com a equipa o projeto e a conta Expo, os identificadores de Android e iOS e a titularidade das assinaturas. Integrar os ícones e demais recursos oficiais após autorização.
2. Autenticar com `npx eas-cli@latest login` e configurar o projeto com `npx eas-cli@latest build:configure`. Definir perfis de distribuição interna e produção em `eas.json`.
3. Compilar para testes internos com `npx eas-cli@latest build --platform android --profile preview` e `npx eas-cli@latest build --platform ios --profile preview` após configurar os perfis. A instalação em iOS requer o provisionamento adequado.
4. Validar em dispositivos reais. Após aprovação e configuração das contas das lojas, criar as compilações de produção e tratar a submissão numa entrega própria.

Os projetos `android/` e `ios/` são gerados pelo Expo a partir da configuração e dos plugins. O suporte web permanece disponível para verificações rápidas de desenvolvimento. Os alvos de distribuição são Android e iOS. Consulta o [guia de EAS Build](https://docs.expo.dev/build/setup/).
