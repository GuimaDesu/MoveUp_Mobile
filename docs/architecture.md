# Arquitetura

## Base implementada

O Expo Router inicia em `src/app/_layout.tsx`, que configura a navegação em pilha. A rota `/` apresenta o ecrã provisório definido em `src/app/index.tsx`. A aplicação funciona sem configuração de serviços e sem dados de clientes.

## Organização prevista

| Localização | Responsabilidade |
| --- | --- |
| `src/app/` | Rotas, layouts e composição dos ecrãs. |
| `src/features/` | Autenticação, painel, treinos, exercícios, evolução, perfil e notificações. Cada módulo reúne a sua lógica, componentes e tipos específicos. |
| `src/components/` | Componentes de interface e layout partilhados entre funcionalidades. |
| `src/services/` | Adaptadores Firebase, armazenamento de ficheiros e sincronização. |
| `src/database/` | Esquema SQLite, migrações e acesso aos dados locais. |
| `src/config/`, `src/theme/` | Configuração validada e tokens visuais quando houver reutilização. |
| `assets/`, `tests/` | Recursos visuais autorizados e cenários automatizados à medida que forem necessários. |

As rotas delegam nas funcionalidades. A lógica de treino trabalha com os seus modelos e acede aos dados através dos adaptadores que a funcionalidade efetivamente precisar. Os módulos partilhados, contextos, hooks e utilitários surgem quando existir reutilização concreta. Os dados fictícios ficam em fixtures separadas da lógica, reutilizáveis em desenvolvimento e testes.

## Dados e sincronização previstos

O Firebase Authentication identifica o cliente, o Firestore disponibiliza planos e registos autorizados e o Firebase Storage aloja as demonstrações. O SQLite disponibiliza os planos já descarregados e guarda cada registo de treino e a respetiva operação pendente na mesma transação.

Após recuperar a ligação e confirmar a sessão, a sincronização tenta enviar operações pendentes com identificadores estáveis. A operação só fica concluída após confirmação do servidor. Repetições devem produzir o mesmo estado remoto. Conflitos devem seguir regras explícitas por tipo de dado, mantendo registos pendentes até à resolução. A cache e a fila ficam isoladas por conta. A troca de conta deve impedir o acesso aos dados da sessão anterior.

As integrações, o esquema e os contratos devem ser introduzidos com os primeiros fluxos que os utilizem. As fases e os critérios de conclusão estão no [roadmap](roadmap.md).
