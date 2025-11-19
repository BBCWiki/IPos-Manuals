---
layout: home
title: DynamicsReport
parent: Dynamics Report
grand_parent: BackOffice Sede
nav_order: 4
---

# ***REPORT SU RICHIESTA:***

**A**.

- **Operazioni Preliminari:**

Per creare un report su richiesta in IPOS, vi sono più moduli coinvolti
tra cui :

**Data Source Connectivity:** Moduli incaricati di stabilire la
connessione e recuperare i dati da svariate fonti (es. database
relazionali via SQL, servizi web REST/SOAP, file CSV/XML/JSON).

**FIleTemplate :** I file template sono lo scheletro vero e proprio del
report

**REPORT ENGINE**: Configurare con i dati del SMTP da utilizzare

**IPOS Modulo Utilità\StoreSetup:** Se l’utente necessita l’invio dei
report ad un indirizzo e-mail sarà necessario configurare il tutto nei
parametri StoreSetup di IPOS

**1**.

## **Data Source Connectivity SQL DATABASE:** Supponiamo di voler creare un
report per l’estrazione delle vendite dei negozi dell’intera catena.
Come prima cosa sarà necessario inserire i parametri StoreSetup inerenti
ai negozi (che può essere fatto anche da interfaccia GUI di IPOS dal
modulo **Utilià\StoreSetup**); di seguito una query di “**INSERT INTO**”
d’esempio : (da eseguire per tutti i negozi della catena)

INSERT INTO StoreSetup (StoreId, CashRegister, ParameterName,
ParameterAttribute, ParameterDescription, ParameterDefaultValue,
ParameterValue, IsSystemSetting) VALUES (323, NULL, 'THNStoreCode',
NULL, 'THN store code to export data', '10554', '10554', 1);

Sucessivamente creare la S.P. per l’estrazione delle vendite ad esempio
in un file CSV in un determinato percorso sul PC. (successivamente si
potrà inviare via e-mail o ftp\SFTP)

USE \[HQR\]

GO

/\*\*\*\*\*\* Object: StoredProcedure \[THN\].\[Report_Export_Sell\]
Script Date: 18/11/2025 12:22:57 \*\*\*\*\*\*/

SET ANSI_NULLS ON

GO

SET QUOTED_IDENTIFIER ON

GO

CREATE PROCEDURE \[THN\].\[Report_EXPORT_SELL\]

@ReportSubscriptionId Int

AS

BEGIN

SET NOCOUNT ON;

-- Dichiarazioni esistenti

DECLARE @SendOptionalData BIT = 1;

DECLARE @MARCOLIN_CHAINID VARCHAR(8) = ISNULL((SELECT ParameterValue
FROM StoreSetup WHERE ParameterName = 'THN_CHAINID'), '243990');

DECLARE @FromDate Date = CONVERT(Date,GETDATE());

DECLARE @ToDate Date = CONVERT(Date,GETDATE());

DECLARE @PreviousFromDate Date = CONVERT(Date,GETDATE());

DECLARE @PreviousToDate Date = CONVERT(Date,GETDATE());

DECLARE @StoreClusterId Int = 0;

DECLARE @StoreId Int = 0;

DECLARE @PreviousDaysOffSet Int;

DECLARE @Period int = 9;

SET DATEFIRST 1;

EXEC ReportPeriodDecode

@ReportSubscriptionId,

@FromDate = @FromDate Out,

@ToDate = @ToDate Out,

@PreviousFromDate = @PreviousFromDate Out,

@PreviousToDate = @PreviousToDate Out,

@PreviousDaysOffSet = @PreviousDaysOffSet Out;

DECLARE @ReferenceDate varchar(16) = FORMAT(GetDate(),'yyyyMMdd');

Select

@StoreClusterId = ISNULL(StoreClusterId,0)

,@StoreId = ISNULL(StoreId,0)

,@Period = Period

From

ReportSubscriptions Rs

Where

Rs.ReportSubscriptionId = @ReportSubscriptionId;

DECLARE @StoresLists TABLE (StoreId INT);

