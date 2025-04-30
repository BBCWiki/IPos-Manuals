---
layout: home
title: Riordino
parent: Ordini e Riassortimento
grand_parent: BackOffice Negozio
nav_order: 5
---

# ***RIORDINO:***

Esiste un altro metodo per effettuare un ordine della merce se il
cliente non vuole utilizzare il riassortimento tramite la creazione
delle “Scorte minime” (vedere documento Scorte minime) , ovvero
effettuare un ordine della merce in base alle vendite emesse.

Questa operazione la si può fare sia dal negozio che direttamente dalla
sede per i propri negozi.

>**NOTA:** gli ordini che verranno generati, anch’essi dovranno
>essere successivamente approvati dalla sede (vedere documento
>Approvazioni Ordini Pv) ed una volta approvati, appariranno anche loro
>nel modulo “**Ordini Fornitore**” (Vedere documento Ordini Fornitore)

- **RIORDINO TOTALE PRODOTTI**

Per effettuare dunque un ordine tramite le vendite emesse, bisognerà
entrare nel menu “**Ordini & riassortimento**” ed aprire il
modulo “**Riordino**”. Una volta aperto il modulo:

- selezionare un range di data

- lasciare la voce “**prodotti movimentati**” (in questo modo andrà ad
  effettuare calcoli sui movimenti \\ vendite dei prodotti)

- Per quanto riguarda i prodotti, non premere sul pulsante prodotti (in
  questo modo si effettuerà il riordino per tutta l’anagrafica che ha
  subito movimentazioni \\ vendite

Dopo aver selezionato il range di data, premere sull’icona definita
dalla “freccia verde” per caricare gli articoli

![image1](https://github.com/user-attachments/assets/185c3c06-5c8f-42d9-a8cd-fdcff927551e)
![image2](https://github.com/user-attachments/assets/18a74170-33c9-4bb0-83a9-ad4ce51bf6b3)


Nella schermata verranno mostrati tutti gli articoli che hanno subito un
movimento nel periodo selezionato e, in particolare nella colonna
“**verde**” **SELL OUT,** viene mostrato in che quantità sono stati
venduti. IPOS non propone nulla nella colonna “**azzurra**”
**ORDINE,** in quanto si dovrà decidere in che modo compilarlo:

**1.**

- **Manualmente:** Andando a compilare a mano il campo della
  colonna **ORDINE**

![image3](https://github.com/user-attachments/assets/52167943-0d09-4c12-8d8c-bd1cb6c2130c)


**2.**

- **Ordine=Vendite:** Si andrà a settare il valore nella cella
  verde “**Sell Out**” (quindi del venduto) all’interno della cella azzurra
  “ordine”. Per farlo selezionare le righe interessate in questi modi:


1)  Selezionare il primo articolo, tenere premuto sulla tastiera il
    tasto in basso a sinistra “**CTRL**” e premere (mantenendo premuto
    il tasto **CTRL**) il tasto “**A**” 🡪 **CTRL+A**

![image4](https://github.com/user-attachments/assets/9afd16f7-90a5-4777-b550-304d405b216b)

![image5](https://github.com/user-attachments/assets/6da811e8-f595-4de8-a01b-961499c6a6c5)


2)  Selezionare il primo articolo, tenere premuto sulla tastiera il tasto in basso a
    sinistra “**SHIFT**” e premere (mantenendo premuto il tasto
    **SHIFT**) il tasto “**SINISTRO**” del mouse sino alla riga
    desiderata 🡪 **SHIFT+Tasto SX**

![image6](https://github.com/user-attachments/assets/24768d38-7528-4817-8f05-4d982c6f2246)
![image8](https://github.com/user-attachments/assets/6b8cb7e0-2cd5-4cde-b8c9-c59b35e438b7) 
![image7](https://github.com/user-attachments/assets/bfbc80d9-aa07-41d5-8f73-6113a87dd6de)



3)  Selezionare il primo articolo, tenere premuto sulla tastiera il tasto in basso a sinistra
    “**CTRL**” e premere (mantenendo premuto il tasto **CTRL**) il tasto
    “**SINISTRO**” del mouse le righe desiderate 🡪 **CTRL+Tasto SX**

![image9](https://github.com/user-attachments/assets/069b25b9-628e-4292-97f5-1f76938cb565)

![image10](https://github.com/user-attachments/assets/bdbd064f-909c-44db-9451-191b0b230cba)


**3.**

- **MODIFICA COPERTURA:** Effettuerà un riordino della merce
  controllando nella colonna stock la merce che non ha stock e per esse,
  aggiunge un valore di copertura (lo stesso che riscontra nella colonna
  stock) nella colonna “**Ordine**”. Per quanto riguarda invece gli articoli
  con stock positivo non verrà settato alcun valore nella colonna
  “**Ordine**”. (La selezione degli articoli è la stessa dei tre metodi
  descritti al punto 2)

![image11](https://github.com/user-attachments/assets/cba1cc2a-c571-4390-89b9-6554a90d23be)


**4.**

- **ADEGUA QUANTITA’
  ORDINE:** Qualora si vorrà ulteriormente adeguare la quantità da
  ordinare in base allo stock, basterà incrementare la % all’interno di
  questa cella ed IPOS incrementerà la qta da ordinare in base al numero
  % settato (**solo per merce con stock in negativo e che ha subito già
  una Modifica copertura**) per i prodotti con stock negativo.

![image12](https://github.com/user-attachments/assets/303a6aa4-6d01-424d-b9fa-da620b978818)


**5.**

- **IMPOSTA QUANTITA’
  ORDINE:** Con questo metodo, IPOS setterà una quantità di riordino
  scelta dall’utente, non tenendo conto della né della qta venduta
  **sellout**, né dello **stock** in negativo

![image13](https://github.com/user-attachments/assets/749134ef-e756-4425-a1e5-a1005785fa6a)



## **CREAZIONE ORDINI**

- **CONFERMA ORDINI:**

**1.**

Dopo aver ultimato di
compilare la quantità da ordinare, possiamo confermare l’ordine premendo
sull’apposita icona definita dalla “**CHECK VERDE**”

![image14](https://github.com/user-attachments/assets/c2b766a6-88c2-4636-9a11-1943705b0d09)

L’ordine verrà generato in **ORDINI PV EMESSI** (vedere documento ordini PV
EMESSI)

![image15](https://github.com/user-attachments/assets/d4209ce2-cdb4-43bc-bfec-8aa189e24649)


**2.**

**GENERAZIONE ORDINI:**

Premendo sull’apposita icona definita da un “**blocco note con il check
rosso**” , IPOS mostrerà direttamente gli ordini fornitori che si
andranno a creare

![image16](https://github.com/user-attachments/assets/892f046e-6825-426e-8ae6-e40ee5075028)


Ecco gli ordini appena generati in “Ordini Fornitori”

![image17](https://github.com/user-attachments/assets/8a481f9b-a837-4a3d-9abf-fa9b3f6e3870)


Successivamente dalla Sede, bisognerà effettuare ### l’APPROVAZIONE ORDINE.
(**Vedere documento Approvazione Ordini**)

![image18](https://github.com/user-attachments/assets/34ccfc41-3f02-4bfe-847f-cf2eaedf4b30)

