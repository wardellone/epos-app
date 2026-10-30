# FAQ — Epos 1

**Come si compra?** Paga 25 € con Revolut su https://revolut.me/wardell
oppure con bonifico ceco (QR Platba, 600 Kč, il QR te lo mando su richiesta),
poi scrivi a
federico.neffa@gmail.com con l'email da usare per il download. Ricevi
l'accesso a una cartella OneDrive privata con l'installer e i suoi
aggiornamenti. Non serve un account GitHub o Microsoft.

**Perché pagare se esiste Handy, gratuito?** Handy è un ottimo progetto.
Epos punta sulla dettatura tarata per l'italiano, sulle correzioni e sul
vocabolario personali e su un uso configurabile da Settings. I 25 € sostengono
lo sviluppo. Non promettiamo superiorità sulle alternative gratuite.

**Serve un microfono speciale?** No: scegli l'input in General e controlla
l'indicatore di livello. Un microfono a 48 kHz viene ricampionato con un filtro
prima della trascrizione. Se il dispositivo salvato manca, Epos usa il
predefinito Windows e ti avvisa. Riprova la cattura dopo una riconnessione.

**Caps Lock e scorciatoie?** Caps Lock è il tasto iniziale: premilo e tienilo
premuto mentre parli. Le maiuscole vengono disattivate solo mentre Epos è
aperto. Il tasto si cambia in General; i cambi indicati RESTART richiedono riavvio.
Ctrl+Alt+L apre il selettore lingua. Settings si apre dalla tray.

**Che cosa succede agli appunti?** Durante l'incolla, la trascrizione occupa
brevemente gli appunti; Epos ripristina poi il contenuto precedente supportato,
anche se l'editor non permette di verificare l'inserimento esatto. Una copia più
recente dell'utente ha sempre la precedenza. Se gli appunti non possono essere
conservati in sicurezza, Epos non li modifica e usa l'inserimento diretto.

**Può incollare nella finestra sbagliata?** Epos memorizza la finestra all'inizio
e la confronta prima della consegna: se è cambiata, non modifica gli appunti,
non inserisce il testo e avvisa. Non vede il cambio di scheda o campo dentro la stessa finestra.
Controlla il destinatario prima di dettare e il testo dopo l'incolla.

**Quali lingue?** Italiano ed inglese sono il riferimento delle verifiche;
le altre lingue selezionabili non hanno garanzie di qualità specifiche.
Il benvenuto segue la lingua italiana/inglese di Windows. Settings è in inglese.

**CPU o NVIDIA?** Auto usa small su CPU e medium con NVIDIA e un runtime CUDA
funzionante. Le prove preliminari non sono requisiti universali: i tempi
dipendono da PC, audio e modello. La validazione su un altro PC è ancora pendente.
Senza le DLL opzionali in `%APPDATA%\EPOS\runtime\cuda12-cudnn9\bin`, Epos
usa la CPU. Il pacchetto non distribuisce le librerie NVIDIA. Per la 1.0 non
c'è installazione guidata di CUDA dalla UI.

**Dove sono i dati?** `%APPDATA%\EPOS\config.json` contiene impostazioni e
vocabolario, `corrections.txt` contiene correzioni, `.tmp` contiene i log.
I modelli sono nella cache locale di Hugging Face. Il testo nei nuovi log
è disattivato di default; Advanced consente diagnostica esplicita. Info
permette di aprire la cartella e cancellare i log, compresi quelli storici.

**Come disinstallo?** Dal menu Start o da Impostazioni Windows. I dati personali
e i modelli vengono conservati per impostazione predefinita, così una
reinstallazione li ritrova. La cache di Hugging Face è condivisa con altre app;
la pulizia dei modelli va effettuata consapevolmente separatamente.

