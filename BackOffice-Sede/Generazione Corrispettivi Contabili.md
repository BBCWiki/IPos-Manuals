---
layout: default
title: Generazione Corrispettivi Contabili
parent: Backoffice Sede
nav_order: 3
---

# Generazione Corrispettivi Contabili

## Chiusura di cassa
In fase di chiusura, IPOS crea dei totali, al livello di chiusura cassa
- testata chiusura - tabella *StoreDayCloses*
- parte economica (totali al livello di IVA) - tabella *StoreDayCloseVats*.
   Vengono generati 2 record per ogni IVA, uno per la vendita e uno per il reso
- parte finanziaria (incassi totali al livello di forma di pagamento) - tabella *MoneyMovements*.
   Viene generato un record per ogni tipologia operazione identificata dalla causale. La causale "principale" e' CC_VENDITE

### Totale vendite per IVA

Di seguito un esempio di una chiusura, come presente nella tabella StoreDayCloseVats:
	
|DocumentType	|VatRate	|VatValue	|ValueVatExcluded	|ValueVatIncluded|
|------------	|--------	|--------	|-------------------|----------------|
|V				|22		|3,21		|14,59					|17,80           |
|V				|10		|0,00		|0,00					|0,00            |
|V				|4		|42,47		|1061,83				|1104,30         |
|V				|0		|0,00		|0,00					|0,00            |
|N				|22		|0,00		|0,00					|0,00            |
|N				|10		|0,00		|0,00					|0,00            |
|N				|4		|0,00		|0,00					|0,00            |
|N				|0		|0,00		|0,00					|0,00            |
	

### Totale Movimenti finanziari (incassi e operazioni di spostamento soldi)

I movimenti denaro sono le operazioni di spostamento dei soldi da un sorgente ad una destinazione.
Ogni movimento fa riferimento a:
	- Causale	(CauseAccounantKeyId)
	- Tipo di pagamento	(PosPaymentTypeId)
	- Sorgente	(SourceAccountantKeyId)
	- Destinazione	(DestinationAccountantKeyId)
	
#### Causali movementi denaro
La causale identifica il motivo per cui sono stati spostati i soldi, le motivazioni sono definite nella tabella AccounantKeys (campo Code). 

CC_APERTURACASSAFORTE	- Apertura negozio. Il valore significa il totale dei soldi presenti nella cassaforte all'inizio giornata. Viene generato in fase di apertura della prima cassa del punto vendita (cassa 1). Solo per i contanti. 

CC_APERTURAFONDOCASSA	- Apertura cassa. Riporta i soldi spostati dalla cassaforte nel negozio  nel casetto. Solo per i contanti. 

CC_VENDITAPRODOTTI - La causale "piu importante". Soldi entrati nel cassetto, dai clienti, per le vendite effettuate in cassa. Un record per ogni forma di pagamento incassata. Questo e' il valore rilevato, potenzialmente modificato dall'utente (nella cella gialla di chiusura) rispetto al teorico calcolato da IPOS.

CC_PC_VENDITAPRODOTTI - Il valore teorico dei soldi entrati nel casetto. Utilizzata per tracciare il valore teorico proposto da IPOS. Se non vengono fatte modifiche/rilevazioni da parte dell'utente, dovrebbe essere uguale al valore del movimento con causale CC_VENDITAPRODOTTI

CC_VENDITAGIFTCARD	- Il valore delle vendite di nuove Gift card - sono le emissioni di gift card. Un record per ogni tipo di pagamento con cui sono state vendute le Gift.

CC_EMISSIONEBUONORESO - Il totale dei resi con emissione del buono reso.

CC_VENDITACAPARRA - Il totale dei soldi ricevuti dai clienti come caparra per gli ordini (caparre "vendute"). Quando viene chiuso l'ordine, il valore della caparra venduta verra "incassato", e risultara nel movimento di CC_VENDITAPRODOTTI con tipo di pagamanto CAPARRA
	
