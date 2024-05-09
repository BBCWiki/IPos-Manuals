---
layout: home
title: Etichette
parent: Catalogo
grand_parent: BackOffice-Sede
nav_order: 5
---


# **Gestione Layout**

**Etichette Predefinite**

**Gestione delle etichette in Ipos BO**

## **PREMESSA**

Dalla versione 1.22.10 in IPOS vengono definiti 10 layout di etichette (estendibile fino a 100), che possono essere modificate dal cliente in autonomia da Back Office della sede – menu Utility - Layout Documento.
In Ipos sik può stampare anche in un ‘altro linguaggio chiamato **ZPL/EPL** per definire il layout dell’etichetta, la quale viene invece stampata sul driver nativo windows della stampante etichette (Zebra,Toshiba, etc), come un normale documento di stampa in Windows.

Per utilzzare il linguaggio **ZPL** bisogna configurare alcuni paramentri per farlo funzionare :

- Su DataBase ,nella tabella LabelTypes ,la colona FormType, deve essere = **ST**

- Nella stessa tabella però nella colona FormDefinition dobbiamo avere :

>^XA ^FO11,10^BY3^BEN,65,Y,N^FD{Var0}^FS
>
>^FO10,106^A0,20,24^FD{Var15}^FS
>
>^FO165,106^A0,20,24^FD{Var10}^FS
>
>^FO10,130^A0,28,32^FD{Var14}^FS
>
>^FO165,130^A0,20,24^FD{Var27}^FS
>
>^FO10,156^A0,20,24^FD{Var6}^FS
>
>^FO165,156^A0,20,24^FD{Var5}^FS
>
>^CI0,21,36 ^LH0,10^FS
>
>^FO5,180^A0B,16,16^FDTaglia^FS
>
>^FO25,180^A0,36,40^FD{Var4}^FS
>
>^FO100,180^A0,44,48^FD{Var7}^FS
>
>^PQ{LabelCount} ^XZ
>
>Dove : {Var0}….{Var27} sono le variabili per definire le informazioni che escono sull'etichetta
>
>^FO-rapresenta
>
>^A0-rapresenta
>
>^PQ{LabelCount} – rapresenta la collona LabelsOnPage della tabella LabelTypes cioè quante etichette vengono stampate per pagina(in questo caso =1)

- Ogni etichetta inizia con ‘’^XA’’ e deve finire con ‘’^XZ’’

![image3](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/10cd5675-390b-4a37-919d-84e65343d184)

![image4](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/611375af-f656-4f0b-b2cb-9e64c7e1bfd7)


L'attuale configurazione con i 10 layout sarebbe esclusivamente per le
etichette singole. Per quanto riguarda etichette in formato A4
(multi-etichetta sul singolo foglio) ci sono delle modifiche da fare
sulla configurazione attuale caricata di default, che è in fase di
sviluppo da parte di BBC.  
Per le etichette A4 verranno definiti\creati altri 10 layout
preconfigurati. L’operazione verrà eseguita da uno script che genera i
10 layout di etichette A4.

## CAPITOLO 1

I Layout delle etichette e per quali negozi sono validi, li troveremo nel menù ipos del BACK OFFICE “Utilità”.

![image5](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/299b4f21-9909-488a-bb72-b66d0c41f045)

Basterà scegliere l’etichetta che vogliamo modificare e fare doppio click col tasto sinistro del mouse per entrare nell’editor del Layout delle Etichette.

Le 10 etichette sono configurate di default con un Layout che contiene la base dati: “Barcode, Codice Articolo, Descrizione, Prezzo scontato”.

![image6](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/fa9be8cf-0c08-451c-a822-b5ff3618f48c)


>**Nota :** Al momento il nome dll’ Etichetta non sarà gestibile lato “utente”, per cui non risulterà visibile nel menù a >elenco(dropdown) dei Prodotti durante la scelta dell’etichetta che ci interessa stampare.

Se vogliamo che il nominativo viene riportato anche nel menù a elenco(dropdown) nel menù Prodotti durante la scelta delle etichette è necessario intervenire a livello Database. Precisamente bisogna modificare il campo “Descrizione” nella tabella LabelType (Vedere immagini qui sotto)

**TAB LABEL TYPE**

![image7](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/906e3534-2acb-4e6e-a134-0614d693f177)

Come scritto sopra, per poter entrare nell’editor delle etichette basterà sceglierne una e fare doppio click del mouse con il tastosinistro. Nel prossimo capito affronteremo nel dettaglio l’utilizzo dell’editor etichette.

## **CAPITOLO 2**

**L’EDITOR**

Qui sotto una panoramica dell’ Editor Etichette di IPOS :

