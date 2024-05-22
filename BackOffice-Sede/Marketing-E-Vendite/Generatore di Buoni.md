---
layout: home
title: Generatore di Buoni
parent: Marketing E Vendite
grand_parent: BackOffice Sede
nav_order: 3
---
# **GENERATORE DI BUONI:**

- **DESCRIZIONE DEI VOUCHER:**

All’Interno del menu “**Generatore di Buoni**” troveremo l’elenco dei “Circuiti” Gift Card \ Voucher \ Coupon che verranno in seguitoutilizzati nei negozi.

Dal 2021 L'Agenzia delle Entrate ha, con il rilascio delle specifiche tecniche del nuovo tracciato XML7 per lo Scontrino Elettronico, identificato la necessità di definire **due diversi metodi** per l'emissione di Buoni Corrispettivi e Gift Card/Tessere Prepagate. Ogni metodo implica una diversa liquidazione **dell'IVA**.

- **BUONO MONOUSO:** “Gift \ Voucher Economico”

Il Buono Monouso è un Buono Corrispettivo da emettere nel caso che:

- L'Aliquota IVA è nota (Un Buono Monouso è riferito ad una singola aliquota IVA e non può essere utilizzato in Documenti
  Commerciali non contenenti tale aliquota).

- L'esercente tratta un'unica aliquota IVA, o informa l'eventuale acquirente che il buono sarà valido per l'acquisto di un determinato insieme di beni e/o servizi aventi la medesima aliquota IVA.

Al fine della liquidazione IVA l'imposta viene pagata **all'EMISSIONE** del buono (tramite relativo Documento Commerciale),
mentre al momento del riscatto verrà richiesto di "stornare" il valore del buono dal totale del nuovo **Documento Commerciale** (tramite appositi comandi e formattazione che permettano di distinguere l'operazione da un abbuono).

- **BUONO MULTIUSO:** “Gift \\ Voucher Finanziario”

Il Buono Multiuso è da emettere invece nella seguente casistica:

- L'esercente tratta diverse aliquote IVA, e di conseguenza al momento dell'emissione del buono non è possibile sapere per quali aliquote verrà utilizzato.

Al fine della liquidazione, l'imposta è versata al **RISCATTO** del buono. Il Documento Commerciale riferito alla vendita del buono dovrà infatti essere emesso con aliquota **NON SOGGETTO IVA**, avendo funzione infatti solo di traccia del credito del cliente verso l'esercente, mentre il D.C. emesso al riscatto sarà un normalissimo scontrino con un totale completo come se non fosse stato utilizzato alcun buono, e l'importo riscattato dal buono indicato come sconto a pagare, che andrà a ridurre solo l'importo pagato dal cliente. Nonostante per alcuni protocolli sia inserito in automatico dal gestionale in fase di emissione scontrino, è buona norma indicare direttamente quale **TENDER \ PAGAMENTO** venga utilizzato dal Registratore Telematico per valorizzare lo sconto a pagare.

Per entrare nel modulo “Generatore Buoni”, premere sul menu “Marketing & vendite” definito dal numero “**1”** situato a sinistra della schermata del Back Office di IPOS, e scegliere il modulo “Generatore Buoni” accanto al numero **"2"**. 
In seguito verrà aperto l’elenco dei Circuiti “Voucher \ Gift” (definito dal numero “3”) creati.

![image1](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/eb9ad985-eee4-45a3-8d4a-084ef610648c)

- **CREAZIONE CIRCUITI VOUCHER \\ GIFT:**

In IPOS sono presenti ben 6 tipi differenti tra **“Voucher \ Gift \ Coupon”:**

**1.** - **Gift Card Economica:**

>Emissione con una **riga di vendita** sullo scontrino fiscale. Redenzione con una **riga di reso** sullo scontrino fiscale.
>Per abilitare la vendita di questa Gift Card in cassa, selezionare la voce in basso **\<Visibile in cassa\>.**
>**L'IVA** del prodotto selezionato verrà applicata in fase di **vendita e redenzione** della Gift Card.

**2.** - **Gift Card Finanziaria**:

> Emissione con uno **scontrino non fiscale**. Redenzione come **forma di pagamento** sullo scontrino di vendita, in >cassa. Utilizzando questa opzione **l'IVA** non verrà applicata quando la Gift viene emessa, ma **solamente in fase di >redenzione**.

**3.** - **Voucher Economico**:

> Redenzione con **una riga di reso** sullo scontrino fiscale.

**4.** - **Voucher Finanziario:**

> Redenzione come **forma di pagamento**. Non può essere venduto dall'operatore. Viene **emesso da promozioni** (oppure > > automaticamente dalla cassa nel caso dei **buoni di reso**)

**5.** - **Buono Attivazione:**

> Attiva una **promozione** quando inserito nel **carrello prodotti**.

**6.** - **Valore Sconto:**

> Offre uno **sconto a valore** (esempio: 5 EUR) sul **piede dello scontrino fiscale**.

**7.** - **Sconto Percentuale:**

> Offre uno **sconto percentuale** (esempio: 10%) sul **piede dello scontrino** fiscale.

## - **CREARE NUOVO VOUCHER \ GIFT:**

Per creare un nuovo circuito Voucher \ GIFT, selezionare l’apposita icona definita dal simbolo “+” per iniziare con la procedura di generazione nuovo Voucher \ Gift

![image3](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/a88dfd06-5bea-4c09-ad89-1c4f44a8b798)

Verrà aperta una schermata “Buoni” suddivisa in 3 TAB:


**A.** - **Creazione:** 
> Nella tab di creazione si andrà a definire oltre che l’anagrafica del circuito “Voucher \\ Gift”, anche la categoria (la > tipologia del voucher \ gift) e la meccanica di emissione.

**B.** - **Redenzione:** 
> Nella tab di redenzione si andrà a definire il periodo di validità entro il quale utilizzare il voucher \\ Gift, ove
> è possibile utilizzarlo ed il come poterlo utilizzare



**C.** - **Lista dei Buoni:** 
> Nella tab “Lista”, si potranno:
> - **Generare** i “voucher \\ gift” in base alle caratteristiche
> precedentemente adottate nelle altre tab; inserendo un valore e la
> quantità da generare “IMPORTANTE, mettere il flag su ATTIVO”
>
> - **Importare** i “voucher \ gift” da un file Excel direttamente all’interno del circuito creato

![image4](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/379da8e1-3fbc-4f30-9fc6-1f46b361f0d8)


- **CREAZIONE VOUCHER FINANZIARIO:**

**1.** Scegliere l’anagrafica del circuito che si desidera creare immettendo un Nome, un codice, un prefisso (cifre iniziali del circuito) ed il repository con cui vengono utilizzata (l’ambiente d’uso).

![image5](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/ac4c0a99-fbc6-4034-b952-5870ec00dec6)

**2.** Selezionare dunque la “**Categoria**”, ovvero il tipo di Voucher \ gift che ne determinerà il comportamento, attivando o disattivando le successive opzioni per la configurazione

![image6](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/7f2dbf6f-d25f-4a33-be1d-d330d47c6c0a)

**3.** Ad esempio scegliendo **“Voucher Finanziario”** attiveremo \ disattiveremo le seguenti opzioni.
In Grigio ciò che viene disabilitato. Dovremo selezionare un tipo pagamento (**DOCUMENTO ANAGRAFICHE**)
**IMPORTANTE ATTIVARE IL FLAG ABILITATO.**

![image7](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/3b042b21-192b-4b5b-b8a7-e55b367ec0ea)

**4.** Le opzioni definite al punto “4”, rimarranno inalterate e saranno tutte selezionabili.

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati una lista di Voucher \ gift, IPOS assegna il primo codice libero che trova in questo elenco.

- **CODICE ASSEGNATO DALL’OPERATORE**: Il commesso fornirà lui stesso al cliente un “Voucher \ gift” precedentemente generato, seguendo le direttive aziendali

![image8](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/79669eda-eb02-4bdd-8528-2bc9105e2704)


**5.** Non sarà possibile impostare un range di valore avendo scelto “Voucher Finanziario” pertanto l’opzione verrà bloccata.

![image9](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/61f9fc0a-86e7-4d28-9102-4850bb4fadc4)

**6.** Nella sezione “Messaggio”, si possono inserire frasi da stampare sullo scontrino da comunicare ai
clienti. Questa opzione non viene mai disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/c8b43d7c-e437-46e3-b655-14fa18ce867f)