IF @StoreId \<\> 0

INSERT INTO @StoresLists

SELECT @StoreId;

IF @StoreClusterId \<\> 0

INSERT INTO @StoresLists

SELECT StoreId

FROM StoreClusterDetails WHERE StoreClusterId = @StoreClusterId;

-- \*\*\*\*\* SELEZIONE DATI ORIGINALE \*\*\*\*\*

-- I risultati di questa query verranno esportati

SELECT

'SELL' AS SELL_FILE_TYPE

,@THN_CHAINID AS SELL_CHAINID

,FORMAT(M.MovementDate,'yyyyMMdd') + '000000' AS SELL_REFE_DATE

,'' AS SELL_POS

,RTRIM(SS.ParameterValue) AS SELL_ADE_POS

,'' AS SELL_ITEM

,M.Barcode AS SELL_BC_ITEM

,CONVERT(INT,M.Quantity \* C.CauseSign) AS SELL_QTY

,'S' AS SELL_AGGR

,FORMAT(M.MovementTime,'yyyyMMddHHmmss') AS SELL_TIME

,'' AS SELL_PROMOT

,CASE WHEN @SendOptionalData = 1 THEN 'EUR' ELSE '' END AS SELL_ISO_CURR

,CASE WHEN @SendOptionalData = 1 THEN
CONVERT(VARCHAR(15),M.NetUnitValueVatIncluded) ELSE '' END AS
SELL_PRICEL

,CASE WHEN @SendOptionalData = 1 THEN
CONVERT(VARCHAR(15),M.NetRowValueVatIncluded) ELSE '' END AS SELL_VALUE

,CASE WHEN @SendOptionalData = 1 THEN S.Name ELSE '' END AS
SELL_POS_NAME

,CASE WHEN @SendOptionalData = 1 THEN P.Name ELSE '' END AS
SELL_ITEM_NAME

,CASE WHEN @SendOptionalData = 1 THEN 'THN' ELSE '' END AS SELL_BRAND

,CASE WHEN @SendOptionalData = 1 THEN 'THN' ELSE '' END AS
SELL_ITEM_SUPPLIER

,CASE WHEN @SendOptionalData = 1 THEN
CONVERT(VARCHAR(10),M.ReceiptNumber) ELSE '' END AS SELL_TICKET

,CASE WHEN @SendOptionalData = 1 THEN FORMAT(GETDATE(), 'yyyyMMdd') ELSE
'' END AS SELL_EXTR_DATE

,'' AS SELL_FREE

INTO

\##TempSalesData

FROM

Movements M

JOIN Causes C ON C.CauseId = M.CauseId

JOIN CauseGroups CG ON CG.CauseGroupId = C.CauseGroupId

JOIN Styles SY ON SY.StyleId = M.StyleId

JOIN Products P ON P.ProductId = SY.ProductId

JOIN ProducerLines PRL ON PRL.ProducerLineId = P.ProducerLineId

JOIN Producers PR ON PR.ProducerId = PRL.ProducerId

JOIN Stores S ON S.StoreId = M.StoreId

JOIN StoreSetup SS ON SS.ParameterName = 'THNStoreCode' And SS.StoreId =
M.StoreId

WHERE

M.ReceiptId IS NOT NULL

AND PR.Code = 'MRC'

-- FILTRO BARCODE

--AND M.Barcode NOT LIKE '210%'

AND M.MovementDate between @FromDate and @ToDate

ORDER BY SELL_ADE_POS, SELL_TIME;

-- \*\*\*\*\* AGGIUNGI L'ESPORTAZIONE E IL SALVATAGGIO DEL FILE
\*\*\*\*\*

-- Prepara il nome del file e il percorso dinamico

DECLARE @FileName VARCHAR(100);

DECLARE @FileDate VARCHAR(8) = FORMAT(GETDATE(), 'yyyyMMdd');

SET @FileName = 'SELL_243990\_' + @FileDate + '.TXT';

DECLARE @FolderPath VARCHAR(255) = 'C:\BBC\Export THN\\;

