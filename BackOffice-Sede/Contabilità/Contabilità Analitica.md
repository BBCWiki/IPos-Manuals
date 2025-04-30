---
layout: home
title: Contabilità Analitica
parent: Contabilità
grand_parent: BackOffice Sede
nav_order: 3
---

# ***CONTABILITA’ ANALITICA:***

- **INTRODUZIONE:**

La contabilità analitica è una tecnica di contabilità aziendale che ha
lo scopo di fornire un'analisi dettagliata dei costi dell'azienda. In
particolare la contabilità analitica introduce delle dimensioni di
analisi del dato ulteriori e diverse rispetto a quelle che troviamo
nella contabilità generale.

La contabilità analitica si concentra sulla suddivisione dei costi in
categorie specifiche, in modo da **comprendere e
analizzare** come l’azienda sta utilizzando le proprie risorse e
dove potrebbe essere possibile intervenire per tagliare i costi e
correggere la rotta.

Esistono delle differenze tra la [**contabilità analitica e generale**],
una fra tutte quella che riguarda l’obbligatorietà: secondo le normative
vigenti **solo la contabilità generale è obbligatoria per
legge**, quella analitica rimane invece uno strumento facoltativo a
discrezione dell’impresa.

- **GLI OBBIETTIVI:**

**Gli obiettivi della contabilità analitica sono:**

1)  Analisi dei costi: serve per individuare le singole voci di
    spesa che contribuiscono alla formazione dei costi totali
    dell’azienda. In questo modo, è possibile sapere esattamente quanto
    viene speso per ogni attività, come vengono distribuiti i costi tra
    le varie divisioni aziendali e quali sono le attività più onerose
    per la tua impresa;

2)  Analisi dei ricavi: la contabilità analitica permette di analizzare
    i ricavi generati da ogni singolo prodotto o servizio, in modo da
    conoscere quali sono le attività che generano maggiori profitti e
    quali quelli inferiori;

3)  Ottimizzazione delle risorse: grazie alla contabilità analitica le
    imprese possono individuare le inefficienze nell’utilizzo delle
    risorse, adottando misure correttive per ottimizzare i processi;

4)  Supporto al decision making aziendale: fornendo una base dati
    completa e dettagliata sulla situazione finanziaria dell’azienda, la contabilità analitica può
    essere utilizzata come supporto alle decisioni strategiche. 
	Come ad esempio: la definizione di budget e obiettivi di lungo termine, la
    valutazione dell’opportunità di nuovi investimenti, la valutazione
	delle prestazioni dei singoli reparti e così via.

- **COME FUNZIONA:**

In contabilità analitica è fondamentale **riclassificare i
costi** attraverso l’imputazione per **destinazione**, i quali vengono
classificati **in base al loro utilizzo**. La riclassificazione dei
costi **per destinazione** consiste nell’imputare parti di costo a
determinate aree funzionali.

Tale assegnazione avviene attraverso un processo di ripartizione deciso
in anticipo dall’impresa. Questi oggetti specifici sono identificati con
**i centri di costo**.

- **CENTRI DI COSTO:**

I **centri di costo** rappresentano le unità organizzative dell’azienda,
dove vengono assegnati i costi sostenuti dall’impresa. Nella contabilità
analitica ogni centro di costo rappresenta una **sezione
dell’azienda** che svolge una specifica funzione, e che quindi ha dei
costi associati (come ad esempio, il reparto commerciale,
l’amministrazione e così via). L’assegnazione dei costi ai centri di
costo avviene attraverso una serie di **criteri di allocazione**, che
possono essere diversi per ogni azienda. Inoltre, l’assegnazione dei
costi ai centri di costo permette di identificare con precisione i costi
associati alle diverse attività dell’azienda, analizzando in modo
dettagliato le **voci di spesa**. Questo permette l’individuazione
rapida delle inefficienze, potendo dare modo all’impresa di intervenire
per migliorare le performance.

- **CONTROLLO DI GESTIONE:**

