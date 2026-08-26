# Rise Flow — Deploy

Esta versão já tem o firebaseConfig embutido diretamente no index.html.

## Antes do deploy
- Authentication > Email/Password: ativado
- Usuários internos: criados
- Firestore Rules: publicadas

## Teste
1. Abra via http/https (Vercel ou servidor local).
2. Faça login.
3. Crie uma demanda.
4. Verifique em Firestore > Data se surgiu `tasks`.
5. Atualize a página para confirmar persistência.