**7.** Avendo scelto che sarà “**Assegnato dall’operatore**”, non sarà necessario leggere nella schermata di vendita nessun barcode in quanto non potrà essere venduto essendo un **Voucher Finanziario**. Potremo scegliere invece se far stampare un Barcode ma, in questo caso non avrebbe senso dato che il codice lo fornisce direttamente il commesso al
cliente. Potremmo però decidere se, il “Voucher \ gift” possa essere utilizzato anche su articoli scontati.

![image11](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/17edd22d-10b6-444e-9b28-76e91bfe8b34)

## - **REDENZIONE VOUCHER FINANZIARIO:**

Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa Tab le opzioni possono variare in base alla Categoria di “Voucher \ gift” selezionato. Avendo scelto “**Voucher Finanziario**” avremo tutte le voci attivate mentre, nel caso in cui si sceglie una categoria di **Buono Monouso** “ovvero quelli **Economici**”, si disabilita
l’opzione di **SCALABILE**

**1.** Si dovrà scegliere un periodo di durata del Voucher \ gift: 

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/4dec0254-1f5b-4c54-a26a-d5d8526b99ed)

- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/ce15c1d4-2aa0-4a4c-8698-13fe7ff8e44f)

- Specificato da una promozione di redenzione. Scegliendo quest’opzione, si disabiliteranno le opzioni di Isolamento, in quanto è la promozione che decide quali negozi partecipano o non partecipano.

![image14](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d98bdf94-19c5-46d0-ab39-31ca5f6efaf4)

**2.** Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \ gift”, potranno essere utilizzati su tutti i negozi della catena senza alcuna esclusione, sia essi siano Diretti o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \ gift, potranno essere utilizzati  **su tutti i negozi** ma il record verrà salvato solo sul computer del **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \ gift, potranno essere utilizzati solo sui negozi di **Emissione** ed il record verrà salvato solo sul computer della Sede.

- **Azienda:** “I voucher \ gift”, potranno essere utilizzati suddivisi per Società di negozi, ovvero se è stato emesso sui negozi diretti **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di una determinata Azienda Franchising di 5 negozi potrà essere usato solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \ gift economico , l’utilizzo multiplo sarebbe stato disabilitato),essendo un “Voucher \ gift finanziario” possiamo scegliere entrambe le opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**, consente di poter utilizzare “non per forza tutto il valore del voucher \ gift “ in un’unica transazione, ma di poterla utilizzare più volte sino ad esaurimento saldo \ valore.

![image15](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/775d8812-b8e3-4bf2-a168-15f0b7fa26d2)

**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il “Voucher \ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \ Gift” può essere accumulato con altri voucher \ gift o promozioni o sconti.

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il numero di volte che il “Voucher \ Gift” può essere utilizzato in una transazione

- **Rimborsabile:** Se settato, questo flag indica che il “Voucher \ Gift” può essere rimborsato in denaro

- **Scalabile:** Se settato, questo flag indica che il “Voucher \ Gift” può essere usato parzialmente

