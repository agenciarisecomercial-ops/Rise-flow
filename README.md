# Rise Flow — correção Firebase

## O que foi corrigido
- Firebase inicializa com SDK compat estável.
- Configuração está dentro do próprio index.html.
- Rise Flow usa namespace próprio no Firestore:
  - riseFlow/main/tasks
  - riseFlow/main/members
- Login por Firebase Authentication.
- Sincronização em tempo real.
- Mudanças de status/Kanban salvam no Firestore.
- Regras de compatibilidade não bloqueiam os outros apps já existentes.

## IMPORTANTE SOBRE AS RULES
O arquivo `firestore.rules` restaura o comportamento público dos apps antigos e protege somente `riseFlow`.

Isso é uma solução de compatibilidade. Depois, o ideal é proteger também as coleções dos outros apps com autenticação/regras próprias.

## Teste
1. Publique as regras do arquivo `firestore.rules`.
2. Suba `index.html` na Vercel/GitHub.
3. Se usar Vercel, adicione o domínio em Firebase Authentication > Settings > Authorized domains.
4. Abra o Rise Flow.
5. Deve aparecer `Login necessário`, não `Conectando...` infinito.
6. Faça login.
7. Deve aparecer `Firebase conectado`.
8. Crie uma demanda e confira:
   Firestore > Data > riseFlow > main > tasks
