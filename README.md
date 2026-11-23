# Pilota Ordini

Tabella condivisa per seguire lo stato degli ordini: una riga per ordine, 8 stati cliccabili, prima riga e prima colonna fisse.
Più persone possono modificarla in contemporanea; le modifiche si salvano da sole e compaiono subito a tutti.

Pagina statica (GitHub Pages) + database Firebase Realtime Database (piano gratuito).

## Collegare il database (una volta sola, circa 5 minuti)
1. Vai su https://console.firebase.google.com e crea un progetto (nome a piacere, Analytics non serve).
2. Nel menu **Build > Realtime Database** clicca **Crea database**, scegli la regione Europa e avvia in **modalità di test**.
3. Apri la scheda **Regole**, incolla il contenuto di `database.rules.json` (copre sia `orders` sia `config`, dove stanno gli stati) e pubblica.
4. In **Impostazioni progetto (ingranaggio) > Generali > Le tue app** aggiungi un'app **Web** (icona `</>`), senza hosting.
5. Copia i valori di `firebaseConfig` (apiKey, authDomain, databaseURL, projectId, appId) nel file `config.js`.
6. Salva e fai commit: la pagina si collega da sola.

## Pubblicare
Repository > Settings > Pages > Source: branch `main`, cartella `/ (root)`. Il link sarà quello mostrato in quella pagina.

## Sicurezza
Chiunque abbia il link può leggere e modificare gli ordini (nessuna password): va bene per un pilota tra poche persone.
Non condividere il link in pubblico. Per proteggere meglio i dati servirà aggiungere un accesso.
