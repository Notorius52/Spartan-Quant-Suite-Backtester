# Spartan-Quant-Suite-Backtester
core/overlord_engine.py: Il motore centrale olistico. Gestisce il capitale iniziale, il calcolo dell'equity, il trailing di flotta, l'Hedge strutturale di emergenza (Magic 999999) e il Logoramento collaborativo (Collaborative Sniper).
C:\Users\direz>cd C:\Users\direz\Documents\Spartan_Overlord_Tester 
 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python core/data_merger.py 
  Inizializzazione Fusione Dati per la Flotta Spartan... 
     Allineamento dati Battaglione: BTCETH 
     Allineamento dati Battaglione: BTCXRP 
     Allineamento dati Battaglione: DE40.c.csv 
     Allineamento dati Battaglione: DJ30.c 
     Allineamento dati Battaglione: F40.c 
     Allineamento dati Battaglione: JP225.c 
     Allineamento dati Battaglione: processed 
  Errore durante l'elaborazione di processed: No columns to parse from file 
     Allineamento dati Battaglione: STOXX50.c 
     Allineamento dati Battaglione: UK100.c 
     Allineamento dati Battaglione: US500.c 
     Allineamento dati Battaglione: USTEC.c 
     Allineamento dati Battaglione: XAGUSD 
     Allineamento dati Battaglione: XAUUSD 
    Sincronizzazione temporale e applicazione Forward Fill sui gap... 
C:\Users\direz\Documents\Spartan_Overlord_Tester\core\data_merger.py:60: FutureWarning: 
DataFrame.fillna with 'method' is deprecated and will raise in a future version. Use obj.ffill() or 
obj.bfill() instead. 
  master_df.fillna(method='ffill', inplace=True) 
   Fusione completata con successo. 
       File Master salvato in: 
C:\Users\direz\Documents\Spartan_Overlord_Tester\data\processed_data.csv 
      Dimensione Dataset Globale: 19511 periodi temporali pronti per il backtest. 
 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python main_simulation.py 
Traceback (most recent call last): 
File "C:\Users\direz\Documents\Spartan_Overlord_Tester\main_simulation.py", line 4, in 
<module> 
from core.indicators import calculate_triad 
File "C:\Users\direz\Documents\Spartan_Overlord_Tester\core\indicators.py", line 3, in 
<module> 
import pandas_ta as ta 
ModuleNotFoundError: No module named 'pandas_ta' 
C:\Users\direz\Documents\Spartan_Overlord_Tester>pip install -r requirements.txt 
Requirement already satisfied: pandas in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from -r 
requirements.txt (line 1)) (2.3.3) 
Requirement already satisfied: numpy in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from -r 
requirements.txt (line 2)) (2.3.5) 
ERROR: Ignored the following versions that require a different python version: 0.4.67b0 Requires
Python >=3.12; 0.4.71b0 Requires-Python >=3.12 
ERROR: Could not find a version that satisfies the requirement pandas-ta (from versions: none) 
ERROR: No matching distribution found for pandas-ta 
[notice] A new release of pip is available: 24.0 -> 26.1.2 
[notice] To update, run: python.exe -m pip install --upgrade pip 
C:\Users\direz\Documents\Spartan_Overlord_Tester>pip install ta 
Collecting ta 
Downloading ta-0.11.0.tar.gz (25 kB) 
Installing build dependencies ... done 
Getting requirements to build wheel ... done 
Preparing metadata (pyproject.toml) ... done 
Requirement already satisfied: numpy in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from ta) (2.3.5) 
Requirement already satisfied: pandas in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from ta) (2.3.3) 
Requirement already satisfied: python-dateutil>=2.8.2 in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from pandas->ta) 
(2.9.0.post0) 
Requirement already satisfied: pytz>=2020.1 in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from pandas->ta) 
(2025.2) 
Requirement already satisfied: tzdata>=2022.7 in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from pandas->ta) 
(2025.3) 
Requirement already satisfied: six>=1.5 in 
c:\users\direz\appdata\local\programs\python\python311\lib\site-packages (from python
dateutil>=2.8.2->pandas->ta) (1.17.0) 
Building wheels for collected packages: ta 
Building wheel for ta (pyproject.toml) ... done 
Created wheel for ta: filename=ta-0.11.0-py3-none-any.whl size=29497 
sha256=2176b82e342a4edb1d86140da6678c87974afbfde00d8c6a9128500606ed5ff0 
Stored in directory: 
c:\users\direz\appdata\local\pip\cache\wheels\a1\d7\29\7781cc5eb9a3659d032d7d15bdd0f49d
07d2b24fec29f44bc4 
Successfully built ta 
Installing collected packages: ta 
Successfully installed ta-0.11.0 
[notice] A new release of pip is available: 24.0 -> 26.1.2 
[notice] To update, run: python.exe -m pip install --upgrade pip 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python main_simulation.py 
Caricamento dati storici della Flotta... 
Calcolo Indicatori Tattici (ADX, RSI, ATR) per tutti i Battaglioni... 
         Overlord Engine avviato. Elaborazione storico... 
       [2026-05-27 02:45:00] MARGIN GUARD ATTIVO! Drawdown: 4.41%. Flotta congelata. 
    Backtest Terminato. Bilancio Finale: 10620.46 USD 
     Report Dettagliato salvato in: 
C:\Users\direz\Documents\Spartan_Overlord_Tester\spartan_report.csv 
           Totale Operazioni Eseguite: 215 
 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python main_simulation.py 
      Caricamento dati storici della Flotta... 
       Calcolo Indicatori Tattici (ADX, RSI, ATR) per tutti i Battaglioni... 
         Esecuzione simulazione ad eventi con Logoramento Attivo... 
       [2025-12-24 18:30:00] SOGLIA CRITICA! Drawdown: 4.06%. Esecuzione Hedge Strutturale. 
    Simulazione Terminata. Bilancio Finale: 14339.99 USD 
     Report Dettagliato salvato in: 
C:\Users\direz\Documents\Spartan_Overlord_Tester\spartan_report.csv 
           Totale Operazioni Eseguite: 32 
 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python main_simulation.py 
      Caricamento dati storici della Flotta... 
       Calcolo Indicatori Tattici (ADX, RSI, ATR) per tutti i Battaglioni... 
Traceback (most recent call last): 
  File "C:\Users\direz\Documents\Spartan_Overlord_Tester\main_simulation.py", line 48, in 
<module> 
    main() 
  File "C:\Users\direz\Documents\Spartan_Overlord_Tester\main_simulation.py", line 38, in main 
    trade_report = overlord.run(df) 
                   ^^^^^^^^^^^^ 
AttributeError: 'SpartanOverlord' object has no attribute 'run' 
 
C:\Users\direz\Documents\Spartan_Overlord_Tester>python main_simulation.py 
Caricamento dati storici della Flotta... 
Calcolo Indicatori Tattici (ADX, RSI, ATR) per tutti i Battaglioni... 
Esecuzione simulazione ad eventi con Logoramento Attivo... 
[2025-12-24 18:30:00] SOGLIA CRITICA! Drawdown: 4.06%. Esecuzione Hedge Strutturale. 
Simulazione Terminata. Bilancio Finale: 19646.85 USD 
Report Dettagliato salvato in: 
C:\Users\direz\Documents\Spartan_Overlord_Tester\spartan_report.csv 
Totale Operazioni Eseguite: 126