- **Numero max utilizzo Buono:** Si tratta di un numeratore che indica il numero massimo di volte che un cliente può utilizzare lo stesso “Voucher \ Gift”

![image16](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/a71aff61-53bc-43ab-acc1-09a483a21ecd)

- **LISTA BUONI \\ GENERAZIONE VOUCHER FINANZIARIO:**

Dopo aver configurato l’Emissione (tab Creazione) e la Redenzione, si può procedere con la “GENERAZIONE” dei “Voucher \ Gift”. Prima di farlo però bisogna **“SALVARE”** il circuito selezionando l’Icona caratterizzata dal **“floppy
disk”** ![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/874fa16c-369f-4de6-b0aa-baa66bdee932)
e rientrare nel Circuito premendo dopplio click del tasto sx del mouse.

Possiamo dunque far generare ad IPOS automaticamente un quantitativo di “Voucher \ Gift” , assegnando ad essi un **valore**, una **data di attivazione,** ed il **range di data** per la **validità** se lo abbiamo settato nella tab “Creazione” verrà proposto in automatico.

**1.** Basterà ad esempio settare:

- 100 qta come **numero**

- 30 € per **valore**

- Settare il flag “**attivo**” per far si che venga indicata l’ora esatta in cui i Voucher \ gift sono stati attivati (il che è possibile anche dopo la **data d’inizio validità**

- Premere “**GENERARE**” per far si che vengano creati i 100 voucher \ gift e mostrati nell’elenco appena sopra

![image18](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/123649c8-41c6-410e-bebb-fe1675e7ffb8)

- Premere OK per accettare la conferma dei “voucher \ gift” e visualizzare l’elenco

![image19](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2be0172e-7492-4a81-aed1-d0acd610c067)

**2.** -L’elenco appare nella sezione appena sopra e si può notare in basso a sx che sono esattamente stati generati 100 codici dal valore di 30 €

![image20](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d42915ff-483c-4808-b066-ebab36a38319)

## - **CREAZIONE VOUCHER ECONOMICO:**

**1.** Scegliere l’anagrafica del
circuito che si desidera creare immettendo un Nome, un codice, un
prefisso (cifre iniziali del circuito) ed il repository con cui vengono
utilizzata (l’ambiente d’uso).
![image21](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/3e869560-a972-42ce-b1e2-5ae9b574c25d)

**2.** Selezionare dunque la
“**Categoria**”, ovvero il tipo di Voucher \\ gift che ne determinerà il
comportamento, attivando o disattivando le successive opzioni per la
configurazione

![image22](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6636a3d2-3e3d-483b-9887-3add7104ac5b)


**3.** Ad esempio scegliendo **“Voucher Economico”** attiveremo \\
disattiveremo le seguenti opzioni.
In Grigio ciò che viene disabilitato. Dovremo selezionare un PRODOTTO
creato in precedenza (**DOCUMENTO PRODOTTI**), ad esempio il “BuonoS2”,
in quanto dovrà essere inserito come riga di reso all’interno della
schermata di vendita. **IMPORTANTE ATTIVARE IL FLAG ABILITATO.**

Premere dunque sull’icona definita dai “3 puntini” per aprire la
schermata di scelta “**prodotto**” da assegnare come “**Voucher
Economico**”

![image23](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6b07e5a3-8d48-4ea2-b3aa-64c222932aa1)


**4.**

Le opzioni definite al punto “4”, cambieranno, verrà oscurata
l’assegnazione dall’operatore.

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo
  dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati
  una lista di Voucher \\ gift, IPOS assegna il primo codice libero che
  trova in questo elenco.

- **CODICE ASSEGNATO DALL’OPERATORE**: Il commesso fornirà lui stesso al
  cliente un “Voucher \\ gift” precedentemente generato, seguendo le
  direttive aziendali

![image24](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/183d66d3-297c-4311-9aea-79a221d2f8e5)


**5.** Non sarà possibile impostare
un range di valore avendo scelto “Voucher Economico” pertanto l’opzione
verrà bloccata.

![image9](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/497f1283-73a7-459d-a5d8-6dd79c47a42f)

**6.** Nella sezione “Messaggio”, si
possono inserire frasi da stampare sullo scontrino da comunicare ai
clienti. Questa opzione non viene mai disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/5e9f95cc-bbbd-4b40-bb2e-221ce4b146b4)

**7.** Potremo scegliere se far stampare un Barcode. Potremmo però decidere se,
il “Voucher \ gift” possa essere utilizzato anche su articoli scontati.

![image11](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/08083443-a7e8-43dc-a9a6-770e17c5ca94)


## - **REDENZIONE VOUCHER ECONOMICO:**

Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa
Tab le opzioni possono variare in base alla Categoria di “Voucher \\
gift” selezionato. Avendo scelto “**Voucher Economico**” si disabilita
l’opzione di **Scalabile**

**1.** Si dovrà scegliere un periodo di durata del Voucher \\ gift:

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8391b184-d565-47f0-8386-7395037578b8)

- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6ef9861f-9ba3-4b10-af6f-a0c950c74194)


- Specificato da una promozione di redenzione. Scegliendo quest’opzione,
  si disabiliteranno le opzioni di Isolamento, in quanto è la promozione
  che decide quali negozi partecipano o non partecipano.

![image14](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8b3e7654-58c8-4b35-836a-f8d8c724670b)


**2.** Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo
Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \\ gift”, potranno essere utilizzati su tutti
  i negozi della catena senza alcuna esclusione, sia essi siano Diretti
  o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \\ gift, potranno essere utilizzati
  **su tutti i negozi** ma il record verrà salvato solo sul computer del
  **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \\ gift, potranno essere utilizzati solo
  sui negozi di **Emissione** ed il record verrà salvato solo sul
  computer della Sede.

