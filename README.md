# Assignment 2 - Processo e Sviluppo del Software

## Git URL
https://gitlab.com/bicoccaprojects/2023_assignment2_interview

## Membri del Gruppo

- Claudio Ricci mtr. 918956

- Damiano Ficara mtr. 919386

## Obiettivo dell'Assignment
L'assignment si propone di delineare una strategia volta a raccogliere informazioni cruciali per l'implementazione di un progetto software in fase di sviluppo. Inquadrandoci nell'ambito del requirements engineering, l'attenzione sarà focalizzata sulla comprensione del comportamento che una soluzione software dovrebbe adottare per affrontare un problema specifico. Pertanto, è necessario inizialmente investigare la natura del problema da risolvere al fine di comprenderne il contesto in cui si manifesta.

## Sentiment Analysis su Vulnerabilità Informatiche Project
### System-as-is
Esiste già un sistema che valuta la severità di una vulnerabilità informatica, il sistema CVE, ma questo ha parecchi limiti. Il sistema CVE assegna una valutazione a ogni vulnerabilità tramite il CVE Severity Score, o CVSS, ma non misura l’impatto di una vulnerabilità perché non è nato per questo scopo. Dunque, dati due valori CVSS, non si è in grado di dire quale dei due sia più urgente da gestire. Lo stesso punteggio CVSS può avere un impatto diverso nel tempo, oppure può avere impatti diversi in sistemi diversi.

Inoltre, secondo un rapporto del 2022 pubblicato da FlashPoint (https://www.scmagazine.com/news/half-of-10-0-cvss-vulnerabilities-reported-so-far-in-2022-scored-incorrectly), è emerso che circa la metà delle vulnerabilità considerate più critiche potrebbe essere stata valutata in modo errato. Nel corso degli ultimi 10 anni, si è verificato che in media il 51,5% di tutte le vulnerabilità con un punteggio CVSS di 10.0 non corrispondesse effettivamente a tale valutazione. Ciò implica che le aziende potrebbero dare priorità a centinaia di problemi che non raggiungono il massimo livello di gravità come indicato dal punteggio CVSS. Flashpoint ha condotto un’analisi su 11.860 vulnerabilità relative agli ultimi 10 anni e ha rilevato che il 27,3% di queste vulnerabilità è stato erroneamente segnalato o erroneamente descritto dai servizi CVE.

Questa ricerca evidenzia l’importanza di considerare tali limitazioni e sottolinea la necessità di integrare il sistema CVSS con altre metodologie e valutazioni per ottenere una valutazione più completa e accurata dei rischi di sicurezza. Tale integrazione consentirebbe alle aziende di prendere decisioni informate e prioritarie sulla gestione delle vulnerabilità, andando oltre la valutazione basata esclusivamente sul punteggio CVSS.

### System-to-be
Il sistema che si andrà a sviluppare prende in input un codice CVE (Common Vulnerabilities and Exposures), utilizzato per identificare univocamente una vulnerabilità, e raccoglie da diverse fonti online quali Reddit, Telegram e siti di notizie di settore, contenuti rilevanti rispetto all’input. Successivamente, i contenuti raccolti vengono sottoposti ad un’analisi del sentimento effettuata tramite machine-learning al fine di estrapolare un “indicatore di interesse” relativo alla vulnerabilità in questione. Tale indicatore potrà fornire utili informazioni circa la percezione degli utenti riguardo la gravita e l’importanza della vulnerabilità stessa. Il sistema di sentiment analysis sviluppato, grazie alla sua capacita di analizzare automaticamente numerose fonti di informazioni, fornisce un punteggio sentimentale che riflette l’opinione generale di articoli di settore e degli utenti della comunità della sicurezza informatica su una specifica CVE.
