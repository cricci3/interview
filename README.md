# Assignment 2 - Processo e Sviluppo del Software

## Git URL
https://gitlab.com/bicoccaprojects/2023_assignment2_interview

## Membri del Gruppo

- Claudio Ricci mtr. 918956

- Damiano Ficara mtr. 919386

## Obiettivo dell'Assignment
L'assignment si propone di delineare una strategia volta a raccogliere informazioni cruciali per l'implementazione di un progetto software in fase di sviluppo. Inquadrandoci nell'ambito del requirements engineering, l'attenzione sarà focalizzata sulla comprensione del comportamento che una soluzione software dovrebbe adottare per affrontare un problema specifico. Pertanto, è necessario inizialmente investigare la natura del problema da risolvere al fine di comprenderne il contesto in cui si manifesta.

## Background Study
La cybersecurity rappresenta oggi un tema di grande rilevanza nell’ambito dell’informatica e della tecnologia. Tra le problematiche maggiormente rilevanti si annoverano le vulnerabilità delle applicazioni software, la cui scoperta e correzione costituiscono una priorità per gli sviluppatori e gli esperti di sicurezza.

Nel contesto dell’informatica, il NIST (National Institute of Standards and Technology) definisce una vulnerabilità come una debolezza in un sistema informatico, nelle procedure di sicurezza del sistema, nei controlli interni di questo o nella sua implementazione, che potrebbe essere sfruttata o innescata da una fonte di minaccia.

CVE (Common Vulnerabilities and Exposures) è uno standard di identificazione delle vulnerabilità informatiche utilizzato a livello internazionale per riferirsi a specifici problemi di sicurezza informatica. Il formato del codice CVE, chiamato anche identificatore CVE o CVE ID, `e costituito da un prefisso ”CVE” seguito da un identificatore numerico univoco. 

L’identificatore numerico univoco del codice CVE e importante perchè consente di distinguere la vulnerabilità in questione da tutte le altre vulnerabilità segnalate o scoperte in precedenza o in seguito. Ciò consente ai ricercatori di sicurezza informatica e agli esperti di gestione dei rischi di fare riferimento in modo univoco alla vulnerabilità e di prendere le misure necessarie per mitigare i rischi associati ad essa.

### System-as-is
Esiste già un sistema che valuta la severità di una vulnerabilità informatica, il sistema CVE, ma questo ha parecchi limiti. Il sistema CVE assegna una valutazione a ogni vulnerabilità tramite il CVE Severity Score, o CVSS, ma non misura l’impatto di una vulnerabilità perché non è nato per questo scopo. Dunque, dati due valori CVSS, non si è in grado di dire quale dei due sia più urgente da gestire. Lo stesso punteggio CVSS può avere un impatto diverso nel tempo, oppure può avere impatti diversi in sistemi diversi.

Inoltre, secondo un rapporto del 2022 pubblicato da FlashPoint (https://www.scmagazine.com/news/half-of-10-0-cvss-vulnerabilities-reported-so-far-in-2022-scored-incorrectly), è emerso che circa la metà delle vulnerabilità considerate più critiche potrebbe essere stata valutata in modo errato. Nel corso degli ultimi 10 anni, si è verificato che in media il 51,5% di tutte le vulnerabilità con un punteggio CVSS di 10.0 non corrispondesse effettivamente a tale valutazione. Ciò implica che le aziende potrebbero dare priorità a centinaia di problemi che non raggiungono il massimo livello di gravità come indicato dal punteggio CVSS. Flashpoint ha condotto un’analisi su 11.860 vulnerabilità relative agli ultimi 10 anni e ha rilevato che il 27,3% di queste vulnerabilità è stato erroneamente segnalato o erroneamente descritto dai servizi CVE.

Questa ricerca evidenzia l’importanza di considerare tali limitazioni e sottolinea la necessità di integrare il sistema CVSS con altre metodologie e valutazioni per ottenere una valutazione più completa e accurata dei rischi di sicurezza. Tale integrazione consentirebbe alle aziende di prendere decisioni informate e prioritarie sulla gestione delle vulnerabilità, andando oltre la valutazione basata esclusivamente sul punteggio CVSS.

### System-to-be
Il sistema che si andrà a sviluppare prende in input un codice CVE e raccoglie da diverse fonti online contenuti rilevanti rispetto all’input. Successivamente, i contenuti raccolti vengono sottoposti ad un’analisi del sentimento effettuata tramite machine-learning al fine di estrapolare un “indicatore di interesse” relativo alla vulnerabilità in questione. Tale indicatore potrà fornire utili informazioni circa la percezione degli utenti riguardo la gravita e l’importanza della vulnerabilità stessa. Il sistema di sentiment analysis sviluppato, grazie alla sua capacità di analizzare automaticamente numerose fonti di informazioni, fornisce un punteggio sentimentale che riflette su una specifica CVE.

## Elicitation Strategy
### Stakeholders
- Secuirty Specialist, esperto di sicurezza informatica che monitora e raccoglie informazioni sulle vulnerabilità informatiche (CVE) 

- Software Engineer, sviluppatore software con competenze su NLP e Sentiment Analysis

- Security Manager, persona che gestisce un reparto di Secuirty Specialist

- Cybersecurity community, comunità online della Cybersecurity

### Workflow
<div align="center">
  <img src="Workflow.png" alt="Image" width="300"/>
</div>

1. Intervista a security specialist contribuisce all'analisi del contesto di sicurezza del progetto. Offre un'expertise specifica sulla sicurezza informatica.

2. Intervista a software engineer apporta conoscenze su come sviluppare il progetto di sentiment analysis e fornisce input sulle tecniche di intelligenza artificiale più adatte per l'analisi delle informazioni sulle CVE. Il Software Developer con Competenze in AI contribuisce alla progettazione dell'analisi dei sentimenti attraverso l'intelligenza artificiale.

3. Intervista a security manager può fornire un punto di vista strategico sulla necessità di investire in un tool di ricerca di informazioni automatico. La sua esperienza nel coordinare il reparto di sicurezza può essere preziosa per valutare l'efficacia e la rilevanza di strumenti automatizzati. Il Security Manager può influenzare la decisione sull'adozione di strumenti automatici basandosi sulla sua esperienza nella gestione della sicurezza.

4. Il questionario alla community della Cyber security può fornire un feedback sul tool che si vuole andare a sviluppare.