DECLARE @FilePath VARCHAR(500) = @FolderPath + @FileName;

-- Crea la cartella se non esiste

DECLARE @CreateFolderCmd VARCHAR(500) = 'IF NOT EXIST ' + @FolderPath +
' MKDIR ' + @FolderPath;

EXEC xp_cmdshell @CreateFolderCmd, no_output;

-- Comando bcp per esportare i dati

-- -t\| = separatore di campo pipe

-- -c = tipo di dati carattere

-- -T = connessione trusted (se usi un account Windows)

DECLARE @BcpCommand VARCHAR(2000);

SET @BcpCommand = 'bcp "SELECT SELL_FILE_TYPE, SELL_CHAINID,
SELL_REFE_DATE, SELL_POS, SELL_ADE_POS, SELL_ITEM, SELL_BC_ITEM,
SELL_QTY, SELL_AGGR, SELL_TIME, SELL_PROMOT, SELL_ISO_CURR, SELL_PRICEL,
SELL_VALUE, SELL_POS_NAME, SELL_ITEM_NAME, SELL_BRAND,
SELL_ITEM_SUPPLIER, SELL_TICKET, SELL_EXTR_DATE, SELL_FREE FROM ' +
QUOTENAME(DB_NAME()) + '..##TempSalesData ORDER BY SELL_ADE_POS,
SELL_TIME" queryout "' + @FilePath + '" -t"\|" -c -C 65001 -T';

EXEC xp_cmdshell @BcpCommand;

-- Pulisci la tabella temporanea

DROP TABLE \##TempSalesData;

END

>**NOTA:** **la sezione di codice qui sotto è valida per ogni report che sarà
>possibile sottoscrivere**

USE \[HQR\]

GO

/\*\*\*\*\*\* Object: StoredProcedure
\[THN\].\[Report_Export_Sell\] Script Date: 18/11/2025 12:22:57
\*\*\*\*\*\*/

SET ANSI_NULLS ON

GO

SET QUOTED_IDENTIFIER ON

GO

ALTER PROCEDURE \[THN\].\[Report_EXPORT_SELL\]

@ReportSubscriptionId Int

AS

BEGIN

SET NOCOUNT ON;

DECLARE @FromDate Date =
CONVERT(Date,GETDATE());

DECLARE @ToDate Date =
CONVERT(Date,GETDATE());

DECLARE @PreviousFromDate Date =
CONVERT(Date,GETDATE());

DECLARE @PreviousToDate Date =
CONVERT(Date,GETDATE());

DECLARE @StoreClusterId Int = 0;

DECLARE @StoreId Int = 0;

DECLARE @PreviousDaysOffSet Int;

DECLARE @Period int = 9;

SET DATEFIRST 1;

EXEC ReportPeriodDecode

@ReportSubscriptionId,

@FromDate = @FromDate Out,

@ToDate = @ToDate Out,

@PreviousFromDate = @PreviousFromDate Out,

@PreviousToDate = @PreviousToDate Out,

@PreviousDaysOffSet = @PreviousDaysOffSet Out;

DECLARE @ReferenceDate varchar(16) =
FORMAT(GetDate(),'yyyyMMdd');

Select

@StoreClusterId = ISNULL(StoreClusterId,0)

,@StoreId = ISNULL(StoreId,0)

,@Period = Period

From

ReportSubscriptions Rs

Where

Rs.ReportSubscriptionId =
@ReportSubscriptionId;

DECLARE @StoresLists TABLE (StoreId INT);

IF @StoreId \<\> 0

INSERT INTO @StoresLists

SELECT @StoreId;

IF @StoreClusterId \<\> 0

INSERT INTO @StoresLists

SELECT StoreId

FROM StoreClusterDetails WHERE StoreClusterId =
@StoreClusterId;

## **FIleTemplate :** (di seguio viene descritto un esempio)

**2**.

Creare un report template in XLS indicando i campi di output della
Stored procedure.

