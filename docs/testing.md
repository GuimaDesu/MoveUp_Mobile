# Testes e desempenho

## Validação da base

Executar `npm ci`, `npm run typecheck`, `npm run lint`, `npm test --if-present` e `npx expo-doctor`. A integração contínua corre a instalação, a análise estática e os testes quando houver um script. A base atual ainda não inclui uma suíte automatizada.

Para o teste de abertura, iniciar o Metro, abrir a rota inicial no Expo Go compatível com o SDK 58 e verificar o título, a mensagem, as áreas seguras e a ausência de erros no Metro e no ecrã. Repetir em Android e iOS com ecrãs pequenos, texto ampliado e leitor de ecrã. Registar modelo, versão do sistema, tipo de compilação e resultado.

## Cobertura prevista

| Área | Cenários |
| --- | --- |
| Funcional | Autenticação e recuperação, autorização do plano, registo de treino, temporizador, histórico e evolução. |
| Compatibilidade | Plataforma, tamanhos de ecrã, áreas seguras, escalas de texto, TalkBack e VoiceOver. Confirmar os requisitos mínimos do SDK adotado. |
| Offline | Abrir um plano já descarregado em modo de avião, registar séries, fechar e reabrir a aplicação e confirmar persistência. Testar reconexão, erros remotos, duplicados, conflitos e mudança de conta. |
| Segurança | Isolamento no Firestore e Storage, validação de escritas, cache por utilizador e ausência de dados pessoais nos logs. |
| Desempenho | Abertura a frio, mudança de exercício, fluidez, tamanho instalado, memória, bateria e tráfego de rede. |

## Metas de desempenho

Medir em compilações de distribuição e em dispositivos de referência, incluindo Android de baixo desempenho. Procurar uma abertura a frio de cerca de dois segundos até ao primeiro ecrã utilizável, fluidez próxima de 60 FPS, tamanho de instalação reduzido e transições rápidas entre exercícios. Os fluxos essenciais de treino devem funcionar offline. Estas metas dependem de medição e preservam a segurança e a estabilidade.

Privilegiar componentes nativos, listas virtualizadas quando o volume justificar, carregamento progressivo, imagens e vídeos otimizados, poucas animações e cache local. Evitar renderizações, WebViews e pedidos de rede desnecessários. Medir o tamanho e o consumo de memória, bateria e dados antes de definir limites por plataforma.