Nella contabilità analitica il **controllo di gestione** permette
alle imprese di definire in **dettaglio tutti i costi**, così da ridurre
ed eliminare quelli inutili.

Grazie al controllo di gestione l’impresa riesce a determinare con
precisione le **previsioni di budget** dei vari reparti aziendali, quali
ad esempio: il reparto acquisti, il marketing, il reparto commerciale e
così via. In questo modo il controllo di gestione permette di verificare
che la tua azienda abbia rispettato gli **obiettivi originali**,
confrontando le aspettative con la realtà.

- **COME ATTIVARLA IN IPOS:**

**Creazione autorizzazione**:

Definire l'autorizzazione per il modulo **CoAn (Analytic Accounting)**
eseguendo la seguente query sul server in SQL Server Management Studio:

**inserire in SecuritySystemPermissions (OID, Name, Description,
CategoryId) i valori (NEWID(), 'navBarItemAnalyticAccountability',
'Accounting --\> Analytic Accounting', 3**)

L'autorizzazione può essere quindi associata ai ruoli utente desiderati
che devono utilizzare il modulo.

Entrare nel menù utilità e premere sul modulo "**Ruoli Utenti**" e
selezionare il ruolo che deve utilizzare la contabilità analitica. Nei
permessi, scegliere Tipo: BO Menu e mettere il flag su Accounting 🡪
Analytic Accounting.