- **Azienda:** “I voucher \\ gift”, potranno essere utilizzati suddivisi
  per Società di negozi, ovvero se è stato emesso sui negozi diretti
  **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di
  una determinata Azienda Franchising di 5 negozi potrà essere usato
  solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \\
gift economico, l’utilizzo multiplo sarebbe stato disabilitato), essendo
un “Voucher \\ gift finanziario” possiamo scegliere entrambe le opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e
  consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**,
  consente di poter utilizzare “non per forza tutto il valore del
  voucher \\ gift “ in un’unica transazione, ma di poterla utilizzare più volte sino ad
  esaurimento saldo \\ valore.

![image15](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/3ab28523-8871-4bd9-ac7c-0b990f46108c)

**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il “Voucher \\ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere accumulato con altri voucher \\ gift o promozioni o
  sconti.

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il
  numero di volte che il “Voucher \\ Gift” può essere utilizzato in una
  transazione

- **Rimborsabile:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere rimborsato in denaro

- **Scalabile:** NON è abilitato con il “Voucher Economico

- **Numero max utilizzo Buono:** Si tratta di un numeratore che indica
  il numero massimo di volte che un cliente può utilizzare lo stesso
  “Voucher \\ Gift”

![image25](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8d844d2b-04f3-490f-8855-8c0827c64f6c)

## - **LISTA BUONI \\ GENERAZIONE VOUCHER ECONOMICO:**
Dopo aver configurato l’Emissione (tab Creazione) e la Redenzione, si può procedere con la
“GENERAZIONE” dei “Voucher \\ Gift”. Prima di farlo però bisogna
“SALVARE” il circuito selezionando l’Icona caratterizzata dal “floppy
disk”![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/1d99ae3e-9ae9-41ee-a2a9-5c1b2c58ddf3)
e rientrare nel Circuito premendo dopplio click del tasto sx del
mouse.

Possiamo dunque far generare ad IPOS automaticamente un quantitativo di
“Voucher \\ Gift” , assegnando ad essi un **valore**, una **data di
attivazione,** ed il **range di data** per la **validità** se lo abbiamo
settato nella tab “Creazione” verrà proposto in automatico.

**1.** Basterà ad esempio settare:

- 100 qta come **numero**

- 30 € per **valore**

- Settare il flag “**attivo**” per far sì che venga indicata l’ora
  esatta in cui i Voucher \\ gift sono stati attivati (il che è
  possibile anche dopo la **data d’inizio validità**

- Premere “**GENERARE**” per far sì che vengano creati i 100 voucher \\
  gift e mostrati nell’elenco appena sopra

![image26](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/59752e8f-5a6e-4c78-8c87-ddffd49f07c3)


- Premere OK per accettare la conferma dei “voucher \\ gift” e visualizzare l’elenco

![image27](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/55372e63-7443-472d-9b21-2bb15cf7ac7f)


**2.** - L’elenco appare nella sezione appena sopra e si può notare in basso a
  sx che sono esattamente stati generati 100 codici dal valore di 30 €

![image28](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/98d82246-597d-463e-8c43-23d776491d38)


## - **CREAZIONE BUONO SCONTO VALORE:**

**1.** Scegliere l’anagrafica del
circuito che si desidera creare immettendo un Nome, un codice, un
prefisso (cifre iniziali del circuito) ed il repository con cui vengono
utilizzata (l’ambiente d’uso).

![image29](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/775f6576-55ea-4cc5-8937-020197ba0b2c)

**2.**>Selezionare dunque la
“**Categoria**”, ovvero il tipo di Voucher \\ gift che ne determinerà il
comportamento, attivando o disattivando le successive opzioni per la
configurazione

![image30](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/38381d5b-3079-4dd0-a194-685a7cca2c9d)

**3.** Ad esempio scegliendo **“Valore sconto”** attiveremo \\ disattiveremo le
seguenti opzioni.
In Grigio ciò che viene disabilitato. Dovremo selezionare una causale di
sconto creata in precedenza (**DOCUMENTO ANAGRAFICHE**). **IMPORTANTE ATTIVARE IL FLAG ABILITATO.**

![image31](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0fbc29f2-affb-4254-a32b-12564abcc88f)


**4.** Le opzioni definite al punto “4”, cambieranno, verrà oscurata
l’assegnazione dall’operatore.

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo
  dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati
  una lista di Voucher \\ gift, IPOS assegna il primo codice libero che
  trova in questo elenco.

- **CODICE ASSEGNATO DALL’OPERATORE**: Il commesso fornirà lui stesso al cliente un
  “Voucher \\ gift” precedentemente generato, seguendo le direttive
  aziendali

![image24](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/915108d6-ef64-4743-bd71-9799e150bbb6)

**5.** Si potrà scegliere se settare
un valore minimo ed un valore massimo. Essendo che vorrei fossero tutti
uguali i Buoni posso anche non settare nulla e lasciare 0€, oppure
mettere un valore uguale sia per entrambi “Min. e Max.”

![image32](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2a06395b-6459-4516-a640-7e159c7f0494)

**6.** Nella sezione “Messaggio”, si
possono inserire frasi da stampare sullo scontrino da comunicare ai
clienti. Questa opzione non viene mai disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/32a64177-6b14-41fd-a48c-6e96ab114259)

**7.** Potremo scegliere se far stampare un Barcode. Potremmo però decidere se,
il “Voucher \\ gift” possa essere utilizzato anche su articoli scontati.

![image33](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/871f7c9b-86c6-443c-b085-8ac88d579924)


