Pytho_33_Tut
============

Traduzione python tutorial 3.3.0


Questo è il primo progetto per vedere se è fattibile utilizzare omegat per tradurre il tutorial di python 3.3.0 e collegarlo con git.
Per ora ciò che ho usato è stato:

Documentazione
==============
1) Download della documentazione in html http://docs.python.org/3/archives/python-3.3.0-docs-html.zip

2) Prelevato dalla decompressione dell'archivio delle directory _sources _static e tutorial, le prime due le ho ricompresse perché non dovranno essere tradotte ma serviranno solo a quando sarà finita la traduzione per migliorare la visualizzazione del tutorial


Omegat
======
1) Scaricato il programma da questo link e decompresso http://sourceforge.net/projects/omegat/files/OmegaT%20-%20Latest/OmegaT%202.6.1%20update%201/OmegaT_2.6.1_01_Beta_Without_JRE.zip/download


2) Avviato con questo comando per vederlo in italiano: java -Duser.language=it -jar OmegaT.jar &

3) Creato il nuovo progetto com menu->progetto->nuovo... , determinato il nome e la directory del nuovo progetto e selezionate le lingue di partenza e di arrivo prima di confermare

4) Selezionato menu->vista->evidenzia i segmeni non tradotti per visualizzare ciò che non si è tradotto

5) Selezionato menu->Opzioni->Comportamento di modifica scegliando "lascia il segmento vuoto" e "permetti traduzione uguale all'originale" per rendere più confortevole la traduzione

6) Chiusura del programma, copia dei file sorgente (tutorial e le altre due directory compresse) nella directory scelta per il progetto di omegat dentro la sottodirectory "source"

7) Riavviando il programma si noterà il caricamento di questi file.


Git
===
1) Con un terminale al suo interno ho scritto:
git config --global user.name "vinniec" (impostato il mio nick)
$ git config --global user.email fz12345@gmail.com (impostata la mia email)
#SCM, git normale non funziona, ssh chiede chiavi pubbliche e quindi è meglio https
$ /apps/git/bin/git clone https://github.com/vinniec/Pytho_33_Tut.git
$ cd ./Pytho_33_Tut/ (si dirige nel repo)
copio tutti i file della traduzione (tutorial e lo zip) più questo readme
$ git status (controllo tutte le nuove modifiche)
$ git add . (per inserire tutti i file della cartella nel repository git)
$ git commit -m "progetto di traduzione iniziale" (x commentare questo add)
$ /apps/git/bin/git push origin master (carica i file sul server)