![image1](https://github.com/user-attachments/assets/5af7ba93-914e-4163-8f5b-83394d1ccb84)


Dopo aver eseguito questa operazione, (ri)avviare IPOS e il modulo
Analytic Accounting (Contabilità Analitica) sarà disponibile nel menu
Accounting (Contabilità) all'interno di Back Office.

![image2](https://github.com/user-attachments/assets/0a991441-cc14-4aff-aff3-a7e30ba04846)


- **BUDGET VS CONSUNTIVO**

Questo è quello che si vuole ottenere, ovvero un confronto tra il Budget
"**valore budget e l’andamento azienda reale "**valore consuntivo**". Vedere
esempio qui sotto :

![image3](https://github.com/user-attachments/assets/e5b494f3-8a29-48e3-a2f5-7d1d254b3e7e)


Come prima cosa, selezionare l'azienda e premere su carica per poter
vedere la situazione finanziaria dell'azienda. Nelle colonne
**budget** e **consuntivo** possiamo veder l'andamento
dell'azienda.

**1.**

È possibile verificare la situazione mese per mese, ma è previsto anche
di poter verificare per anno, per un quarto di anno, per mezzo anno.
Bisogna dunque premere sui drop down menu:

- **Azienda:** qui si sceglie la società di riferimento della situazione
  finanziaria. Premere sul triangolo del drop down menu e selezionare
  con tasti SX del mouse l’Azienda.

![image4](https://github.com/user-attachments/assets/aeddba94-9c57-4a48-a3f2-bcc2c8eab5e9)


- **Anno:** scegliere l’anno di riferimento della situazione finanziaria
  da analizzare. Utilizzare le freccette a scorrimento per indicare
  l’anno da analizzare

![image5](https://github.com/user-attachments/assets/8469996e-7d92-4c9f-ab28-016f3147d55a)


- **Mese:** scegliere il mese o i mesi di riferimento della situazione
  finanziaria da analizzare. Utilizzare il triangolo del drop down menu
  e settare i check nel riquadro accanto ai mesi che si desiderano
  analizzare

![image6](https://github.com/user-attachments/assets/29ae206a-8004-4b59-9989-fea11499baa0)


Dopo aver definito il range di data (anno e mese \i) e l’azienda,
premere sull’icona definita da una "**freccia verde**" per caricare i dati
della situazione finanziaria dell’azienda.

![image7](https://github.com/user-attachments/assets/7216af01-f7e4-4e7e-89d8-0b9e10a9c9b8)


- **COMPOSIZIONE DEL REPORT BUDGET VS CONSUNTIVO:**

**2.**

La schermata del report è una pivot , ed è così suddivisa :

- Nella parte **sinistra** abbiamo le colonne su cui vengono elaborati i
  dati e sono

![image8](https://github.com/user-attachments/assets/31f4ee45-32db-4545-b021-3f62fc009372)

1)  **Mese:** Avendo selezionato da Gennaio a Marzo, vengono
    rappresentati con i numeri di riferimento 1, 2,3 (ovvero i primi tre
    mesi dell’anno). Premendo sulla freccetta nera prima del numero di
    ogni mese andremo ad esporre la situazione finanziaria aziendale dei
    vari centri di costo (che possono essere negozi , logistiche o Sede)
    suddivisa su 3 livelli di conti "**Mastro, Conto, Sottoconto**"

2)  **Centri di costo**: Tutto ciò che per il cliente può essere
    un **costo** o, un **ricavo**, può essere definito con
    un **centro di costo** sul quale andare a fare movimenti contabili.
    I centri di costo attualmente sono di 3 Tipi:

- Logistica: (Magazzini per uscita ed entrata
merce)

- Pv: (Negozi sia costo che ricavo)

- Sede: Reparti aziendali, ad esempio il
Marketing o risorse umane)

![image9](https://github.com/user-attachments/assets/ee1d2e8e-98af-4694-a9ec-987b6ce81b35)


3)  I conti vengono definiti dal cliente premendo sul bottone "Piano
    Conti". I conti sono di 3 gerarchie.

- Conto Mastro

- Conto

- Sottoconto

Poniamo il caso di voler vedere i dati inerenti alle 3 gerarchie di
conto , per quanto riguarda il centro di costo di tipo "**Pv**" (negozio)
Trieste:



**A.**

- Muoversi col mouse sull’ intestazione del "**Centro di costo**". Apparirà
  una piccola icona che indica il filtro dati. Premere il tasto sx del
  mouse.

![image10](https://github.com/user-attachments/assets/e1233bf0-80a4-4104-a47b-afa91a18025f)


**B.**

- Si aprirà una finestra di selezione. Mettere il check sul \ sui
  negozio \ i per cui si desidera visualizzare i dati.

![image11](https://github.com/user-attachments/assets/ea6bdde7-be34-41ac-8087-24fa7d895334)

**C.**

- Premere poi sulla freccia nera accanto a negozio Trieste nella colonna
  "****Centro di Costo****" per visualizzare i dati del "****Conto Mastro****",
  e successivamente sulla freccia accanto al nominativo nella colonna
  "****Conto Mastro****" per viualizzare i dati nella colonna "****Conto****" ed
  espandere ulteriormente premendo sulla freccia accanto al \\ i
  nominativi sotto la colonna "****Conto****" per visualizzare i record
  nella terza gerarchia di conti "****Sottoconto****"


![image12](https://github.com/user-attachments/assets/60f82e26-e19d-47a3-900e-5cd5b270ac5e)

**D.**

- Nella parte **destra** abbiamo le colonne su cui vengono mostrati e
  messi a confronto i valori



Ad esempio, possiamo osservare i dati relativi al **Conto Mastro "**Costi
Generali**"** per il negozio di Trieste , il quale espandendolo, mostrerà
5 **conti** nella colonna de **Conto** , ognuno di essi che a sua volta
espandendolo mostrerà i relativi "**Sottoconti**" . Prendendo in esame il
Conto "**Altri costi superficie**" , si noterà che al suo interno nella
colonna "**Sottoconti**" ci sono ulteriori 5 voci. Ogni voce avrà poi nella
parte di destra un valore di tipo (una previsione) **Budget** ed un
valore (andamento reale) **consuntivo** ed un valore **%** che potrà
essere in negativo o positivo a seconda del confronto tra il Budget e il
consuntivo. Questo esempio , indica l’adamento aziendale per i
Sottoconti appartenenti al Conto "**Altri Costi Superfici**" del Conto
Mastro "**Costi Generali.

![image15](https://github.com/user-attachments/assets/a70d7994-f14d-424e-ba88-a032cdfa42a7)


- **INSERIMENTO DEI DATI**

In questo capitolo verrà affrontata dunque la parte per la preparazione
dei dati, ovvero come e dove vengono prelevati i dati che compongono il
report.

**1.**

**I JOB** : I record vengono caricati all'interno degli aggregati
di dati, tramite 2 JOB di sql "un job importa da IPOS , il secondo
"importa da contabilità generale"

![image16](https://github.com/user-attachments/assets/34383fe7-5e3e-4499-84ef-42bbe635dafe)


**COAN - import dati da Coge** (importa i dati dal software ERP scelto
dal cliente , in questo caso ad hoc revolution)

**COAN - Import costo del venduto da IPOS** (qui vengono importati i
dati del mastro conto del "costo venduto" , ma anche i ricavi. I costi
saranno rappresentati in colonna "valore consuntivo" con il simbolo del
"-" davanti al valore)

**2.**

**IMPORT BUDGET**: Serve per importare i movimenti contabili che
l'azienda ha previsto in riferimento magari ai valori dell'anno
precedente. Premere dunque sul pulsante "import budget", si aprirà una
finestra ove bisognerà selezionare tutte le voci:

![image17](https://github.com/user-attachments/assets/0fc36227-6b1d-4a10-a147-ace163f8f230)

Bisognerà dunque selezionare un film template da importare, premendo
sull’Icona Open

![image18](https://github.com/user-attachments/assets/671e0583-52b4-41d1-a6f3-f49a0e6de2e3)

Selezionare dunque il file template da importare

![image19](https://github.com/user-attachments/assets/9aba0652-5911-4204-b8a0-8079e0f5a9ca)


Dopo aver selezionato il file da importare, ecco il risultato (premere
su generate per importare i dati del Budget) :

![image20](https://github.com/user-attachments/assets/5fcc17aa-4c8b-451b-9999-0654ac5eb7c6)


**3.**

**CENTRI DI COSTO**:
il centro di costo (cdc) è uno strumento utilizzato per attribuire costi
o ricavi a gruppi omogenei di attività aziendali, che possono
rappresentare un qualsiasi oggetto di analisi: ad esempio un negozio o
magazzino o un reparto aziendale, un prodotto o una linea di prodotto,
un processo produttivo o una loro combinazione.

![image21](https://github.com/user-attachments/assets/91151752-74c6-4d35-b000-d6753c1ca86b)

I centri di costo attualmente sono di 3 Tipi:

![image22](https://github.com/user-attachments/assets/7ca42b15-f6ea-4e06-bf12-dafc6b7c03c3)

Se premiamo sulla freccia nera accanto alla tipologia di centro di costo
, vedremo l’elenco dei centri di costo appartenente alla categoria:

![image23](https://github.com/user-attachments/assets/78771365-2ff9-4756-8d49-a610af942656)

Premere sull’icona definita dal simbolo "**+**" per aggiungere un nuovo
centro di costo. Si aprirà una finestra dove bisognerà inserire i dati
del nuovo centro di costo. Premere sul floppy disk per salvare il nuovo
centro.

![image24](https://github.com/user-attachments/assets/40de6993-2ee4-40c7-b9cf-c32395704345)


Per modificare un centro di costo, selezionarlo e premere sull’icona
definita dal "**blocco note**". Si aprirà la finestra dove si potrà
modificare le voci al suo interno(ad esempio il **nome**). Per salvare
le modifiche premere sull’icona definita dal floppy disk.

![image25](https://github.com/user-attachments/assets/7f5b5b7a-a757-4545-a126-916b61d11e66)


Per eliminare un centro di costo , selezionare la riga che si desidera
eliminare e premere sull’icona definita dalla "**X rossa**". Premere poi
sull’icona definta dal floppy disk per salvare.

![image26](https://github.com/user-attachments/assets/8677818f-c6ca-4cdc-b655-eaae75570093)

**4.**

**IL PIANO DEI CONTI**: I conti vengono definiti dal cliente
premendo sul bottone "Piano Conti". I conti sono di 3 gerarchie

- Conto Mastro

- Conto

- Sottoconto

**Mastri, conti e sottoconti**

La struttura del piano dei conti è cosiddetta **multilivello** senza
limiti al numero di livelli utilizzabili. E' costituita fondamentalmente
da tre elementi:

• **Mastri**: sono i conti di primo livello che **danno inizio alla
struttura del piano dei conti**;  
  
• **Conti**: sono collegabili gerarchicamente tra di loro a partire da
un mastro e **costituiscono la struttura del piano dei conti**;  
  
• **Sottoconti**: sono collegati ai conti e sono gli **elementi su cui
effettuare le registrazioni contabili**.

Un piano dei conti sarà pertanto formato da N livelli con i **mastri al
primo livello**, i **conti in mezzo **e i **sottoconti
all'ultimo**. Ogni azienda ha un proprio piano dei conti, caratterizzato
dalla sua struttura, all'attività svolta, dalle informazioni che si vuol
evidenziare nella contabilità. Nel piano dei conti ogni conto viene
indicato con un **codice** che ne facilita la classificazione.

**I Mastri:**

Rappresentano la **categorizzazione base** della struttura del piano dei
conti, i valori possibili sono:  
  
- Stato patrimoniale attività;  
- Stato patrimoniale passività;  
- Conto economico costi;  
- Conto economico ricavi;  
- Conti d'ordine;  
  
**I conti:**

Questo campo deve indicare il conto di livello **immediatamente
superiore**, per un conto di secondo livello sarà indicato
un **mastro**.  
  
**I sottoconti:**

I sottoconti vanno inseriti nel **piano dei conti**, che a sua volta può
essere suddiviso in diversi livelli di aggregazione/classificazione, ad
esempio i sottoconti possono essere raggruppati sotto conti detti
"di **mastro**"; potendo arrivare sino a una struttura a 4
livelli: **Gruppi, Mastri, Conti, Sottoconti**.

Premere dunque sul pulsante "**PIANO CONTI**" per apire la schermata di
inserimento dei **CONTI**

![image27](https://github.com/user-attachments/assets/b293c5f6-3a16-439a-9684-f2917b6e18ef)


![image28](https://github.com/user-attachments/assets/10fa6c35-5a9f-4435-8d8f-f788f02be583)


Se premiamo sulla freccia nera accanto ad un conto, esso verrà espanso
mostrando i Conti associati.

![image29](https://github.com/user-attachments/assets/3a682a43-b43c-4dea-9646-5088578266ed)

Successivamente, premendo sulle frecce nere accanto ai conti, esere
verranno espanse e mostreranno i sottoconti associati. Sulla destra
della schermata avremo invece le indicazioni se il conto è un costo
"**Segno -1**" o un Ricavo "**Segno 1**" e a che livello esso appartiene
"**M=Mastro**" , "**A=Conto**" , "**S=Sottoconto**"

![image30](https://github.com/user-attachments/assets/474def71-e643-4337-8052-0e09ea567bb7)


Per aggiungere un nuovo Conto Mastro e definirne i conti e sottoconti
associati, premere sull’icona definita dal simbolo "**+**" . Si aprirà una
finestra ove sarà necessario compilarne i campi per la creazione del
Conto Mastro. Salvare poi premendo sull’icona definita dal floppy disk.

![image31](https://github.com/user-attachments/assets/228fd072-b9fa-4d28-b08f-97681a21a84c)


Per aggiungere poi i "****Conti****" ed i "****Sottoconti****", bisognerà
ripetere l’operazione di creazione di un nuovo conto, settando nella
cella "**Conto Padre**" il livello superiore di appartenenza. Premere
successivamente sull’icona definita dal Floppy Disk per salvare.

CONTI
![image32](https://github.com/user-attachments/assets/66612835-7df6-4126-8b3e-593dd26f4314)

SOTTOCONTI

![image33](https://github.com/user-attachments/assets/f972d7fa-2e78-4a9c-9895-197a914538e5)


- **PIANO CONTI:**

![image34](https://github.com/user-attachments/assets/038c79b6-c05d-425a-9585-7c03937fd9fb)


Per Modificare un conto avvalersi dell’icona definita dal "**Blocco Note**".
SI aprirà la finestra del conto, ove si potrà modificare la o le voci
desiderati (per esempio cambiare il segno). Premere successivamente
sull’icona definita dal "**floppy disk**" per salvare

![image35](https://github.com/user-attachments/assets/253eb930-8292-4d84-81f9-e1264e52d0dc)


Per eliminare un conto, selezionare il conto e premere il tasto definito
dalla X rossa. Premere successivamente sull’icona definita dal Floppy
Disk per salvare.

![image36](https://github.com/user-attachments/assets/52c3b606-298b-4cde-a523-f1efb48bb8c5)

**5.** 

- **MOVIMENTO CONTABILE:**
Un movimento contabile sono dei movimenti associati ad un conto è dunque
composto


- Centro di costo

- Sottoconto

- Mese

Se si deve dunque, inserire il movimento del costo del personale, si
andrà ad inserirlo con il livello più basso (quindi dettagliato)
possibile "Centro di Costo e Sottoconto".

Premere dunque sul pulsante "**Movimenti Contabili**" per aprire l’elenco
dei movimenti o, inserirne uno manualmente

![image37](https://github.com/user-attachments/assets/048e1102-b23b-44a9-b080-c6f4fdd544b1)

![image38](https://github.com/user-attachments/assets/fcb14fbb-a129-48b5-9188-4fa557d9d545)

Per espandere i movimenti di gennaio, premere sulla freccia nera accanto
alla voce sotto la colonna "**Centro di Conto**". Verranno mostrati tutti i
movimenti contabili legati alle 3 gerarchi di "**Conto**"

![image39](https://github.com/user-attachments/assets/47d30e41-c8b6-42c4-af92-fb19bf708802)


Qualora volessimo filtrare per un singolo centro di costo , si devono
utilizzare i filtri nelle celle sotto le intestazioni: Ad esempio se si
desidera vedere i movimenti contabili del centro di costo del negozio di
Bologna, basterà filtrare per il centro di costo ed il conto Mastro che
ci interessa:

![image40](https://github.com/user-attachments/assets/a8ddbb74-41a2-4171-ad64-289ce8d86803)

Queste elencate, sono vendite di IPOS ma che in realtà non arrivano da
IPOS ma bensì dalla contabilità generale, in quanto IPOS esporta i
corrispettivi alla contabilità generale, (in contabilità, potrebbero
avvenire anche delle modifiche) e poi Il modulo di contabilità analitica
tramite un processo di importazione va ad importarle in IPOS.I tipi di
movimento contabile o "fonti dati" attualmente sono 3

- CCG: ovvero dati recuperati dalla contabilità Generale

- BDG: Movimenti di tipo budget inseriti quando si va a fare la
previsione ad inizio anno

- WMS (ovvero sistema di cassa)

È possibile inserire due tipi di movimenti contabili, quelli di tipo CCG
e BDG. Premere sull’icona definita dal "**simbolo +**" e inserire i dati
all’interno della finestra che si aprirà. Premere successivamente
sull’icona definita dal floppy disk per salvare il movimento contabile

![image41](https://github.com/user-attachments/assets/928b2293-c792-4f61-9dc9-d1da37bdbb9f)


L’altro metodo che importa dati "**Il processo di importazione**", deve
essere sviluppato su misura per il cliente in quanto ogni cliente
potrebbe avere un software diverso per la contabilità generale il quale
non sempre si appoggia ad un database sql.

>**Nota:** Se un movimento ha il campo InternalKey popolato
>(Internal key rappresenta L'ID del movimento), non può essere modificato
>(questi movimenti sono importati da altre fonti ad esempio contabilità
>generale). Solitamente i tipi movimento Budget possono essere
>modificati, facendo doppio click sx del mouse e, possono essere aggiunti
>manualmente premendo sull'icona definita dal "simbolo più" (aggiungi).
>Si aprirà una finestra per la modifica, dove sarà necessario compilare
>tutti i campi e successivamente premere sull' icona del floppy disk per
>salvare il movimento.

Per eliminare un movimento contabile, selezionare la riga del movimento
e premere sull’icona definita dalla "**X rossa**".

![image42](https://github.com/user-attachments/assets/e99267f8-cab5-4e5b-9ecf-6f55756f105d)


- **REPORT**

I dati possono essere rappresentati anche in modo più statico
dall'utente. Il report estrae i dati del valore budget vs valore
consuntivo a partire dal livello più alto di conto "Conto Mastro".
Selezionare il layout del report e premere sul pulsante definito dalla**"
freccia verde**" per caricare i dati

![image43](https://github.com/user-attachments/assets/95a8c931-f8bc-41c2-a0b8-1491fd7ca159)


**CREARE UN NUOVO LAYOUT:** E’ stato messo a disposizione dei
clienti anche la possibilità di editare \ importare dei nuovi layout
per il report.

![image44](https://github.com/user-attachments/assets/25e5f3ef-1cad-43e1-84e5-5d709693a0fd)


**Subtotals Editor**:
Permette all’utente di poter inserire delle vere e proprie formule
matematiche da poter poi inserire all’interno dell’editor del Report.

![image45](https://github.com/user-attachments/assets/08ea99e7-2263-4e67-880d-ab5fcd339937)

Premere dunque sull’icona definita dal "**simbolo +**" per inserire una
nuova formula nell’elenco. Bisognerà compilare tutti i campi.

**Codice:** Sarà il codice di riferimento della formula
nell’editor dei report

**Nome:** Nome della formula

**Formula:** contiene il codice della formula

![image46](https://github.com/user-attachments/assets/39660b51-3bd9-4191-ab3d-7d5dd1e5f016)

Premere poi sull’icona definita dal floppy disk per salvare la formula e
vederla apparire in elenco 

![image47](https://github.com/user-attachments/assets/3ffef918-18e1-402a-9c43-b255d0402547)

Per modificare la formula, fare doppio click del tasto sx sulla riga della formula, si aprirà
nuovamente la finestra di inserimento dati per apportare le modifiche
desiderate (**ex: il nome della formula o il codice**)

![image48](https://github.com/user-attachments/assets/f3ac448e-4fb9-42c9-8a5d-d46388c9a148)

Premere sull’ icona definita dal floppy disk per salvare la modifica.

![image49](https://github.com/user-attachments/assets/f9a7b9bb-1cd8-4995-84f7-594601460b9c)


Premere sull’icona definita dalla "**X rossa**" per eliminare la formula.
Premere successivamente sull’icona definita dal floppy disk pe salvare

![image50](https://github.com/user-attachments/assets/b22be9b6-0bed-4838-8631-a5e3088300da)

**REPORT EDITOR:** Permette all’utente di poter inserire dei
nuovi layout per i report.

![image51](https://github.com/user-attachments/assets/e2b6380c-b311-4029-b7d9-4730bbe4ee1c)

Premere sul tasto definito dal "**simbolo +**" per aprire l’editor. Premere
nuovamente sul simbolo "**+**" per aggiungere le righe di cui è composto il
report. Compilare dunque la colonna Conto se si tratta di una riga non
di calcolo, mentre se si tratta di una riga di calcolo, compilare anche
la colonna subtotale per la scelta della formula. Premere poi sull’icona
definita dal floppy disk per salvare il nuovo layout.

![image52](https://github.com/user-attachments/assets/172e9cdb-4a6e-438b-9a98-a10d418e0404)
