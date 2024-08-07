---
layout: default
title: Verifica Email
parent: BackOffice Sede
nav_order: 6
---

# Verifica Email

## Cosa fa:
La Verifica Email è una funzionalità che invia un'email ai tuoi clienti contenente un link. Quando il link viene cliccato, verifica che l'indirizzo email sia corretto. Se l'email viene verificata con successo, il tuo cliente sarà idoneo a ricevere nuove offerte o promozioni da te via email.

## Requisiti:
- All'interno dei Layout dei Documenti, avrai un'entità chiamata **EmailVerification**. Qui troverai un modello di base che verrà utilizzato per inviare email dall'aspetto uniforme a tutti i tuoi clienti. Puoi personalizzare questo modello, ma tieni presente che sarà necessario consultare BBC Technologies per assicurarti che il modello sia conforme.
- È necessario avere un account SMTP all'interno di **StoreSetup** (per ulteriori dettagli su come configurarlo, contatta BBC Technologies).
- Se hai un firewall che non consente l'accesso a Internet pubblico, assicurati di **WHITELISTARE** il seguente indirizzo IP: xxx.xxx.xxx.xxx.

## Come Abilitare:
Nel Backoffice di **IPOS**, all'interno del menu **StoreSetup**, dovrai cambiare il servizio **EmailVerificationService** da "Disabled" a "Enabled". 


![Screenshot 2024-08-09 165036](https://github.com/user-attachments/assets/a93a6047-d86f-42cc-9ae6-254eaddb6885)

