---
layout: home
title: Pianficazione Stagione
parent: Ordini e Riassortimento
grand_parent: BackOffice Sede
nav_order: 8
---
# **PIANIFICAZIONE STAGIONE:**

- **INTRO:**

Pianificazione Stagione, viene utilizzata per pianificare gli acquisti
della nuova Stagione. Il sistema di pianificazione si basa sulla domanda
prevista ed effettiva da parte dei clienti, ad esempio la previsione e
gli ordini di vendita. Un altro obiettivo del sistema di pianificazione
consiste nel garantire che il magazzino non aumenti in modo superfluo.

**1.**

**CREAZIONE NUOVA PIANIFICAZIONE:**

Prima di passare alla
creazione di una pianificazione stagione, sarà necessario creare degli
**store cluster** di tipo “**Store Capacity**” per indicare i negozi che
partecipano alla **pianificazione stagione** e su cui si andrà a creare
la pianificazione. Bisognerà dunque entrare in “Anagrafiche” (vedere
documento Anagrafiche) e selezionare il modulo **“Store Cluster”**, per
creare i cluster ed inserire i negozi che ve ne faranno parte.

![image1](https://github.com/user-attachments/assets/8b9bf5e7-cf0c-46de-903f-82364b6c6fd6)

Aperto il modulo “**Store Cluster**”, si dovrà premere sull’icona
definita dal “**simbolo più**” per creare un nuovo “**Store Cluster**”.
Verrà aggiunta una nuova riga in basso nell’elenco che si dovrà
compilare in tutti i campi e scegliendo la categoria di cluster “**Store
Capacity**”. Salvare avvalendosi dell’apposita icona a forma di
“**floppy disk**”

![image2](https://github.com/user-attachments/assets/884f1166-e32c-4d17-94f9-0695a566f665)

Successivamente, selezionare lo “**store cluster**” creato e premere
sull’icona definita dal “**blocco note**” per inserire i negozi
appartenenti al cluster. Apparirà una finestra per la selezione dei
negozi da inserire nello “**store cluster**”; selezionare i negozi e
premere sul tasto ok per vederli apparire a destra della schermata.
Premere sull’icona definita dal “**floppy disk**” per salvare lo
“**store cluster**”.

![image3](https://github.com/user-attachments/assets/41167ba1-4098-4af6-b904-df13097ab55e)


Per aprire “**Pianificazione Stagione**”, loggarsi al “Back Office” di
Ipos, premere sul menù “**Ordini & Riassortimento**” e premere sulla
voce “**Pianificazione Stagione**”.
Una volta cliccato sulla voce “**Pianificazione Stagione**”, la
schermata si presenterà in questo modo:

![image4](https://github.com/user-attachments/assets/2669796f-68cb-4c6c-ac5f-c1ee02842179)

Selezionare la stagione che vogliamo pianificare, nel nostro caso **la Pe2022**

![image5](https://github.com/user-attachments/assets/27af6fd5-fef1-46dd-97d2-90c17a2df7d7)

È possibile effettuare un confronto con le stagioni precedenti, da cui
partire per effettuare la Pianificazione Stagione. Per farlo, settare il
flag “**Abilita comparazione Stagione Rif**.” e selezionare una
“**Stagione d Riferimento**” ad esempio PE2021.

![image6](https://github.com/user-attachments/assets/83f50d26-1afb-4426-bec9-350a0a845c90)

Premere sull’apposita Icona definita da una “**freccia verde**” per
caricare i dati della stagione precedente da cui partire per effettuare
la “**Pianificazione della stagione**”

>**NOTA:** Le stagioni sono precaricate all'interno del db di ipos
>nella tabella **seasons** e la tipologia delle stagioni in
>**seasonality**. Ogni stagione ha ben 3 tipologie "**Primavera-Estate,
>Autunno-Inverno e CONTINUATIVO**".

**LA SCHERMATA:**

**2.**

La schermata apparirà suddivisa in 3 parti ed i dati saranno raggruppati
per famiglia, sottofamiglia e cluster negozi. I Cluster negozi
(precedentemente configurati nel modulo **Stores Cluster**) possono
essere creati a proprio piacimento, per esempio si potrebbero creare in
questo modo “**Negozi Piccoli, Medi e Grandi**” ma, si potrà avere anche
un **singolo Negozio per Cluster**.

Di seguito come appare la schermata di “**Pianificazione Stagione**” dopo aver inserito i dati con
cui vogliamo lavorare:

![image7](https://github.com/user-attachments/assets/337eadf8-c7bd-43a6-8915-e122ce009941)

>**NOTA:** Come per ogni schermata di IPOS è possibile spostare le
>colonne ed aggiungere e togliere le colonne per cambiare il layout.

- **Le colonne:** La schermata di pianificazione della Stagione,
  è composta da quattro parti:

- La parte a sinistra, rappresenta le anagrafiche dei prodotti ,
  famiglie e dei negozi per la quale si dovrà compilare la
  Pianificazione della stagione

![image8](https://github.com/user-attachments/assets/b6bf0a0f-c231-458f-8ca0-64c321956773)


![image10](https://github.com/user-attachments/assets/13bacb24-9929-4ec5-973f-4f5d832e5dfc) In questa colonna andrò a scegliere la Categoria di Prodotti (I Reparti) per la Pianificazione


In **Sottofamiglia** (Funzioni), andremo a scegliere la tipologia di prodotti per la pianificazione

![image9](https://github.com/user-attachments/assets/44f19ae4-8837-48d4-a874-f22c30e64011)


![image11](https://github.com/user-attachments/assets/cc692277-25db-41e6-9ff3-72b056cb6ac2) In questa colonna troverò i Cluster di appartenenza dei Negozi su cui i
dati della **Pianificazione** saranno raggruppati

- **La prima parte di celle:** rappresentano la parte che si dovrà compilare per la
  pianificazione. In questa maschera si definisce il numero di modelli,
  la quantità di acquisto, i costi ed i prezzi per ogni famiglia e
  sottofamiglia che si vuole comprare per ogni tipologia di negozio
  (Cluster).
  
![image12](https://github.com/user-attachments/assets/3b864e1f-1704-45fa-ad2f-909879fd7c26)

- **In giallo alla destra**: ci sono i dati della stagione di riferimento scelta per il confronto.
  Bisognerà tener conto dunque per la **pianificazione attuale,**
  della “Storia” della stagione di riferimento scelta. Questo perché è
  importante sapere se l'anno scorso con la stessa stagione si sono
  comprati 10000 pezzi ma ne sono stati venduti solo 5000 pezzi. In
  questo caso, magari nella pianificazione stagione di quest'anno si
  ridurranno un po’ gli acquisti.
  
![image13](https://github.com/user-attachments/assets/fd9c06b7-9b6f-4089-b220-dbc535e56e63)

>**NOTA:** Dunque questo confronto che vediamo a destra con le
>colonne in giallo “che sono i dati della stessa stagione ma dell'anno
>della **stagione di riferimento”**, aiutano a capire quale
>quantità per gli acquisti impostare per la **Pianificazione
>Attuale.**

**COMPILAZIONE NUOVA PIANIFICAZIONE:**

**3.**

In sostanza, i dati della stagione di riferimento nelle colonne in
giallo, possono essere utilizzati come punto di riferimento per capire
quale quantità impostare per la nuova Pianificazione della Stagione.

Per iniziare la pianificazione sulle colonne a sinistra abbiamo due
possibilità:

-   O inserisco direttamente nella colonna Azzurra **“Capacità Pv”**
    (ovvero la capacità per ogni Negozio appartenente al Cluster) la
    quantità totale della somma degli articoli per le referenze che
    appartengono alla sottofamiglia di cui si sta pianificando la
    stagione.

In questo caso, impostando 125 qta nella colonna azzurra Capacità pv, il sistema IPOS farà un confronto
con la quantità di riferimento presente nella cella gialla **Qtà SellIn
Rif**., e con la **colonna % SellOut Rif.**, e andrà ad inserire qualora
vi fosse una maggiorazione di quantità,il valore % della maggiorazione
nella cella **Magg. SellOut Rif**.

![image14](https://github.com/user-attachments/assets/8c2d3653-95e5-4976-896a-c388436c6f6a)

Inoltre, settando i valori nelle colonne **“Costo”** e **“Prezzo
Vendita I.I.”**, il sistema effettuerà un confronto con le colonne in
giallo **“Costo Rif.”**, **“Valore Sell in \Out Rif.”** e **“Margin
Rif.”** e calcolerà un valore % nella colonna **“Margine %”**

![image15](https://github.com/user-attachments/assets/d32b5a98-c791-4640-9900-3a85b509e835)

-  Oppure, si può direttamente inserire una % di Maggiorazione Sell Out Rif, per
   calcolare la “Capacità Pv” per la sottofamiglia che si sta
   Pianificando.

![image16](https://github.com/user-attachments/assets/f84938bd-e0bf-4901-ba15-c0065b17dba7)


 Tutto rimane invariato rispetto al punto 1) per quanto riguarda il
 calcolo del Margine. Ovvero, settando i valori nelle colonne
 **“Costo”** e **“Prezzo Vendita I.I.”**, il sistema effettuerà un
 confronto con le colonne in giallo **“Costo Rif.”**, **“Valore Sell in
 \Out Rif.”** e **“Margin Rif.”** e calcolerà un valore % nella colonna
 **“Margine %”**

>**NOTA:** Di seguito il significato di altre colonne:

- **NUMERO REFERENZE**: è il numero di **modelli** per quanto riguarda
  gli articoli di una sottofamiglia. Ad esempio, se per la famiglia dei
  “**Berretti**” si inserisce il numero 7, significa che si sta
  pianificando la stagione per 7 tipi diversi di Berretto (lana,
  Baseball, Basco, bombetta, cilindro ecc) e che dunque il valore della
  quantità nella colonna “Capacità Pv”, è la somma delle quantità di
  questi 7 modelli di berretto.

- **RICARICO**: è il guadagno rapportato sul costo. La % di ricarico è
  calcolata a partire dal Costo di acquisto, la cui formula è la
  seguente **“Ricarico di vendita (%) = \[(prezzo di vendita – costo di
  acquisto) / costo di acquisto\] x 100”**

**I TOTALI:**

**4.**

Dopo aver impostato i valori inerenti alla **quantità** degli articoli
ed ai loro **costi e prezzi di vendita**, si auto compileranno le
**colonne BLU** dei totali dei negozi appartenenti al cluster, ovvero i
**totali della Quantità Pianificata ed il totale degli Acquisti** di
tutti i negozi appartenenti al cluster. Nel caso d’esempio, ogni singolo
negozio rappresenta un cluster, per cui i totali in queste due celle
sono esattamente i totali di tutte le **quantità** e **del valore di
acquisto**, per ogni singolo negozio.

![image17](https://github.com/user-attachments/assets/ebada143-15eb-4a28-9c6b-8fe2d5225d54)

>**NOTA:** Il valore **totale degli acquisti** delle **celle BLU**, è
>riportato anche nella successiva tab **Budget per Pv**, la quale
>contiene la somma dei totali Acquisto di tutte le categorie, suddivisa
>per cluster (in questo caso essendo ogni negozio un cluster, sarà
>suddivisa per ogni singolo negozio). Il valore, si aggiornerà durante la
>compilazione della Pianificazione Stagione.
>
>![image18](https://github.com/user-attachments/assets/149d96b3-bfd5-4c00-851a-ad2b6acedfed)


Qualora si decidesse all’inizio della pianificazione, di settare un
Budget per Tutti i pv appartenenti ad un Cluster (nel caso di esempio,
essendo un negozio per Cluster, significherebbe settare un budget da non
superare per il negozio), basterà mettere la cifra desiderata
all’interno della cella “Budget Singolo Pv”(per ogni negozio
appartenente al Cluster, nel caso d’esempio 1) . Nella colonna
“**Stato**”, apparirà un numero %

- che sarà evidenziato di **ROSSO,** se durante la compilazione della
  pianificazione stagione, verrà superato il valore impostato nella
  cella “**Budget Tutti i PV**” dal valore presente nella cella dei
  “**totali Budget per categoria**” (questo valore si aggiorna durante
  la compilazione della pianificazione stagione ed è esattamente il
  valore riportato della cella dei totali BLU **“Totali acquisti IE
  tutti pv”**

![image19](https://github.com/user-attachments/assets/09b1f426-535e-468d-a3b3-a73d50364e11)


- che sarà evidenziato di **VERDE,** se durante la compilazione della
  pianificazione stagione, verrà mantenuto maggiore il valore impostato
  nella cella “**Budget Tutti i PV**” rispetto al valore presente nella
  cella dei “**totali Budget per categoria**” (questo valore si aggiorna
  durante la compilazione della pianificazione stagione ed è esattamente
  il valore riportato della cella dei totali BLU **“Totali acquisti IE
  tutti pv”**

![image20](https://github.com/user-attachments/assets/71e73ccd-79b1-4ca6-a6d7-ce2e29042a80)
