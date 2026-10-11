# Urna Digital

Simulador moderno e bonito de urna eletrônica digital.

## Recursos

- Interface moderna com design escuro e animações
- Urna interativa com teclado numérico (13 = Lula, 22 = Flávio Bolsonaro)
- Contagem de votos em tempo real
- Suporte a teclado do computador
- Pronto para conectar ao **Firebase Firestore**

## Como ativar votos reais (Firebase)

1. Crie um projeto gratuito no [Firebase Console](https://console.firebase.google.com)
2. Ative o **Firestore Database** (modo de teste está ok para começar)
3. Vá em Project Settings → Your apps → Web app e copie o config JSON
4. No site, clique no botão **⚙️ Config DB** (canto inferior direito)
5. Cole o JSON e clique em **Salvar e Conectar**
6. Recarregue a página

Os votos serão salvos no documento `votes/totals` com os campos `lula` e `flavio`.

### Regras de segurança sugeridas (Firestore)

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /votes/{document} {
      allow read: if true;
      allow write: if true;  // Em produção, restrinja melhor
    }
  }
}
```

## GitHub Pages

O site está hospedado em:

**https://alexandreprass.github.io/urna-digital/**

## Desenvolvimento local

Basta abrir o `index.html` no navegador. Sem Firebase configurado, ele roda em modo demo local (localStorage).

## Licença

Código livre para uso e modificação.
