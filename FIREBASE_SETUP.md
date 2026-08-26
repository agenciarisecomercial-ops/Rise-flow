# Configurar Firebase no Rise Flow

## 1. Criar o projeto
No Firebase Console, crie um projeto para a Rise.

## 2. Criar um app Web
Em Configurações do projeto > Seus apps > Web, registre um app.

Copie o objeto `firebaseConfig` e cole os valores em:

`firebase-config.js`

Depois altere:

```js
window.RISE_FIREBASE_ENABLED = true;
```

## 3. Ativar Authentication
Firebase Console > Authentication > Sign-in method.

Ative:

- Email/Password

Depois crie manualmente os usuários internos da Rise em:

Authentication > Users

Exemplos:
- Gabriel
- Andrey
- Lara

Não existe cadastro público no Rise Flow.

## 4. Criar o Firestore
Firebase Console > Firestore Database > Create database.

Use as regras contidas no arquivo:

`firestore.rules`

As regras exigem usuário autenticado.

## 5. Publicar as regras
Cole o conteúdo de `firestore.rules` na aba Rules do Firestore e publique.

## 6. Deploy
Depois você pode subir os arquivos no GitHub e importar o repositório na Vercel.

Arquivos principais:
- index.html
- firebase-config.js
- firestore.rules

## Como os dados funcionam

Quando o Firebase estiver desligado:
- o Rise Flow continua funcionando com localStorage.

Quando o Firebase estiver configurado e o usuário fizer login:
- tarefas são carregadas do Firestore;
- membros são carregados do Firestore;
- alterações são sincronizadas;
- mudança de etapa no Kanban é sincronizada;
- tarefas excluídas são removidas do Firestore;
- membros removidos são removidos do Firestore.

## Segurança

A chave `apiKey` do Firebase Web não funciona como uma senha secreta.

A proteção dos dados depende principalmente de:
- Firebase Authentication;
- regras do Firestore;
- não usar regras públicas como `allow read, write: if true`.

Nunca coloque uma Service Account ou chave privada do Firebase Admin neste projeto front-end.

## Status atual

O projeto já está com o `firebaseConfig` do projeto `rise-painel` preenchido
e `RISE_FIREBASE_ENABLED = true`.

Ainda é necessário:
- ativar Authentication > Email/Password;
- criar os usuários internos;
- publicar as regras de `firestore.rules`.
