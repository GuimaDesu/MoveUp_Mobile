# Roadmap

| Fase | Prioridade e dependências | Critérios de conclusão |
| --- | --- | --- |
| 0 · Base do projeto | Inicial. Expo SDK 58, npm e Git. | Ecrã provisório, validações reproduzíveis, documentação e revisão por pull request. |
| 1 · Conta e planos | Alta. Projeto Firebase de teste, regras de acesso e modelo de planos acordado com a gestão. | O cliente inicia sessão, recupera a palavra-passe e consulta o perfil, o painel e os planos atribuídos. Os testes confirmam o isolamento entre contas. |
| 2 · Execução do treino | Alta. Planos disponíveis, catálogo fictício e SQLite. Os media reais dependem de autorização. | Biblioteca e demonstrações de exercícios, navegação rápida, temporizador e registo de séries, repetições e cargas. O plano em cache e o registo funcionam offline, incluindo após reabrir a aplicação. |
| 3 · Sincronização e evolução | Alta. Registos locais, regras de Firestore testadas e política de conflitos. | Na reconexão os registos são sincronizados automaticamente, sem duplicação após repetição. O histórico e os indicadores de evolução refletem os registos válidos. |
| 4 · Serviços e distribuição | Média. Conteúdos e identidade aprovados, compilação nativa e permissões de notificação. | Informação sobre o ginásio e notificações configuráveis. Compilações Android e iOS validadas em dispositivos reais antes de qualquer submissão. |

As fases 1 a 4 descrevem trabalho previsto. O desenho dos fluxos deve ser validado com o ginásio, medindo a rapidez com que os clientes concluem as tarefas durante um treino.