CC_PRELIEVO - Operazioni manuali di prelievo contanti dalla cassa, e spostamento nella cassaforte.

CC_VERSAMENTO - Operazioni manuali di versamento nella cassa, dei soldi prelevati dalla cassaforte.

CC_SPESE - Operazioni manuali di prelievo soldi dalla cassa per pagare delle spese (fatture fornitori, acquisti materiali, etc). Solo per i Contanti.


CC_DIFFERENZENEGATIVE	- La differenza **negativa**, se esiste, tra il rilevato e il teorico del contante, nel conteggio in fase di chiusura. Il conto destinazone e' il conto differenze.

CC_DIFFERENZEPOSITIVE - La differenza **positiva**, se esiste, tra il rilevato e il teorico del contante, nel conteggio in fase di chiusura. Il conto destinazone e' il conto differenze.
		
CC_DEPOSITOBANCA - Operazioni manuali di prelievo dei soldi dalla cassaforte per spostarli in banca. Solo per i Contanti.
	
CC_CHIUSURAFONDOCASSA - Chiusura cassa. Sposta il totale dei contanti dal cassetto nella cassaforte.

CC_CHIUSURACASSAFORTE - Chiusura negozio. Il valore significa il totale dei soldi presenti nella cassaforte a fine giornata. Viene Generato in fase di chiusura dell'ultima cassa del punto vendita (cassa 1). Solo per i Contanti.

## Generazione Registrazioni contabili
Ipos genera le registrazioni contabiliti in partita doppia (Dare/Avere), cioe la Prima Nota contabile. I dati generati sono pronti per essere inviati ad un sistema contabile, quindi riportano i codici dei conti contabili e delle causali cosi come richiesto dal sistema di contabilita. 
La registrazione viene fatta per punto vendita, quindi contiene la somma delle chiusure di tutte le casse del negozio.
Di conseguenza, per poter fare le registrazioni, e' necessario prima definire la mappatura tra i codici conti e causali di IPOS e il valore corrispondente del sistema contabile.
La mappatura viene fatta usando il modulo BO-Contabilita-Default Conti/Causale dove, per ogni causale e tipo di pagamento, viene definito il valore con cui questo viene esportato verso la contabilita (Tabella AccounantKeys)
E' possibile definire anche al livello di Punto Vendita un codice causale/conto differente (tabella AccountantStoreKeys), che ha precendeza rispetto a quello generale.

### Mappatura Causali
Per ogni causale esportata e' necessario impostare nel campo "Valore" il codice della causale del sistema di contabilita.
	Codice = {Codice Causale IPOS}
	Valore = {Codice Causale Sistema Contabile}
	
### Mappatura Conti
Come conto si intende il tipo di pagamento.
Per ogni tipo di pagamento **dev'essere** definito il valore una mappatura in AccounantKeys, con il seguente formato:
	Codice = ST_{Codice Tipo di Pagamento IPOS}
	Valore = {Codice Conto Sistema Contabile}
	
	Esempi: ST_TICKET, ST_CASH, ST_CC04

### Formati diversi di esportazione
Visto che ogni cliente e sistema contabile aveva il suo modo in cui i le registrazione dovevano essere generate, sono stati sviluppati piu' modalita di generazione, ogni modalita e' una nuova stored procedure AccountantRegistrationsRegisterFiscalDay01, ..02, ..03, etc

## Generazione Corrispettivi formato DEN

|Tipo|Causale|Conto|Dare|Avere|
|----|-------|-----|----|-----|
|E|CCCORRIS|SCCORRIS| | Imponibile
|V|CCCORRIS|SCIVACOR| Iva | |
|F|CCCORRIS|ST_(TipoPagamento)| IncassatoVenditeProdotti | |
|F|CCCORRIS|ST_BR| | ValoreBuoniResoEmessi
|F|CCCORRIS|ST_GIFTCARD| | ValoreGiftCardVendute

## Export verso la contabilita


