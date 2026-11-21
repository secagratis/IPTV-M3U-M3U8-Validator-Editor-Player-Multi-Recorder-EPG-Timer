╔══════════════════════════════════════════════════════════════════════════════╗
║                                                                              ║
║      📺  IPTV M3U / M3U8 VALIDATOR, EDITOR, PLAYER & EPG TIMER RECORDER      ║
║                                                                              ║
║          Gestione, Verifica, Guida EPG e Registrazione Multi-Canale          ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝


  📌 PANORAMICA
  ────────────────────────────────────────────────────────────────────────────
  Utility desktop per Windows progettata per analizzare, ripulire, modificare,
  riprodurre e registrare playlist IPTV (.m3u / .m3u8) con integrazione
  completa della guida programmi elettronica EPG in formato XMLTV.


  ✨ FUNZIONALITÀ PRINCIPALI
  ────────────────────────────────────────────────────────────────────────────

  1. 📂 CARICAMENTO & ANALISI PLAYLIST
     • Apertura diretta di file locali .m3u e .m3u8 ("Apri .m3u / .m3u8...").
     • Inserimento rapido tramite appunti ("Incolla Lista / URL").
     • Rilevamento automatico di Paese, Categoria (group-title), ID EPG
       (tvg-id), User-Agent e Referer per ogni singolo flusso.

  2. ⚡ VERIFICA VELOCE MULTI-THREAD
     • Controllo simultaneo dei flussi con numero di thread e timeout
       personalizzabili.
     • Analisi approfondita del manifest HLS (#EXTM3U e segmenti) per
       scartare link scaduti, flussi vuoti o pagine HTML di errore.
     • Filtri istantanei per Paese e Stato (Tutti / Solo Online / Solo Offline).

  3. 🗓️ GUIDA EPG (XMLTV) & EDITOR CANALI
     • Caricamento guida EPG da URL remoto o da file locale (.xml / .xml.gz).
     • Rilevamento automatico dell'indirizzo EPG nell'intestazione #EXTM3U.
     • Visualizzazione in tempo reale del programma "In Onda Ora" in tabella.
     • Finestra "Modifica / EPG" (anche con tasto destro sul canale):
       - Modifica Nome Canale, Paese, URL Flusso, User-Agent e Referer.
       - Ricerca istantanea nella guida XMLTV e abbinamento manuale del tvg-id.

  4. ▶️ RIPRODUZIONE DIRETTA SU PLAYER
     • Doppio clic su qualsiasi canale (o pulsante "Riproduci") per avviarlo
       su VLC o ffplay con invio automatico di User-Agent e Referer.

  5. 🔴 REGISTRAZIONE VIDEO & TIMER PROGRAMMATO DA EPG
     • Registrazione Immediata / a Tempo:
       Imposta i minuti in "Min (0=∞)" e premi "Registra Video" (.ts / .mp4).
     • Registrazione & Timer da Guida EPG ("Registra da EPG..."):
       - Evento IN ONDA ORA ➔ avvio immediato e stop automatico a fine
         programma (con margine extra configurabile).
       - Evento FUTURO      ➔ imposta un Timer in attesa che avvia e ferma
         la registrazione in automatico all'orario previsto.
     • Multi-Registrazione & Gestione Timer ("Timer / Reg. (N)"):
       Permette di registrare o programmare più canali contemporaneamente,
       monitorando avanzamento, dimensione file e stato dei timer.

  6. 💾 ESPORTAZIONE PLAYLIST PULITA
     • "Esporta M3U Pulita": crea un nuovo file .m3u con i soli canali ONLINE
       (rispettando il filtro Paese) e i tag tvg-id aggiornati.
     • "Esporta Vista (.m3u)": salva tutti i canali attualmente filtrati.


  ⚙️ REQUISITI CONSIGLIATI
  ────────────────────────────────────────────────────────────────────────────
  • Player Video : VLC Media Player oppure ffplay.exe installati sul PC
                   (rilevati in automatico o selezionabili via "Sfoglia...").
  • Registrazione: Per la massima compatibilità (.ts e .mp4 con riconnessione
                   automatica), copia "ffmpeg.exe" nella stessa cartella del
                   programma (oppure nella cartella di VLC / PATH di Windows).
                   In assenza di ffmpeg entra in funzione il motore interno
                   Python per flussi HLS (.m3u8).


  🛠️ COMPILAZIONE ESEGUIBILE (.EXE)
  ────────────────────────────────────────────────────────────────────────────
  Per rigenerare l'eseguibile standalone dopo eventuali modifiche al codice
  sorgente "iptv_checker_validator.py":

     1. Avvia con doppio clic ➔ compila_IPTV_Checker_Validator.bat
     2. Troverai il file aggiornato in ➔ dist\IPTV_Checker_Validator.exe


══════════════════════════════════════════════════════════════════════════════
