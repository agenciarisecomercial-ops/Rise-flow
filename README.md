# Rise Flow — Stable Fix

Correção:
- restaurada a função `renderClientStatusFilters()` que havia sido removida acidentalmente;
- Firebase voltou exatamente para a arquitetura da última versão estável;
- nenhuma alteração nas Rules;
- nenhuma alteração no namespace do Firestore;
- mantém observações e edição de demandas;
- mantém clientes, status, filtros e Kanban.

Causa do bug:
`render()` chamava `renderClientStatusFilters()`, mas essa função não existia mais.
Isso gerava ReferenceError antes de `initFirebase()` ser chamado.
