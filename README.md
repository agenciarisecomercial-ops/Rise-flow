# Rise Flow — Firebase V8

Mudança principal:
- Removeu completamente a conexão WebSocket/long-polling do Firestore SDK.
- Mantém Firebase Authentication.
- Dados são lidos/escritos diretamente pela API REST oficial do Firestore usando o token do usuário.
- Atualização automática a cada 15 segundos.
- Toda alteração feita no app é enviada imediatamente ao Firestore.
- Botão Testar Firebase faz escrita + leitura real.
- Não altera as Rules.