<img width="216" height="47" alt="image1" src="https://github.com/user-attachments/assets/2e6bde16-9ddd-4a90-bb02-0ad5d242133a" />

Perfarlo è possibile generarlo internarmente in IPOS tramite il modulo
“Foglio Elettronico” del menu Utilità

1)  Nella prima colonna ci sono le tipologie delle righe

**H=Header**

**D= Detail**

**GF= ClusterName**

**F=Footer**

<img width="1484" height="375" alt="image2" src="https://github.com/user-attachments/assets/d33e44f8-bfb5-4922-893d-cd206b44e852" />

2)  Per i campi Detail dichiarare il **nome** delle variabili

- Posizionarsi sulla cella dove creare la variabile

- Premere su “Formulas”

- In seguito premere sull’Icona “Name Manager” per aprire lo strumento
  per la creazione di una variabile

- Premere sul tasto “New…” per inserire la nuova variabile

- I riferimenti vengono popolati in autonomia

<img width="1221" height="477" alt="image3" src="https://github.com/user-attachments/assets/bdf6fc83-89e4-4307-b30e-6dccd9a37f7c" />
<img width="1066" height="283" alt="image4" src="https://github.com/user-attachments/assets/ce3e8a99-5b4d-4059-9b57-e87871a9b9b1" />

3)  Per i campi Footer dei totali, settare le varie formule ad esempio:

- La somma delle chiusure andrà settata nella riga F sotto la colonna
  Chiusure tenendo conto della Variabile Chiusure che si è creata
  precedentemente

<img width="1473" height="270" alt="image9" src="https://github.com/user-attachments/assets/ff465574-b266-4699-8096-7cae39f4a0f3" />

- Si desidera vedere il totale ? Si dovrà effettuare la somma dei valori
  delle celle K ed L

<img width="1845" height="185" alt="image10" src="https://github.com/user-attachments/assets/78f37ef1-5eda-47ad-9e7a-589c5c92e5a3" />

- Si desidera vedere gli incassi ad esempio dei Bancomat ? IN precedenza
  si sarà dovuta creare la Variabile di riferimento. Supponiamo di
  averla chiamata SCBancomat

<img width="791" height="332" alt="image11" src="https://github.com/user-attachments/assets/8764e4ca-0feb-43c0-a0b4-f717437118ee" />

- Si dovrà inserire la formula =SUM(NomeVariabile) 🡪 =SUM(SCBancomat)

<img width="1859" height="210" alt="image12" src="https://github.com/user-attachments/assets/03789130-bff0-4677-a6ad-545dcf4c5add" />

se c’è da sommare i valori di un campo o fare dei calcoli, Dichiarare il nome della variabile

<img width="1202" height="522" alt="image13" src="https://github.com/user-attachments/assets/1b2e2009-4b15-425d-a823-45fb26fb1f9a" />

> **NOTA: Queste operazioni saranno da fare per tutti i campi che si ritengono opportuni.**

**3**.

**REPORT ENGINE:** Il report Engine è un componente software
fondamentale, progettato per il compito specifico di **trasformare i
dati grezzi in informazioni strutturate e leggibili** sotto forma di
report. SI trova (se installato) nel percorso C:\BBC\ReportEngine.
Andare nel percorso dell’installazione e configurare il Report Engine.exe.config con i dati
del SMTP da utilizzare. Vedi esempio:

<img width="1466" height="556" alt="image14" src="https://github.com/user-attachments/assets/5752e805-cbf7-4e3a-8e52-85c013a9a2ff" />

>**NOTA:** Sarà poi da utilizzare in utilità pianificata di Windows nel
>caso in cui si vuole automatizzare il report. Il ReportEngine.exe è
>all’interno di una cartella (serve intera cartella) e viene lanciato
>nello scheduler con un parametro che corrisponde all’indice esecuzione
>(gruppo di esecuzione). Questo sarà ripreso più avanti nel documento

**4**.

**IPOS Modulo Utilità\StoreSetup:** Loggarsi nel Back-Office di
IPOS e premere a sinistra sul menu “**Utilità**”. Il meno verrà esploso
nella parte superiore sinistra della videata; premere successivamente
sul modulo “**Configurazione Store**” per aprire l’elenco dei parametri IPOS