## - **REDENZIONE BUONO VALORE SCONTO:**
Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa
Tab le opzioni possono variare in base alla Categoria di “Voucher \\
gift” selezionato. Avendo scelto “**Valore Sconto**” si disabilita
l’opzione di **Scalabile, Utilizzo Multiplo ed il Numeratore Max di
utilizzo Buono.**

**1.** Si dovrà scegliere un periodo di durata del Voucher \\ gift:

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/b2d61b3c-e601-4bf3-ae27-a62ceb3e4b61)


- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d8195b80-dbaa-40b0-9ef5-27c54fe97a8e)


- Specificato da unapromozione di redenzione. Scegliendo quest’opzione, si disabiliteranno
  le opzioni di Isolamento, in quanto è la promozione che decide quali
  negozi partecipano o non partecipano.

![image34](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d1a6a6b5-716c-4ee2-81a0-ea526d20cf4d)


*2.* Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo
Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \\ gift”, potranno essere utilizzati su tutti
  i negozi della catena senza alcuna esclusione, sia essi siano Diretti
  o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \\ gift, potranno essere utilizzati
  **su tutti i negozi** ma il record verrà salvato solo sul computer del
  **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \\ gift, potranno essere utilizzati solo
  sui negozi di **Emissione** ed il record verrà salvato solo sul
  computer della Sede.

- **Azienda:** “I voucher \\ gift”, potranno essere utilizzati suddivisi
  per Società di negozi, ovvero se è stato emesso sui negozi diretti
  **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di
  una determinata Azienda Franchising di 5 negozi potrà essere usato
  solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \\
gift economico , l’utilizzo multiplo sarebbe stato disabilitato),
essendo un “Voucher \\ gift finanziario” possiamo scegliere entrambe le
opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e
  consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**,
  consente di poter utilizzare “non per forza tutto il valore del
  voucher \\ gift “in un’unica transazione, ma di poterla utilizzare più
  volte sino ad esaurimento saldo \\ valore.

![image35](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/7baa2065-a8cc-44df-9d46-22c4537da92f)

**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il
“Voucher \\ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere accumulato con altri voucher \\ gift o promozioni o
  sconti.

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il
  numero di volte che il “Voucher \\ Gift” può essere utilizzato in una
  transazione

- **Rimborsabile:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere rimborsato in denaro

- **Scalabile:** NON è abilitato con il “Voucher Economico”

- **Numero max utilizzo Buono:** NON è abilitato con il Buono “Valore
  sconto”

![image36](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6e8676e1-5fdd-4122-a586-d33a26bf1685)


## - **LISTA BUONI \\ GENERAZIONE Buono “Valore Sconto”:**

Dopo aver configurato l’Emissione (tab Creazione) e la Redenzione, si può procedere con la
“GENERAZIONE” dei “Voucher \\ Gift”. Prima di farlo però bisogna
“SALVARE” il circuito selezionando l’Icona caratterizzata dal “floppy
disk”![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/7fda39a5-3087-4480-b26f-6a9dbd0ceb0b)
e rientrare nel Circuito premendo dopplio click del tasto sx del
mouse.

Possiamo dunque far generare ad IPOS automaticamente un quantitativo di
“Voucher \\ Gift” , assegnando ad essi un **valore**, una **data di
attivazione,** ed il **range di data** per la **validità** se lo abbiamo
settato nella tab “Creazione” verrà proposto in automatico.

**1.** Basterà ad esempio settare:

- 100 qta come **numero**

- 30 € per **valore**

- Settare il flag “**attivo**” per far sì che venga indicata l’ora
  esatta in cui i Voucher \\ gift sono stati attivati (il che è
  possibile anche dopo la **data d’inizio validità**

- Premere “**GENERARE**” per far sì che vengano creati i 100 voucher \\
  gift e mostrati nell’elenco appena sopra

![image37](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/992ebd54-4cad-4de2-9b40-1e9b5fb5fe58)

- Premere OK per accettare la conferma dei “voucher \\ gift” e
  visualizzare l’elenco

![image38](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/da4b19e3-9848-4724-9032-645cc2b2f092)


**2.** -L’elenco appare nella
  sezione appena sopra e si può notare in basso a sx che sono
  esattamente stati generati 100 codici dal valore di 30 €

![image39](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2e345ee2-3a96-4e73-b255-2c65c10f40ff)


## - **CREAZIONE GIFT CARD FINANZIARIA:**

**1.** Scegliere l’anagrafica del circuito che si desidera creare immettendo un
Nome, un codice, un prefisso (cifre iniziali del circuito) ed il
repository con cui vengono utilizzata (l’ambiente d’uso).

![image40](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/afed1196-9083-444b-8085-3e0fb4ef7580)


**2.** Selezionare dunque la “**Categoria**”, ovvero il tipo di Voucher \\ gift che ne determinerà il
comportamento, attivando o disattivando le successive opzioni per la
configurazione

![image41](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/dc40e57e-e01b-466c-8087-9b551ae49284)


**3.** Ad esempio scegliendo **“Gift Card Finanziaria”** attiveremo \\
disattiveremo le seguenti opzioni.
In Grigio ciò che viene disabilitato. Dovremo selezionare una causale di
sconto creata in precedenza (**DOCUMENTO ANAGRAFICHE**). **IMPORTANTE ATTIVARE IL FLAG ABILITATO.**

![image42](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/cd6ab234-25d0-45e0-9c47-d828aff40cde)


**4.** Le opzioni definite al punto “4”, saranno tutte attive:

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo
  dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati
  una lista di Voucher \\ gift, IPOS assegna il primo codice libero che
  trova in questo elenco.

- **CODICE ASSEGNATO
  DALL’OPERATORE**: Il commesso fornirà lui stesso al cliente un
  “Voucher \\ gift” precedentemente generato, seguendo le direttive
  aziendali

![image24](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0ba7d246-2309-4e9b-917c-d5fb4f93fbc5)

**5.** Si potrà scegliere se settare un valore minimo ed un valore massimo. Essendo che vorrei fossero emessi
in automatico delle “Gift” con valore variale tra 50 e 500 euro, si
dovrà settare nella cella Valore Min. 50€ e nella cella Valore Max. 500€

![image43](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d22f36fb-3c44-4d5e-8227-d78cc8ed4466)


**6.** Nella sezione “Messaggio”, si possono inserire frasi da stampare sullo scontrino da comunicare ai
clienti. Questa opzione non viene mai disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/9c985c07-65ca-4656-b9e7-e9f0f05e84a3)

