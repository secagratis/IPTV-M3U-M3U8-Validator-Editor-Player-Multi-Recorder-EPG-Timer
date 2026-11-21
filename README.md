================================================================================
IPTV M3U / M3U8 Validator, Editor, Player, Multi-Recorder & EPG Timer
================================================================================

1. DESCRIZIONE DEL PROGRAMMA
Utility desktop per Windows dedicata alla gestione, verifica, riproduzione e
registrazione di playlist IPTV (.m3u / .m3u8) con supporto completo alla guida
programmi elettronica EPG in formato XMLTV (.xml / .xml.gz).

--------------------------------------------------------------------------------
2. FUNZIONALITA' PRINCIPALI
--------------------------------------------------------------------------------
- Caricamento Playlist:
  * Apertura di file locali .m3u e .m3u8 ("Apri .m3u / .m3u8...").
  * Incolla diretto di testo M3U o elenco di URL ("Incolla Lista / URL").
  * Rilevamento automatico di paese, group-title, tvg-id, User-Agent e Referer.

- Controllo Flussi Multi-Thread:
  * Verifica simultanea dei canali (thread e timeout configurabili).
  * Controllo approfondito del manifest HLS (#EXTM3U / segmenti) per scartare
    flussi vuoti, scaduti o pagine HTML.
  * Filtro rapido per Paese e per Stato (Tutti / Solo Online / Solo Offline).

- Guida EPG (XMLTV) & Editor Canali:
  * Caricamento guida EPG da URL o file locale (.xml / .xml.gz).
  * Rilevamento automatico dell'URL EPG dall'intestazione #EXTM3U (url-tvg).
  * Visualizzazione del programma attualmente in onda nella colonna "EPG".
  * Pulsante "Modifica / EPG" (o tasto destro -> "Modifica Canale / Associa EPG..."):
    permette di rinominare il canale, cambiare paese, modificare URL/User-Agent/
    Referer e cercare/abbinare manualmente il tvg-id dalla lista canali XMLTV.

- Riproduzione Diretta:
  * Doppio clic su un canale (o pulsante "Riproduci") per avviarlo su VLC o
    ffplay, passando automaticamente User-Agent e Referer del singolo canale.

- Registrazione Video & Timer Programmato da EPG:
  * Registrazione Immediata / a Tempo: imposta i minuti nella casella
    "Min (0=infinito)" e premi "Registra Video" per salvare in .ts o .mp4.
  * Registrazione / Timer da EPG ("Registra da EPG..."):
    - Selezionando un programma IN ONDA ORA, la registrazione parte subito e si
      ferma automaticamente alla fine dell'evento (piu' eventuale margine extra).
    - Selezionando un programma FUTURO, viene impostato un Timer in attesa che
      avviera' e fermera' la registrazione in automatico all'orario previsto.
  * Multi-Registrazione & Gestione Timer ("Timer / Reg. (N)"):
    - Consente di registrare o programmare piu' canali contemporaneamente.
    - Cliccando sul pulsante "Timer / Reg. (N)" si apre la finestra di gestione
      per controllare stato, durata, dimensione file e fermare/annullare un
      singolo timer o tutti insieme.

- Esportazione Playlist Pulita:
  * "Esporta M3U Pulita": salva un nuovo file .m3u contenente solo i canali
    ONLINE (rispettando l'eventuale filtro Paese) con i nomi e i tvg-id EPG
    aggiornati.
  * "Esporta Vista (.m3u)": esporta tutti i canali attualmente visibili.

--------------------------------------------------------------------------------
3. REQUISITI PER PLAYER E REGISTRAZIONE
--------------------------------------------------------------------------------
- Riproduzione: richiede VLC Media Player oppure ffplay.exe installati sul PC
  (rilevati automaticamente o selezionabili tramite "Sfoglia...").
- Registrazione Video:
  * Consigliato: posizionare "ffmpeg.exe" nella stessa cartella del programma
    (oppure nella cartella di VLC / nel PATH di Windows) per registrare qualsiasi
    formato (.ts e .mp4) con riconnessione automatica.
  * Senza ffmpeg: il programma utilizza un motore interno Python di fallback
    compatibile con i flussi HLS (.m3u8).

--------------------------------------------------------------------------------
4. COMPILAZIONE ESEGUIBILE (.EXE)
--------------------------------------------------------------------------------
Per ricreare il file eseguibile standalone dopo una modifica al sorgente
"iptv_checker_validator.py", avviare con doppio clic il file batch:
  compila_IPTV_Checker_Validator.bat
L'eseguibile verra' generato nella sottocartella:
  dist\IPTV_Checker_Validator.exe
================================================================================