<img width="1842" height="962" alt="image15" src="https://github.com/user-attachments/assets/b0ae0e0b-376c-49c8-ae90-b9a0de157a64" />


Di seguito l’elenco dei Parametri da configurare per settare l’invio del
report tramite e-mail :

<img width="1216" height="229" alt="image16" src="https://github.com/user-attachments/assets/4ba9c6d0-c7e7-4524-a294-d59ad60233b3" />


**B**.

- **Creazione Report:**

Loggarsi nel Back-Office di IPOS e premere a sinistra sul menu “**Dynamic Reports**” per vedere i
moduli coinvolti:

<img width="860" height="356" alt="image17" src="https://github.com/user-attachments/assets/6b1da7ee-b048-4751-995e-1b6d8929f049" />

**1**.

- **Report Editor:**

Per creare un nuovo report premere sul modulo “Report Editor” e
successivamente sull’Icona definita dal “**simbolo +**”.

<img width="1886" height="450" alt="image18" src="https://github.com/user-attachments/assets/fc468552-b795-47ab-833e-b7ae845d08d3" />

Si aprirà così una nuova riga per l’inserimento di un nuovo report e si attiverà anche l’icona del
salvataggio definita dal “floppy disk”:

<img width="1887" height="475" alt="image19" src="https://github.com/user-attachments/assets/10293d54-a6fa-4db8-8594-6c075bc9eb63" />

Compilare dunque tutti i campi tranne il campo ID che è di tipo
“Identity” e verrà incrementato autonomamente quando il report verrà
salvato.

Di seguito un esempio :

**NOME:** Export THN – SELL (Questo valore indicherà il nome del report
da eseguire)

**STORE PROCEDURE:**
THN.Report_EXPORT_SELL (Questo valore indica il nome della Store
Procedure che estrae i dati e che è stata precedentemente creata)

<img width="1887" height="475" alt="image19" src="https://github.com/user-attachments/assets/803869bb-55dd-4d1f-98d0-423e36eef646" />

**TITOLO:** EXPORT SELL (questo valore da un indicazione di ciò che fa
il report)

**PERCORSO FILE TEMPLATE:** Vi possono essere 3 tipologie di percorso.

<img width="204" height="65" alt="image21" src="https://github.com/user-attachments/assets/88eba0f9-717b-4575-bf70-a1102f8b3575" />

Indica un percorsoFTP(sceglierlo se il file si trova su FTP)
Indica un percorso sul PC in locale**(scelta raccomandata**)
Non è in uso

Scegliendo dunque “**Load Template file**” si aprirà una finestra di windows per cercare in locale
il file template da associare al report che si sta creando (consigliamo
di crearli tutti i un unico percorso, ad esempio
“C**:\BBC\ReportTemplates**”).

<img width="936" height="527" alt="image22" src="https://github.com/user-attachments/assets/9bc9f464-2840-4678-932f-7c69f5ee1f1f" />

**FILE NAME FORMAT:** Bisogna indicare il nome del file (ed il formato)
che si desidera creare.

<img width="1097" height="138" alt="image23" src="https://github.com/user-attachments/assets/80e0f5be-e7f3-417b-bbc0-de22a36bb0fb" />

**CSV SEPARATOR:** Nel caso di un report che genera un file CSV,
indicare con quale separatore (virgola, punto e virgola ecc.)

**RUOLO:** Indicare il ruolo utente necessario per poter eseguire il
report.

Una volta terminato di inserire i valori, salvare il report con
avvalendosi dell’apposita icona definita dal “**floppy disk**”

<img width="1528" height="205" alt="image24" src="https://github.com/user-attachments/assets/0f164f8a-16fb-435c-b08f-8bd6b6ac0fbe" />


Rispondere “OK” al successivo messaggio d’avviso

<img width="621" height="252" alt="image25" src="https://github.com/user-attachments/assets/f0ad15b1-b221-4965-89e0-c1a648d137d1" />