**7.** Potremo scegliere se far stampare un Barcode (il cassiere legge la scheda da vendere e assegna il
valore) , e decidere se il “Voucher \\ gift” possa essere utilizzato anche su articoli scontati.

![image44](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/5d338aad-1312-4fd9-adb8-fbf1bdb72ded)

## - **REDENZIONE GIFT CARD FINANZIARIA:**

Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa
Tab le opzioni possono variare in base alla Categoria di “Voucher \\
gift” selezionato. Avendo scelto “**Gift Card Finanziaria**” si
disabilita l’opzione di, **Utilizzo Multiplo ed il Numeratore Max di
utilizzo Buono.**

**1.** Si dovrà scegliere un periodo di durata del Voucher \\ gift:

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/baefb3bf-30a8-4797-822f-3b72202ca632)

- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/9928c2ec-1f9f-4561-9afd-d7d187e29258)


- Specificato da una promozione di redenzione. Scegliendo quest’opzione,
  si disabiliteranno le opzioni di Isolamento, in quanto è la promozione
  che decide quali negozi partecipano o non partecipano.
  Come detto in precedenza non avremo attivo l’utilizzo multiplo.

![image45](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/23af2093-bb51-4c5d-9286-a3faf73a096e)


**2.** Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo
Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \\ gift”, potranno essere utilizzati su tutti
  i negozi della catena senza alcuna esclusione, sia essi siano Diretti
  o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \\ gift, potranno essere utilizzati
  **su tutti i negozi** ma il record verrà salvato solo sul computer del
  **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \\ gift, potranno essere utilizzati solo
  sui negozi di **Emissione** ed il record verrà salvato solo sul
  computer della Sede.

- **Azienda:** “I voucher \\ gift”, potranno essere utilizzati suddivisi
  per Società di negozi, ovvero se è stato emesso sui negozi diretti
  **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di
  una determinata Azienda Franchising di 5 negozi potrà essere usato
  solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \\
gift economico, l’utilizzo multiplo sarebbe stato disabilitato), essendo
un “Voucher \\ gift finanziario” possiamo scegliere entrambe le opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e
  consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**, consente di poter utilizzare “non per forza tutto il valore del
  voucher \\ gift “in un’unica transazione, ma di poterla utilizzare più
  volte sino ad esaurimento saldo \\ valore.

![image35](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6e0df4df-6d55-4a02-9ac4-89bfe0af086e)

**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il
“Voucher \\ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere accumulato con altri voucher \\ gift o promozioni o
  sconti.

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il
  numero di volte che il “Voucher \\ Gift” può essere utilizzato in una
  transazione

- **Rimborsabile:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere rimborsato in denaro

- **Scalabile:** Se settato, questo flag indica che il “Voucher \\ Gift”
  può essere usato parzialmente **Numero max utilizzo Buono:** NON è
  abilitato con il Buono “Valore sconto”

![image46](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d69662af-af10-4184-88ff-43e6eff130d5)


## - **LISTA BUONI \\ GENERAZIONE “Gift Card Finanziarie”:**

Dopo aver configurato l’Emissione (tab Creazione) e la Redenzione, si può procedere con la
“GENERAZIONE” dei “Voucher \\ Gift”. Prima di farlo però bisogna
“SALVARE” il circuito selezionando l’Icona caratterizzata dal “floppy
disk”![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/7466ec18-5d0a-40fc-b26a-b661064e5ae5)
e rientrare nel Circuito premendo dopplio click del tasto sx del
mouse.

Possiamo dunque far generare ad IPOS automaticamente un quantitativo di
“Voucher \\ Gift” , assegnando ad essi un **valore**, una **data di
attivazione,** ed il **range di data** per la **validità** se lo abbiamo
settato nella tab “Creazione” verrà proposto in automatico.

Ma, avendo scelto che verranno stampati da IPOS in autonomia, IPOS
genererà in autonomia i codici delle “Gift card Finanziarie” seguendo le
informazioni settate all’interno del circuito del Voucher Generator.

## - **CREAZIONE BUONO ATTIVAZIONE:**

**1.** Scegliere l’anagrafica del circuito che si desidera creare immettendo un Nome, un codice, un
prefisso (cifre iniziali del circuito) ed il repository con cui vengono
utilizzata (l’ambiente d’uso).

![image47](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d8e25bb4-9552-483c-92ce-decddaf48a98)

**2.** Selezionare dunque la “**Categoria**”, ovvero il tipo di Voucher \\ gift che ne determinerà il
comportamento, attivando o disattivando le successive opzioni per la
configurazione

![image48](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/3d14b1df-2e49-4c8d-81cc-acf3df2c83ee)

**3.** Ad esempio scegliendo **“Buono Attivazione”** disattiveremo tutte le
opzioni. In Grigio ciò che viene disabilitato. **IMPORTANTE ATTIVARE IL FLAG ABILITATO.**

![image49](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2ad89224-1e3c-42d3-842f-6cbb28f6d599)


