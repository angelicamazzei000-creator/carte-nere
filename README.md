# Carte Nere Online con Firebase

Questa versione usa Firebase Realtime Database e accesso anonimo, quindi le stanze funzionano tra telefoni diversi.

## Configurazione

1. Crea un progetto su Firebase.
2. Attiva **Authentication → Sign-in method → Anonymous**.
3. Crea **Realtime Database** in modalità bloccata, scegliendo una regione europea.
4. In **Realtime Database → Rules**, incolla:

```json
{
  "rules": {
    "rooms": {
      "$room": {
        ".read": "auth != null",
        ".write": "auth != null"
      }
    }
  }
}
```

5. In **Impostazioni progetto → Le tue app**, crea una app Web.
6. Copia la configurazione Firebase dentro `firebase-config.js`.
7. Carica tutti i file nella root del repository GitHub e attendi GitHub Pages.

## Nota

Le regole sopra sono semplici e adatte a una partita privata tra amici. Non usare questa configurazione per un servizio pubblico con dati sensibili.
