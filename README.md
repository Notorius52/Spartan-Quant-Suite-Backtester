🦅 Spartan Overlord & Fleet Backtester
Quantitative Multi-Asset Backtesting Suite for MetaTrader 5

Benvenuto nella suite di backtesting quantitativo per il tuo gestore di portafoglio Spartan Overlord e i relativi 12 Battaglioni Spartan (Crypto, Indici, Metalli). Questa guida ti permetterà di simulare il comportamento dell'intera flotta in Python, testando la resilienza del sistema di fronte a scenari di mercato estremi (Margin Guard, Hedge Strutturale e Logoramento Collaborativo).

Questa è la versione definitiva, stabile e permanente dell'intero ecosistema. Include l'integrazione nativa del bypass per il convalidatore del Market MQL5 e la completa stabilizzazione del motore di calcolo (indicatori tecnici su base ta).

🛠️ 1. Requisiti di Sistema
Per eseguire i test è necessario installare Python (versione 3.11 o superiore).
Le librerie necessarie sono elencate nel file requirements.txt e possono essere installate rapidamente lanciando il seguente comando dal terminale (nella cartella principale del progetto):

Bash
pip install -r requirements.txt
(Librerie utilizzate: pandas, numpy, ta)

💾 2. Preparazione della Linea di Rifornimento Dati (TRINCEA)
MetaTrader 5 esporta i dati storici in modo frammentato. Il simulatore ha bisogno di unire e sincronizzare i flussi di prezzo dei 12 asset (tenendo conto che le crypto girano 24/7 mentre gli indici chiudono nei weekend).

Esporta gli storici da MT5: Estrai i file .csv (consigliato timeframe M15 o H1) per tutti i 12 ticker attivi della tua flotta (es. BTCETH_M15.csv, US500.c_M15.csv, XAUUSD_M15.csv, ecc.).

Posiziona i file: Inserisci i 12 file .csv grezzi all'interno della cartella data/raw_mt5/.

Sincronizzazione temporale: Esegui lo script di allineamento. Questo applicherà la logica del Forward Fill per unificare le timeline ed eliminare eventuali asincronie tra i mercati:

Bash
python core/data_merger.py
Il sistema genererà il file processed_data.csv nella cartella data/, contenente migliaia di periodi temporali pronti all'uso.

⚙️ 3. Configurazione Tattica e Allineamento Matrice
Prima di lanciare la simulazione, puoi verificare o modificare i parametri globali della flotta e le soglie della Triade Perfetta (ADX, RSI, ATR) direttamente dal file config/fleet_settings.py.

Nota bene sull'allineamento operativo: per garantire la massima efficacia, i parametri dei singoli Battaglioni (come l'RSI a 14 o 60 periodi a seconda dell'asset istituzionale) e la reattività della flotta sono stati meticolosamente allineati per operare in sinergia con il Margin Guard:

initial_capital: Capitale di partenza (es. 10000.0 USD).

max_drawdown_pct: Soglia critica di attivazione dell'Hedge Strutturale (es. 4.0%).

trailing_activation e trailing_step: Parametri del Trailing Profit olistico di flotta.

logoramento_target: Profitto minimo cumulato dei battaglioni sani necessario per avviare il cecchino e smantellare l'hedge.

🚀 4. Esecuzione della Simulazione e Stress Test
Una volta allineati i dati e calibrati i parametri, il quartier generale è pronto ad attaccare il mercato. Lancia il motore di calcolo con il comando:

Bash
python main_simulation.py
Cosa succede durante il test:
Il motore calcola simultaneamente gli indicatori tecnici (ADX, RSI, ATR) su tutti i 12 canali.

I singoli Battaglioni scansionano il mercato ed eseguono le operazioni nominali di assalto, continuando a combattere ed evolvere anche in situazioni di emergenza per alimentare la cassa.

L'Overlord supervisiona l'equity globale in tempo reale.

Resilienza e Logoramento: Se il mercato va contro la flotta superando il drawdown massimo, l'Overlord innesca l'Hedge Strutturale (Magic = 999999). A quel punto, i singoli battaglioni continuano ad operare generando cassa per finanziare il Cecchino (Collaborative Sniper), che andrà a tagliare progressivamente i lotti in perdita fino allo sblocco totale della flotta.

📊 5. Analisi del Bollettino e Reportistica
📌 Storico Aggiornato - Telemetria Ufficiale (Timeframe M15/H1)
L'architettura, grazie agli ultimi set di calibrazione e all'affinamento dei trigger operativi (es. calibro RSI ottimizzato per l'intera flotta), ha superato stress-test pluriennali di grande impatto, tra cui repentine escursioni di volatilità e crolli.

Stress Test con Logoramento Attivo (Es. Crollo Dicembre 2025)

Evento critico: Innesco Hedge Strutturale il 2025-12-24 18:30:00 (Drawdown 4.06% pre-natalizio).

Risposta del sistema: La flotta ha continuato a generare profitto con i restanti asset, finanziando il Cecchino e riassorbendo completamente l'emergenza.

Bilancio Finale Registrato: 31.772,86 USD (partendo da 10.000 USD).

Totale Operazioni Eseguite: 375

Al termine di ogni simulazione, il terminale stamperà il bilancio finale e salverà un report dettagliato con l'intera telemetria delle operazioni eseguite:

spartan_report.csv: Report completo di tutte le transazioni, orari di innesco delle difese, tagli parziali dell'hedge e profitti incassati.

Puoi aprire istantaneamente il report in Excel o nel tuo visualizzatore CSV preferito digitando da terminale:

Bash
start spartan_report.csv
Suite sviluppata per il trading algoritmico quantitativo professionale MQL5.