**4.** Le opzioni definite al punto “4”, saranno tutte attive:

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo
  dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati
  una lista di Voucher \\ gift, IPOS assegna il primo codice libero che
  trova in questo elenco.

- **CODICE ASSEGNATO DALL’OPERATORE**: Il commesso fornirà lui stesso al cliente un
  “Voucher \\ gift” precedentemente generato, seguendo le direttive
  aziendali

![image24](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/a33843e5-a06e-4368-b695-f1a4cdbe9891)

**5.** Le opzioni definite al punto “5”, saranno tutte disattivate:

![image50](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/aea6d7fe-19ec-4e6e-89cc-24032b190a1b)

**6.** Nella sezione “Messaggio”, si possono inserire frasi da stampare sullo
scontrino da comunicare ai clienti. Questa opzione non viene mai
disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/a8e5a877-826e-46a4-8c3a-0c0d008cdb93)

**7.** Potremo scegliere se far stampare un Barcode (il cassiere legge la scheda da vendere e assegna il
valore), e decidere se il “Voucher \\ gift” possa essere utilizzato anche su articoli scontati.

![image44](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/21cc45ac-9dc3-405e-8920-087f38859627)

## - **REDENZIONE BUONO ATTIVAZIONE:**

Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa
Tab le opzioni possono variare in base alla Categoria di “Voucher \\
gift” selezionato. Avendo scelto “**Buono Attivazione**” si disabilita
l’opzione di **Scalabile, Cumulativo, Rimborsabile.**

**1.** Si dovrà scegliere un periodo di durata del Voucher \\ gift:

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/863f3d43-0273-41b7-84ee-92f63e866717)

- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/74fd2c08-a0ca-420a-80dd-860f1a17575c)

- Specificato da una promozione di redenzione. Scegliendo quest’opzione, si disabiliteranno
  le opzioni di Isolamento, in quanto è la promozione che decide quali
  negozi partecipano o non partecipano.

![image51](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/b2102884-5997-4221-a138-dd175c502058)

**2.** Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo
Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \\ gift”, potranno essere utilizzati su tutti
  i negozi della catena senza alcuna esclusione, sia essi siano Diretti
  o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \\ gift, potranno essere utilizzati
  **su tutti i negozi** ma il record verrà salvato solo sul computer del
  **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \\ gift, potranno essere utilizzati solo
  sui negozi di **Emissione** ed il record verrà salvato solo sul
  computer della Sede.

- **Azienda:** “I voucher \\ gift”, potranno essere utilizzati suddivisi
  per Società di negozi, ovvero se è stato emesso sui negozi diretti
  **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di
  una determinata Azienda Franchising di 5 negozi potrà essere usato
  solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \\
gift economico, l’utilizzo multiplo sarebbe stato disabilitato), essendo
un “Voucher \\ gift finanziario” possiamo scegliere entrambe le opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e
  consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**, consente di poter utilizzare “non per forza
  tutto il valore del voucher \\ gift “in un’unica transazione, ma di
  poterla utilizzare più volte sino ad esaurimento saldo \\ valore.

![image52](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/532e21fc-9bae-4cda-91e8-ee465e4dffe7)


**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il
“Voucher \\ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere accumulato con altri voucher \\ gift o promozioni o
  sconti. (In questo caso non è possibile disattivarlo)

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il
  numero di volte che il “Voucher \\ Gift” può essere utilizzato in una
  transazione

- **Rimborsabile:** NON è abilitato con il Buono “Buono Attivazione”

- **Scalabile:** NON è abilitato con il Buono “Buono Attivazione”

- **Numero max utilizzo Buono:** NON è abilitato con il Buono “Valore sconto”

![image53](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/b4c286df-033c-498a-95bd-cfc259b19b17)

## - **LISTA BUONI \\ GENERAZIONE “Buono Attivazione”:**

Dopo aver configurato l’Emissione (tab Creazione) e la Redenzione, si può procedere con la
“GENERAZIONE” dei “Voucher \\ Gift”. Prima di farlo però bisogna
“SALVARE” il circuito selezionando l’Icona caratterizzata dal “floppy
disk”![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/76d1a9de-5aec-4992-89a2-e7a956658817)
e rientrare nel Circuito premendo dopplio click del tasto sx del
mouse.

Possiamo dunque far generare ad IPOS automaticamente un quantitativo di
“Voucher \\ Gift” , assegnando ad essi un **valore**, una **data di
attivazione,** ed il **range di data** per la **validità** se lo abbiamo
settato nella tab “Creazione” verrà proposto in automatico.

Ma, avendo scelto che verranno stampati da IPOS in autonomia, IPOS
genererà in autonomia i codici delle “Buoni Attivazione” seguendo le
informazioni settate all’interno del circuito del Voucher Generator.

## - **CREAZIONE GIFT CARD ECONOMICA:**

**1.** Scegliere l’anagrafica del
circuito che si desidera creare immettendo un Nome, un codice, un
prefisso (cifre iniziali del circuito) ed il repository con cui vengono
utilizzata (l’ambiente d’uso).

![image21](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/81d4c071-2c41-42df-a11d-926389f46374)

**2.** Selezionare dunque la
“**Categoria**”, ovvero il tipo di Voucher \\ gift che ne determinerà il
comportamento, attivando o disattivando le successive opzioni per la
configurazione

![image54](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2f20c8c5-7127-4d80-a681-d72f4afd576c)

**3.** Ad esempio scegliendo **“Gift Economico”** attiveremo \\ disattiveremo
le seguenti opzioni.
In Grigio ciò che viene disabilitato. Dovremo selezionare un PRODOTTO
creato in precedenza (**DOCUMENTO PRODOTTI**), ad esempio il “BuonoS2”,
in quanto dovrà essere inserito come riga di reso all’interno della
schermata di vendita. **IMPORTANTE ATTIVARE IL FLAG ABILITATO.**
Premere dunque sull’icona
definita dai “3 puntini” per aprire la schermata di scelta
“**prodotto**” da assegnare come “**Gift Economico**”

