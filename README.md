# Rise Flow — GitHub/Vercel

## Arquivos do repositório

- `index.html` — aplicação completa, incluindo configuração do Firebase.
- `firestore.rules` — cópia das regras usadas no Firestore. A Vercel não publica esse arquivo no Firebase; as regras precisam estar publicadas no Firebase Console.
- `README.md` — instruções.

## Deploy na Vercel

Suba estes arquivos na raiz do repositório GitHub.

A estrutura deve ficar assim:

```text
/
├── index.html
├── firestore.rules
└── README.md
```

Depois importe o repositório na Vercel como site estático.

Não precisa de `firebase-config.js`, `package.json`, React, npm ou build command.

## Firebase

O `index.html` já aponta para o projeto:

`rise-painel`

O sistema usa:
- Firebase Authentication
- Cloud Firestore
- namespace `riseFlow/main/...`

## Antes de testar

No Firebase Console:

1. Authentication > Sign-in method > Email/Password deve estar ativo.
2. O usuário deve existir em Authentication > Users.
3. As regras de `firestore.rules` devem estar publicadas em Firestore > Rules.
4. O domínio da Vercel deve estar em Authentication > Settings > Authorized domains.

## Importante

Não suba versões antigas de:
- `firebase-config.js`
- `rise-flow-firebase-v6`
- `rise-flow-firebase-v7`
- `rise-flow-firebase-v8`

Esta pasta é a versão limpa para o deploy.
