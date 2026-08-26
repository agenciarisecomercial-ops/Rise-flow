# Rise Flow — Protótipo

Protótipo em HTML/CSS/JS puro para gerenciamento interno da Rise.

## Como testar
Abra `index.html` diretamente no navegador.

## Como subir na Vercel
1. Crie um repositório no GitHub.
2. Envie o `index.html`.
3. Importe o repositório na Vercel.
4. Deploy.

## O que já funciona
- Dashboard
- Demandas
- Filtros separados por responsável, origem e cliente
- Clientes
- Produção em Kanban
- Mover demandas entre etapas pelo Kanban
- Equipe
- Adicionar/remover membros da equipe
- Central de urgência do Andrey
- Ordenação automática por urgência e prazo
- Indicadores de atrasadas / hoje / abertas
- Nova demanda
- Recorrência
- Concluir/excluir demandas
- Persistência com localStorage

## Importante
Esta V1 usa `localStorage`, então os dados ficam apenas no navegador.
Para uso real multiusuário, a próxima etapa deve conectar Supabase para:
- login
- banco de dados compartilhado
- permissões
- histórico
- sincronização em tempo real

## Firebase

O projeto agora está preparado para usar Firebase Authentication + Cloud Firestore.

Enquanto `RISE_FIREBASE_ENABLED = false`, ele continua usando localStorage.

Veja `FIREBASE_SETUP.md` para configurar.

Arquivos:
- `firebase-config.js`
- `firestore.rules`
- `FIREBASE_SETUP.md`