**Aggiornamenti e licenza?** 25 € una volta sola, licenza perpetua per la
versione 1 con tutti i suoi aggiornamenti. Nessuna attivazione o rinnovo. Un
utilizzatore, più PC propri, anche uso professionale; non condividere l'installer
o la cartella di download. La versione 1 continua a funzionare anche dopo una
versione 2, che per chi possiede la 1 costerà la metà. Epos controlla una volta
all'avvio se c'è una versione nuova e ti avvisa; puoi controllare anche dalla
tray o da Info. Il nuovo installer è nella stessa cartella OneDrive; reinstallare
sopra conserva il profilo.

**Rimborsi?** Su richiesta entro 14 giorni dal pagamento: scrivi a
federico.neffa@gmail.com e l'importo ti viene restituito con lo stesso metodo.

**Hash, SmartScreen e Smart App Control?** Confronta `Get-FileHash` con `latest.json`
e la pagina prodotto. L'hash verifica la coincidenza, non il publisher. SmartScreen
può avvisare per scarsa reputazione; se disponibile usa Ulteriori informazioni →
Esegui comunque solo per un download di cui hai verificato la provenienza.
Smart App Control può bloccare del tutto una build non firmata: la sua prova
reale è pendente. Non indichiamo di disattivare le protezioni. Un avviso di
reputazione non equivale a una rilevazione antivirus; una rilevazione Defender
concreta va invece esaminata separatamente.

## English FAQ

**How do I buy?** Pay €25 via Revolut at https://revolut.me/wardell or with
Czech bank transfer (QR Platba, 600 CZK; QR sent on request), then email federico.neffa@gmail.com
with the address to use for the download. You get access to a private OneDrive
folder with the installer and its updates. No GitHub or Microsoft account needed.

**Why pay when Handy is free?** Handy is a good project. Epos focuses on
Italian dictation, personal vocabulary/corrections and accessible Settings;
the €25 supports development. No claim of being more accurate or faster.

**Microphone and shortcuts?** Choose input in General and check its level.
Native 48 kHz capture is filtered and resampled. A missing saved input falls
back to Windows default with a notice. Hold Caps Lock to dictate; it does not
toggle capitals while Epos runs. Change it in Settings (restart required).
Ctrl+Alt+L opens the language picker; the tray opens Settings.

**Clipboard and recipient?** Epos restores supported prior clipboard content
after every sent paste, even when the editor cannot expose the exact insertion.
A newer user copy always wins. If clipboard content cannot be preserved safely,
Epos leaves it unchanged and uses direct text input in the original focused
field. Keep the intended field focused until the text appears, and always check
the recipient and transcript.

**Languages and hardware?** Italian and English are reference languages for
validation; other selectable languages have no specific quality guarantee.
Settings is English. Auto uses small on CPU, medium on NVIDIA with a working
CUDA runtime. Latency varies and a second-PC test is pending. Optional NVIDIA
DLLs go in `%APPDATA%\EPOS\runtime\cuda12-cudnn9\bin`; they are not shipped.

**Data and uninstall?** Settings/vocabulary are in `%APPDATA%\EPOS\config.json`,
corrections in `corrections.txt`, logs in `.tmp`, models in the Hugging Face cache.
New logs exclude text unless explicitly enabled. Info clears current/legacy logs.
Uninstall keeps data and models by default; shared model caches require separate
careful cleanup. Installing an update over Epos retains the profile.

**Updates, licence and refunds?** €25 once; perpetual licence for version 1
with all its updates. One user, multiple own PCs, professional use allowed. No
activation or renewal. Version 1 keeps working after a version 2, which version
1 owners get at 50% off. Epos checks for a newer version once at startup and
on request; the new installer is in the same OneDrive folder. Refund on request
within 14 days of payment: email federico.neffa@gmail.com.

**Windows warnings and hash?** SHA256 confirms identical files, not publisher
identity. SmartScreen may warn about the unsigned file's reputation; the
More info → Run anyway option may be available. Smart App Control can block
it completely; real validation is pending. Do not disable protections as an
ordinary installation step. Investigate actual Defender detections separately.
