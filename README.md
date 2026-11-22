================================================================================
IPTV STUDIO PRO - LEGGIMI (README)
================================================================================

Applicazione desktop in Python (tkinter) per caricare, validare, organizzare e
riprodurre playlist IPTV .m3u / .m3u8, associare guide EPG XMLTV, registrare
flussi video (immediati, a tempo o programmati con timer) e compilare un
eseguibile autonomo con PyInstaller.

--------------------------------------------------------------------------------
1. FUNZIONALITA PRINCIPALI
--------------------------------------------------------------------------------
- Gestione playlist M3U:
  Caricamento da URL remoto (inclusa lista predefinita Seca), file locale
  .m3u/.m3u8 o testo incollato, con gestione di User-Agent, Referer, preferiti
  (*), spostamento righe, ripristino ordine originale (Ordine Orig.) e
  rimozione duplicati.

- Verifica flussi e risoluzione:
  Controllo concorrente dello stato ONLINE / OFFLINE, latenza e manifest HLS,
  con rilevamento risoluzione tramite ffprobe limitato a 3 thread simultanei per
  evitare saturazioni e pulsante "Retry Offline" per ritestare solo i canali
  non raggiungibili.

- Guida EPG XMLTV e Timer:
  Caricamento di file .xml / .xml.gz o URL multipli, abbinamento automatico e
  manuale (tvg-id), anteprima del programma in onda e del successivo,
  programmazione timer con anticipo/margine e salvataggio automatico dei timer
  futuri in iptv_studio_config.json.

- Player integrato e player esterno:
  Riproduzione diretta nel pannello laterale tramite ffplay (con aggancio
  finestra Win32 e ridimensionamento) oppure avvio su player esterno (VLC o
  ffplay).

- Registrazione video:
  Salvataggio flussi in .ts o .mp4 tramite ffmpeg (con fallback HLS se ffmpeg
  non e presente), cartella predefinita configurabile e apertura rapida
  ("Apri").

- Esportazione mirata:
  Salvataggio di playlist .m3u con preferiti in cima nelle modalita "M3U
  Pulita" (ONLINE), "Con EPG" e "Vista" corrente.

--------------------------------------------------------------------------------
2. PREREQUISITI E STRUMENTI CONSIGLIATI
--------------------------------------------------------------------------------
- Python 3.x (con tkinter incluso) per eseguire o compilare lo script.
- PyInstaller per creare l'eseguibile .exe autonomo.
- FFmpeg (ffmpeg.exe, ffprobe.exe, ffplay.exe): opzionale ma consigliato per
  rilevamento risoluzione, player integrato e registrazione stabile dei flussi.
- VLC Media Player: opzionale per la riproduzione esterna.

--------------------------------------------------------------------------------
3. COMPILAZIONE CON PYINSTALLER
--------------------------------------------------------------------------------
Apri il terminale nella cartella contenente iptv_checker.py ed esegui:

    pyinstaller --onefile --windowed --name IPTV_Studio_Pro iptv_checker.py

- L'eseguibile verra creato in dist\IPTV_Studio_Pro.exe.
- Al primo avvio, nella stessa cartella dell'eseguibile verra generato
  iptv_studio_config.json per salvare tema, sorgenti, preferenze
  player/registrazione e timer in attesa.

--------------------------------------------------------------------------------
4. USO RAPIDO
--------------------------------------------------------------------------------
1. Carica una playlist: inserisci un URL o un file M3U nella barra in alto
   oppure clicca "Lista Seca" / "Incolla Lista".
2. Carica l'EPG (opzionale): indica uno o piu file/URL XMLTV e clicca
   "Carica EPG" (o "Auto-EPG" per forzare l'abbinamento).
3. Controlla i canali: imposta Timeout, Thread e opzioni HLS/Risoluzione,
   quindi clicca "Avvia Controllo Flussi".
4. Guarda o registra: seleziona un canale e usa "Player" (o doppio clic),
   "Esterno", "Registra" oppure "Reg. da EPG...".
5. Esporta la lista: usa "Esporta M3U Pulita", "Esporta Con EPG" o
   "Esporta Vista" per salvare il nuovo file .m3u.

--------------------------------------------------------------------------------
5. NOTE PRATICHE
--------------------------------------------------------------------------------
- Alcuni flussi IPTV richiedono header specifici (User-Agent / Referer) o
  restrizioni geografiche/di rete: un canale segnato OFFLINE in un controllo
  veloce puo risultare riproducibile con "Retry Offline" o su player esterno.
- Per il player integrato, assicurati che ffplay.exe sia presente nel PATH,
  nella cartella del programma oppure accanto al player configurato.