![image23](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/dfe85fa3-3816-4f98-9b46-41ba162e14c4)


**4.** Le opzioni definite al punto “4”, cambieranno, verrà oscurata
l’assegnazione dall’operatore.

- **AUTO-GENERATO**: IPOS genera in automatico un nuovo codice partendo
  dal “Prefisso”

- **AUTO-ASSEGNATO**: Se in precedenza sono stati importati o caricati
  una lista di Voucher \\ gift, IPOS assegna il primo codice libero che
  trova in questo elenco.

- >**CODICE ASSEGNATO DALL’OPERATORE**: Il commesso fornirà lui stesso al cliente un
  “Voucher \\ gift” precedentemente generato, seguendo le direttive
  aziendali

![image24](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/93435027-ccc0-4060-a056-62b66bda50cf)

**5.** Sarà possibile impostare un range di valore avendo scelto “**Gift Economico**” pertanto bisognerà
settare un valore minimo ed un valore massimo.

![image55](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/16f9838f-c910-4bdc-9fb4-8d53dfbe1c78)


**6.** Nella sezione “Messaggio”, si
possono inserire frasi da stampare sullo scontrino da comunicare ai
clienti. Questa opzione non viene mai disabilitata.

![image10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/498c5ade-de37-4828-95c0-4d8556a47040)

**7.** Come descritto al punto 2, per poter vendere un “Gift Economico” , bisogna abilitare che sia
**visibile in cassa (Visibile POS).** Potremo scegliere se far stampare
un Barcode. Potremmo però decidere se, il “Voucher \\ gift” possa essere
utilizzato anche su articoli scontati.

![image56](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0ee4d678-9b44-45c8-a243-86f699de8ace)

- **REDENZIONE BUONO VALORE SCONTO:**

**1.** Collegandoci al punto 3 del paragrafo “**CREAZIONE**”, anche in questa
Tab le opzioni possono variare in base alla Categoria di “Voucher \\
gift” selezionato. Avendo scelto “**Gift Economico**” si disabilita
l’opzione di **Scalabile, Utilizzo Multiplo ed il Numeratore Max di utilizzo Buono.**

Si dovrà scegliere un periodo di durata del Voucher \\ gift:

- Ad esempio si potrà settare un periodo **FISSO** tra 2 date

![image12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/658fbac7-56ad-48a0-99ce-88219349db84)

- Settare un periodo dinamico, ad esempio 1 anno

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/3af79ee8-65e3-4982-8563-4f428d058f46)


- Specificato da una promozione di redenzione. Scegliendo quest’opzione, si disabiliteranno
  le opzioni di Isolamento, in quanto è la promozione che decide quali
  negozi partecipano o non partecipano.

  ![image14](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/b7dd2f98-ce09-4b2c-8d6d-9c10abca660e)


**2.** Per quanto riguarda l’Isolamento, nei casi del Periodo Fisso o Periodo
Dinamico, si dovrà settare il tipo di isolamento desiderato ovvero:

- **Nessuno:** “I voucher \\ gift”, potranno essere utilizzati su tutti
  i negozi della catena senza alcuna esclusione, sia essi siano Diretti
  o Franchising o Rivenditori o Corner. Dati rimangono **su DB Sede**.

- **PV su DB Locale:** “I voucher \\ gift, potranno essere utilizzati
  **su tutti i negozi** ma il record verrà salvato solo sul computer del
  **negozio** e non in Sede.

- **PV su DB SEDE:** “I voucher \\ gift, potranno essere utilizzati solo
  sui negozi di **Emissione** ed il record verrà salvato solo sul
  computer della Sede.

- **Azienda:** “I voucher \\ gift”, potranno essere utilizzati suddivisi
  per Società di negozi, ovvero se è stato emesso sui negozi diretti
  **SOLO** sui diretti potrà essere utilizzato, mentre se emesso su di
  una determinata Azienda Franchising di 5 negozi potrà essere usato
  solo su questi 5 negozi eccc. I dati rimarranno solo su Db SEDE.

Mentre, per quanto riguarda **l’utilizzo** (se fosse stato un voucher \\
gift economico , l’utilizzo multiplo sarebbe stato disabilitato),
essendo un “Voucher \\ gift finanziario” possiamo scegliere entrambe le
opzioni:

- **L’Utilizzo unico**, solitamente si usa per voucher economici e
  consente **solo** l’utilizzo tutto in un’unica transazione.

- **L’utilizzo multiplo**,
  consente di poter utilizzare “non per forza tutto il valore del
  voucher \\ gift “in un’unica transazione, ma di poterla utilizzare più
  volte sino ad esaurimento saldo \\ valore.

![image35](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/069b9a15-5e3e-4dd1-b607-eca6e0e6ac75)

**3.** Inoltre si avrà la possibilità di poter scegliere come utilizzare il
“Voucher \\ Gift”

- **Cumulativo:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere accumulato con altri voucher \\ gift o promozioni o
  sconti.

- **Conteggio Cumulativo:** Si tratta di un numeratore che indica il
  numero di volte che il “Voucher \\ Gift” può essere utilizzato in una
  transazione

- **Rimborsabile:** Se settato, questo flag indica che il “Voucher \\
  Gift” può essere rimborsato in denaro

- **Scalabile:** NON è abilitato con il “Voucher Economico”

- **Numero max utilizzo Buono:** NON è abilitato con il Buono “Valore
  sconto”

![image36](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/68b0fa2f-f9ad-4245-b2e9-0661cb560364)