![image8](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/cad602e3-5bdc-41b3-a8c6-5df4b99be8a8)

Nel centro troveremo **l’etichetta** creata con i parametri (le Variabili) di default.

Sulla destra abbiamo il menù “**Esplorer Report**” , una sorta di riepilogo di tutto quello di cui è composta l’etichetta, per esempio i bordi superiori ed inferiori, i dettagli (contiene il dettaglio per esempio di altezza dell’etichetta e la sua larghezza), se vi sono foto presenti al suo interno ecc. Se apriamo i dettagli, troveremo un sottomenù con il contenuto dei dettagli dell’etichetta (Vedere immagini qui sotto) . Più sotto troveremo il menù “Properties” ed il menù “Report
Gallery”

![image 10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/70b9ed6a-f89a-46fe-b327-5e812ee76a96)



>NOTA : Ogni voce del menù Detail che andremo a selezionare, avrà lapossibilità di essere “MODIFICATA” nelle sue >caratteristiche. Appena selezioneremo un dettaglio dal Menù “Report Esplorer” o selezioneremo un
>pezzo di etichetta, anche il menù “Properties” ci indicherà le proprietà del dettaglio selezionato.

## CAPITOLO N: “PROPERTIES”

In questo caso ho selezionato ad esempio il dettaglio “Barcode”, ed il Menù “Properties” mi seleziona automaticamente dal suo menù di Dropdown, il dettaglio da me scelto con tutte le sui proprietà annesse. Tramite “scrollbar” di destra è possibile scorrere tra le proprietà del Dettaglio scelto e modificarne i valori.

![image13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0857f592-03e3-4b6a-a0a3-1d7d8adb6762)

Le proprietà si dividono in sottomenù tra cui :

![image14](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/99292237-df69-4215-ac17-0370ce641777) APPEREANCE :

Qui possiamo modificare l’allineamento del dettaglio selezionato ,le dimensioni intese come “Altezza e Larghezza”,
il posizionamento per quanto riguarda asse x ed Y del dettaglio all’interno dello spazio di lavoro dell’etichetta.

![image15](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/ba7dece8-c370-446e-bcd4-2f05d821d77c) DATA:

Troveremo a titolo informativo ove il dettaglio selezionato è contenuto, il suo DataSource, il suo DataMember,

![image16](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/e71ad6af-11be-4887-8df5-0638a85c06f0) MISCELLANEOUS:

Troveremo l’indicazione in merito, al nome del Dettaglio, e la possibilità di settare i margini di controllo del dettaglio selezionato.

![image17](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/dbf0e6a1-b930-4b3f-b0f2-1462cd6ae201) PAGE SETTINGS: (non del singolo dettaglio ma di tutta l’etichetta)

