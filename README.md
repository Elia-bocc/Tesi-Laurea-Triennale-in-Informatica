# Tesi Laurea Triennale in Informatica Pisa febbraio 2024

## Abstract

In questo lavoro di tesi sono state esplorate differenti tecniche di estrazione di entità nominate
in due domini affini, malattie e sport, con la finalit`a di generare, attraverso la
combinazione delle due migliori tecniche, un nuovo strumento di elaborazione di testi
biomedico-sportivi, utile per ulteriori studi sulle relazioni multi-dominio (malattie e sport
in questo caso).

Lo studio è stato effettuato su un dataset composto da 150 articoli biomedici, estratti appositamente
da pubMed utilizzando l’API E-Utilities, la quale permette di effettuare una
ricerca avanzata multi-keyword. Di questi, ne sono stati selezionati 50 riguardanti solo
malattie, 50 solamente sport e i restanti 50 riguardanti entrambi i domini.
L’elaborazione degli articoli è consistita nell’estrazione di entità nominate (sport e malattie)
tramite quattro tecniche: per quanto riguarda l’estrazione di malattie è stato utilizzato
un pipeline di Spacy ed un transformers fine-tuned model di bioBERT specializzati
in ambito biomedico, mentre per gli sport, l’estrazione è stata effettuata facendo prompting
su un instruct-following model non adattato e facendo semplice pattern matching tramite
una baseline, creata appositamente, composta da nomi di sport.
Allo scopo di valutare i metodi, sono stati annotati manualmente gli abstract precedentemente
processati e, dal confronto tra le annotazioni “gold” e le estrazioni effettuate, sono
state calcolate recall, precision e f1-score. Infine, dopo aver valutato i metodi ed averne
identificati i due migliori, è stata effettuata l’estrazione combinata, dando origine al nuovo
metodo di estrazione multi-dominio.

## Propositi e contributi

Questo nuovo metodo costituisce la base di partenza per mettere appunto un metodo più efficiente
e, oltre ad essere un importante strumento di elaborazione di testi medico-sportivi in grado
di estrarre informazioni come entità nominate, potrebbe essere utile per sviluppare un metodo di
identificazione delle relazioni tra le entità estratte (relation extraction).
In generale un identificatore di relazioni permetterebbe di studiare relazioni multi-dominio e, in
questo caso, si potrebbe indagare sull’esistenza di influenze negative dirette tra uno sport ed una
malattia specifica, oppure se un particolare sport può essere utile alla cura di una malattia, oltre
anche alla possibilità di effettuare varie indagini statistiche.
In aggiunta alla creazione di questo metodo, questo lavoro mette a disposizione una baseline composta
da nomi di sport in lingua inglese ed un piccolo dataset annotato per entità medico-sportive,
che possono essere utilizzati per sviluppare e testare nuovi metodi e modelli.


## Datasets

Da questo lavoro sono stati prodotti dei piccoli datasets annotati manualmente:
  - disease.csv contiene articoli (e annotazioni) relativi alle malattie
  - sport.csv contiene articoli (e annotazioni) relativi agli sport
  - sport_disease contiene articoli (e annotazioni) relativi sia a malattie che sport