**C**.

## **SOTTOSCRIZIONI REPORT**:

Aprire il modulo successivo “Sottoscrizioni report” e procedere alla
creazione della sottoscrizione come segue:

Premere sull’Icona definita dal simbolo “**+**” per aprire la finestra
della nuova sottoscrizione

<img width="1138" height="552" alt="image26" src="https://github.com/user-attachments/assets/a4b1df45-cda7-4c86-a486-25c9efb433ff" />

Compilare mettendo i valori nei campi che si ritengono opportuni:

**REPORT**: premere sul tasto del menu a tendina e selezionare il report
da sottoscrivere

**Store Cluster**: Indicare il cluster di negozi da cui estrarre i dati.

**PERIODO**: indicare il periodo per la sottoscrizione

**INDICE ESECUZIONE**: indicare il nome parametro a cui farà riferimento
il Report Engine nello scheduler dell’ operazione automatica di windows.

**PROFONDITA’ FILE** : scegliere se un file unico e un file per ogni
negozio

**URL**: Indicare il percorso del file del report

>**INVIA PER MAIL** : Settare
il pallino su questa scelta per la sottoscrizione report.

<img width="899" height="442" alt="image27" src="https://github.com/user-attachments/assets/0597f638-3821-4204-b3d5-4ac3f8343ac2" />

Premere sull’icona del “**floppy disk**” per salvare il contenuto della
sottoscrizione. Successivamente salvare la sottoscrizione stessa sempre
col tasto del “**floppy disk**”.

**D**.

## **ESEGUIRE IL REPORT:**

Per eseguire il report Report Su Richiesta, premere sull’apposito modulo
del menu Dynamics Report, compilare i campi con i dati del report che si
desidera eseguire :

<img width="865" height="285" alt="image28" src="https://github.com/user-attachments/assets/eaa29045-9466-4632-9f62-ba217627c42f" />


**E**.

## **Creare l’utilità di pianificazione (task scheduler**) :

Aprire l’Unità di pianificazione d windows, premere col tasto destro del
mouse su “Libreria Unità di Pianificazione e successivamente col tasto
sinistro del mouse su “Crea attività”

<img width="1222" height="407" alt="image29" src="https://github.com/user-attachments/assets/75902118-2950-40a9-bc6c-d1f9f00ce686" />

Compilare come segue :

**1**.

### **TAB GENERALE:**

**Nome:** Inserire il nome dell’operazione

**Descrizione (facoltativo):** Inserire una breve descrizione
dell’operazione

**Opzioni di sicurezza:**

- Settare esegui indipendentemente dalla connessione degli utenti

- Settare esegui con i privilegi più elevati

<img width="629" height="474" alt="image30" src="https://github.com/user-attachments/assets/a9d29316-ce34-4c99-a266-f848d9138bdc" />

**2**.

### **TAB ATTIVAZIONE:**

**Impostazioni:**

- Settare “Giornialiera”

**Inizio:**

- Settare data e ora dell’avvio dell’attivazione

**Impostazioni avanzate:**

- Settare “Arresta attività eseguite per più di 3 giorni”

- Settare “Attivato”

<img width="1227" height="517" alt="image31" src="https://github.com/user-attachments/assets/175c01bb-3eb5-4245-aa4c-d705ac76e8b9" />

**3**.

### **TAB AZIONI:**

**Programma o script**: premendo sul tasto sfoglia, indicare il percorso
dell’eseguibile del ReportEngine
<img width="892" height="101" alt="image32" src="https://github.com/user-attachments/assets/36ec3a0b-78c6-4c1c-a951-7ec52fb29cab" />

**Aggiungi argomenti:**
Settare l’indice di esecuzione della sottoscrizione report

**Inizio:** Settare il percorso

<img width="1085" height="499" alt="image33" src="https://github.com/user-attachments/assets/431ae8b4-559d-4c90-93f2-67c9bd8174e2" />

**4**.

### **TAB CONDIZIONI:**

