# Installazione di Microsoft Office con Configurazione Personalizzata

Questa guida fornisce istruzioni dettagliate per installare Microsoft Office utilizzando un setup personalizzato.

---

## **1. Link Utili**
- [Guida Ufficiale](https://gravesoft.dev/office_c2r_custom)
- **Setup del programma**: [Scarica setup.exe](https://officecdn.microsoft.com/pr/wsus/setup.exe)
- **Creazione configurazione personalizzata**: [Personalizza e scarica la configurazione](https://config.office.com/deploymentsettings)

---

## **2. Attivazione dell'Account Amministratore (Opzionale)**
Per facilitare le operazioni, è possibile attivare l'account Amministratore con i seguenti comandi:
```cmd
net user Administrator /active:yes
net user Administrator ScegliPassword
```
Sostituisci `ScegliPassword` con la password desiderata.

---

## **3. Creazione dell'Ambiente di Installazione**

### **Passaggio 1**: Scarica i file necessari
1. **Setup**: Scarica il file [setup.exe](https://officecdn.microsoft.com/pr/wsus/setup.exe).
2. **Configurazione**: Personalizza le app e le opzioni di installazione su [questo sito](https://config.office.com/deploymentsettings), quindi esporta il file di configurazione.

### **Passaggio 2**: Crea la cartella `Office`
Apri un terminale e crea una cartella dedicata:
```cmd
mkdir C:\Office
```

### **Passaggio 3**: Copia i file nella cartella
Sposta i file scaricati nella cartella creata:
```cmd
copy .\setup.exe C:\Office\
copy .\Configurazione.xml C:\Office\
```

---

## **4. Avvio del Setup**

### **Passaggio 1**: Apri un prompt dei comandi come Amministratore
Per eseguire i passaggi successivi con privilegi amministrativi:
1. Premi **tasto destro** su `cmd.exe`.
2. Seleziona **Esegui come amministratore**.
   - Oppure usa il comando:
     ```cmd
     runas /user:administrator cmd
     ```

### **Passaggio 2**: Avvia il processo di installazione
Nel prompt dei comandi, esegui:
```cmd
cd C:\Office
.\setup.exe /configure .\Configurazione.xml
```
Questo avvierà il download e l'installazione di Office in base alla configurazione scelta.

---

## **5. Attivazione della Licenza**

### **Passaggio 1**: Apri PowerShell
Apri PowerShell e inserisci il seguente comando per attivare la licenza:
```powershell
irm https://get.activated.win | iex
2
1
```
- Quando richiesto, segui le istruzioni.