Troveremo caratteristiche in merito all’altezza e larghezza ell’etichetta, troveremo i settings sui margini di lavoro dell’etichetta, e la possibilità di settare la tipologia di stampa richiesta dall’etichetta(per esempio se dovremmo settare una stampa per etichetta A4.

## CAPITOLO N: “FIELD-LIST”

Il Menù Field-List non è altro che il menù delle variabili dell’etichetta.
Il cliente può variare qualsiasi posizionamento e applicare alcune formattazioni sui campi.

![image18](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/ded90ea6-bb23-44eb-8eb1-ec8092926d9c)

Di seguito l’etichetta con le Variabili di default:

![image19](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0ca0caff-bffc-47f8-a628-a0297d3c746f)

Per aggiungere altri campi nel layout si devono trascinare da FieldList i campi variabili:

Di seguito una rapida “Descrizione” delle Variabili che è possibile modificare all’interno del piano di lavoro dll’etichetta.

00 Barcode  
01 ProductCode  
02 ProductName  
03 ProductId             
04 SizeCode  
05 ColorCode  
06 ColorName  
07 GrossSalePrice  
08 DiscountPercentage  
09 NetSalePrice  
10 SeasonCode  
11 Currency  
12 ProductFamilyCode  
13 ProductFamilyName  
14 ProductSubfamilyCode  
15 ProductSubfamilyName  
16 ProducerName  
17 ProducerLineName  
18 ProductGroupName  
19 ProductTypeName  
20 LabelName  
21 Attribute1Name  
22 Attribute2Name  
23 Attribute3Name  
24 Attribute4Name  
25 Attribute5Name  
26 Attribute6Name  
27 SupplierProductCode  
28 ProductGroupCode  
29 ProductTypeCode

Come abbiamo visto nel menù precedente, ogni variabile che verrà aggiunta all’etichetta sarà inserita nel sottomenù “detail” del menù “Report Explorer”, e ne potremo poi modificare i settaggi nel menù “Properties”

![image20](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/f00d9136-9275-4396-8bd7-0f32527ec466)

Ecco che appena inserita nel Layout la VAR9, ci appare nel Detail “label2” e anche nel menù Properties “Label2 Label”. Sarà dunque possibile ora modificarne i Settings come visto in precedenza.

![image21](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/f683ba1a-8858-424e-ac1b-323262028429)

Possiamo dunque anche cancellare le variabili che non ci servono o anche tutta quanta l’etichetta, semplicemente selezionando le variabili ed il barcode e premere il tasto “canc” da tastiera. (Vedere immagini sotto).
Inoltre spariranno anche dai menù detail e properties le variabili cancellate.

![image 11](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/ecaea1a5-cee5-417b-a87c-54e5e99c6488)


## SHORTCUT MENU’ DETAIL BAND

Un altro metodo per la modifica dei settings delle Variabili aggiunte, è direttamente dal “detail band” presente generico sul Layout dell’etichetta (per modifiche generali), o su ogni variabile aggiunta.
Basta premere sull’icona ![image25](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/f67046c1-23d7-472e-bc33-8cd334f062a1) accanto alle variabili o alla scritta Detail, per aprire i settings(vedere sotto immagini).
L’editor ci indicherà dove ci troviamo evidenziando nel sottomenù detail del menù Report Explorer:

Generico per Layout Etichetta:

![mah10](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2344f40a-ead9-4265-9b27-1129f2649084)

Specifico per ogni variabile:

![mah 11](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/e5d8d7a5-1ea1-432b-9898-4af0819d3079)

Altri shortcut li troviamo nella parte alta dell’editor :

In base alla parte cheselezioniamo del Layout , cambieranno anche i setting del menù shortcut in alto

![image30](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/251dc30a-a838-48ba-8d7e-1d1564b23657)

Per esempio selezionando il barcode avremo questo menù :

![image31](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/7cdf7560-5d6a-4ab2-a36c-2a08b2136aae)

Se invece selezioneremo un’immagine, il menù cambierà i settings:

![image32](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/5a52ce72-1a5f-41b1-b3df-9d140742cafd)

# CAPITOLO 4: “MENU’ TOOLBOX”


![image33](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/384886c9-829c-4a71-a2de-2d029cec2944)
Tutto quello (o quasi) che è presente nel menù “**verticale**” a sinistra dell’Layout etichetta, può essere trascinato all’interno dell’etichetta stessa, ed in automatico verrà aggiunto nel menù “**EXplorer Report**” di cui ho menzionato in precedenza. Per esempio qualora volessimo inserire un’immagine basterà trascinare il simbolo della “Picture” nell’etichetta e subito lo vedremo apparire nell’elenco del menù “**EXplorer Report**”, pronta per essere modificata a nostro
piacimento.

![image34](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/0010d35a-38b9-456e-acad-740f7eab4c2f)


Come vedete ho trascinato l’area per l’immagine sull’etichetta, ma ètroppo grande e viene marchiata di rosso. Non è un problema in quanto, per adeguare l’immagine basterà premere sulla voce “picturebox1” apparsa nell’elenco “detail” ( del menù “Report Explorer”) e, modificarne le proprietà dell’oggetto inserito (l’immagine) a mio piacimento tramite le
proprietà del menù “Properties” (che trovo nella parte inferiore a destra dell’editor).

Oppure basterà muovere il mouse per ingrandire o rimpicciolire l’immagine tenendo premuto il tasto sx su uno dei punti che circondano l’area dell’immagine o dell’oggetto che decideremo di inserire.

Vengono accettate quasi tutti i tipi di immagini, già presenti sul proprio PC o scaricate online. Per comodità ho creato una cartella dove inserirle.

![image35](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/005c2e07-eb86-4b41-8101-30463d4d97de)

Per caricare un’immagine che abbiamo appena scaricato o che è presente sul nostro Pc, useremo il menù “Properties”, cliccando sopra a picturebox1 nell’elenco detail. Dovremo poi andare alla voce “Datasource” e selezionare il percorso dell’immagine che ci interessapremendo sui puntini nel box “image URL”. Si aprirà dunque la finestra di windows per selezionare l’immagine desiderata. (vedi immagini quisotto)

Premere dunque su “image url” per far aprire la finestra di Scelta dell’immagine di windows

![image36](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/a2344699-d66b-48b3-ae51-28c28fad4beb)

Una volta apparsa la finestra, scegliere l’immagine desiderata per far si che ci appaia nel layout etichetta

![image37](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/740257d7-e23d-4d87-a5af-0c405ac2dcc9)

L’immagine verrà caricata nel layout, e dal menù Properties potremo plasmarla a nostro piacimento.

![image38](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/cbfcefff-d8da-4229-a616-5fe92601b3cb)

Se nel riquadro immagine appare solo un pezzo, basta andare nel menù “Properties” per modificarla.

Nel menù “Properties” basterà andare sulla voce ![image39](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8a90fc0c-54e4-4ac8-85ae-b9706098d24a) “Behavior” e modificare la “Size” a proprio piacimento alla voce “sizing”:

![image40](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/275fa6a9-e799-47b5-8814-66627a741f88)

Per esempio, scegliendo Stretch Image, ho ottenuto il seguente risultato:

![image41](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/caa57628-2228-47a7-bd91-e94edc4f31aa)


## ANTEPRIMA

Qualora volessimo vedere a che punto siamo con la creazione della nostra etichetta possiamo selezionare il dettaglio che ci interessa e premere sul pulsante in basso **“PREVIEW”**

Per esempio selezionando l’immagine, potremo vedere nell’etichetta come appare

![image42](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/2dc5c43f-a282-4487-b62e-f095803a1fdd)

![mah 12](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6f54c49f-5139-4083-92a1-a2ea444cb2bd)

## CAPITOLO 5: “REPORT GALLERY”

Il menù “Report Gallery” consente di archiviare e riutilizzare i report e i loro elementi.

![image44](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/06034446-9d81-4a5d-8cce-80a7495aff87)

Non bisogna confondere “Report Gallery” con “Report Explorer” che ha un'interfaccia utente simile. “Report Gallery”, memorizza i modelli, i componenti, i dettagli condivisi del layout. “Report Explorer” visualizza la struttura del report corrente.

### MODELLI DI REPORTS

“Report Gallery” mostra i modelli di layout delle etichette nella
categoria Reports.

![image45](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/fbb5ef45-4d29-443e-acb6-c174a43dd4d4)

Per creare un nuovo modello, fare clic con il pulsante destro del mouse su un'area vuota attorno all'area di progettazione e selezionare Aggiungi alla galleria nel menu contestuale.

![image46](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/c2cbc2e2-d124-469f-8212-8b573e077b78)

Il valore della proprietà Name del report definisce il nome del modello.

![image47](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8822c400-c647-4e74-8d39-d735e9e30ff2)

Qualora volessimo applicare un modello al rapporto corrente, dovremo fare clic con il pulsante destro del mouse sul modello nell’ elenco dei Reports e selezionare Applica layout al report.

![image48](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/d78945a8-99fe-4716-8aa9-88e0c3a13a0d) ![image49](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/8ce7fb31-f861-480f-a3ea-e41a2e615e6a)


Ovviamente l’editor ci avviserà che andremo a perdere tutti i dati dell’etichetta corrente. “Premere su yes”

![image50](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/9de4d9ba-4555-460e-950e-d585f8e2c7ef)


## BANDS

La categoria Bands in “Report Gallery”, contiene modelli di bande.

Per creare un nuovo modello, fai clic con il pulsante destro del mouse su una fascia di report e scegli Aggiungi alla galleria nel menu contestuale. Il valore della proprietà Name della band definisce il nome del modello

![mah 13](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/be112f7b-bd6a-4c8a-8c46-3a1edf24a247)

## CONTROLS

Si possono combinare i controlli dei report della stessa Bands in un modello. Tieni premuto MAIUSC o CTRL e seleziona i controlli. Quindi, fai clic con il pulsante destro del mouse sulla selezione e scegli
Aggiungi alla galleria nel menu di scelta rapida.

![image52](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/4d58fe1c-120a-4f0b-aa87-92d79a0f8c60)  ![image53](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/6131870e-bbc5-4180-a15c-80a3ebdcee93)



## Import and Export Templates

Puoi importare elementi della Galleria da un file XML. Fare clic con il pulsante destro del mouse sul pulsante Importa della barra degli strumenti, individuare un file nella finestra di dialogo Apri richiamat0a e fare clic su OK.

![image54](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/cec80536-2596-4c2e-85bd-c771c2c35793)


Selezionare la fonte xml da dove poter caricare gli elementi dell’etichetta.

![image55](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/27120200-fe0c-45bb-95ae-342c72c78d29)

Per salvare i modelli di galleria in un file XML, fai clic sul pulsante Esporta nella barra degli strumenti e seleziona un file di destinazione nella finestra di dialogo Salva.

![image56](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/b4232ad7-d212-4d2d-a1a9-77f1e9e2d7b5)


Scrivere il nome della fonte xml dove poter salvare il modello dell’etichetta.

![image57](https://github.com/BBCWiki/IPos-Manuals/assets/164161230/f627b1c5-48ed-4a6d-90e5-7933328eae7f)