**Alimentazione:**

- Settare “avvia attività solo se il computer è alimentato da rete
  elettrica”

- Settare “interrompi se il computer passa all’alimentazione a batteria”

<img width="631" height="479" alt="image34" src="https://github.com/user-attachments/assets/4cc2aa95-f83b-4b88-9c7d-d532abe36df1" />


**5**.

### **TAB IMPOSTAZIONI:**

**Ulteriori impostazioni:**

- Settare “consenti esecuzione attività su richiesta”

- Settare “avvia appena possibile se un avvio pianificato non viene
  eseguito”

- Settare “interrompi se eseguita per oltre 3 Giorni”

- Settare “se l’attività non cessa quando richiesto, imponi
  l’interruzione”

<img width="630" height="475" alt="image35" src="https://github.com/user-attachments/assets/ffaf2ab6-d7ed-401b-a46a-b952129e55c6" />

**6**. 

>**Nota:** Quando viene
>salvato viene richiesto di inserire utente e password del pc
> <img width="953" height="561" alt="image36" src="https://github.com/user-attachments/assets/764cafd1-2a82-4163-a8da-b2df155831e9" />

Dopo aver premuto su “ok”, l’attività verrà inserita nell’elenco:

<img width="995" height="322" alt="image37" src="https://github.com/user-attachments/assets/ad6dcaf3-3519-42d7-9085-45162c0d139a" />

**7**.

**LOG REPORT ENGINE:**

Il log dell’esecuzione è **in c:\bbc\log\AAAA_MM\IPOS.ReportEngine** ma
potrebbe trovarsi anche direttamente la cartella principale dove c’è
l’eseguibile

<img width="1482" height="606" alt="image38" src="https://github.com/user-attachments/assets/7067f25c-13a9-4db5-bdf1-2464d51ef456" />

**F**.

### **TEST**

E’ possibile fare un test sul SMTP tramite Cmd o Powershell windows.

Aprire cmd o powershell come utente administrator , andare al percorso
del ReportEngine ed eseguire il comando (l’e-mail del test è solo un
esempio):

“**Reportengine.exe SMTPTEST mpesenti@bbctech.it**”

<img width="446" height="92" alt="image39" src="https://github.com/user-attachments/assets/015d6573-98d0-4b3d-9367-a6a74c790fb2" />

Controllare la casella di posta elettronica in quanto dovrebbe arrivare anche una mail di test

<img width="410" height="175" alt="image40" src="https://github.com/user-attachments/assets/221c632d-ee1e-4604-a753-a295a6ed6b9c" />

Nel caso in cui il test fallisse, potrebbe essere necessario abilitare
le porte richieste nel Firewall. Selezionare **Outbound Rules** e
premere a destra nella sezione “**Actions**” su “**New Rule…**”

<img width="1466" height="215" alt="image41" src="https://github.com/user-attachments/assets/f4b33922-53d7-482e-8802-1461e0a867d3" />


Selezionare “**Port**” e premere su “**Next**”. Nella schermata
successiva selezionare “TCP” e “Specific remote ports”. Settare dunque
la porta 587 e premere su “NEXT”.

<img width="1218" height="470" alt="image42" src="https://github.com/user-attachments/assets/f8750e2e-b8d5-4365-882a-7074d782d855" />


Nella finestra successiva selezionare “Allow the connection” e premere
su “Next”. Selezionare tutte le opzioni e premere nuovamente su “Next”

<img width="860" height="339" alt="image43" src="https://github.com/user-attachments/assets/4a9b5897-0897-4cc3-8e51-2d8af8d534b4" />


Nella schermata che si apre, inserire il nome della regola e premere su
finish per salvarla

<img width="447" height="365" alt="image44" src="https://github.com/user-attachments/assets/d4bf96df-f907-43c1-9746-522568f82263" />


Ecco la regola salvata nell’elenco del Firewall di windows.

<img width="999" height="94" alt="image45" src="https://github.com/user-attachments/assets/b37e374b-e2f9-4267-be65-fbfd10a11eeb" />

