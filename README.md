Pytho_33_Tut
============

Traduzione python tutorial 3.3.0


Questo è il primo progetto per vedere se è fattibile utilizzare omegat per tradurre il tutorial di python 3.3.0 e collegarlo con git.
Per ora ciò che ho usato è stato:

Aquisizione Documentazione
==========================
1) Download della documentazione in html http://docs.python.org/3/archives/python-3.3.0-docs-html.zip

2) Prelevato dalla decompressione dell'archivio delle directory _sources _static e tutorial, le prime due le ho ricompresse perché non dovranno essere tradotte ma serviranno solo a quando sarà finita la traduzione per migliorare la visualizzazione del tutorial


Creazione Progetto Omegat
=========================
1) Scaricato il programma da questo link e decompresso http://sourceforge.net/projects/omegat/files/OmegaT%20-%20Latest/OmegaT%202.6.1%20update%201/OmegaT_2.6.1_01_Beta_Without_JRE.zip/download


2) Avviato con questo comando per vederlo in italiano: java -Duser.language=it -jar OmegaT.jar &

3) Creato il nuovo progetto com menu->progetto->nuovo... , determinato il nome e la directory del nuovo progetto e selezionate le lingue di partenza e di arrivo prima di confermare

4) Selezionato menu->vista->evidenzia i segmeni non tradotti per visualizzare ciò che non si è tradotto

5) Selezionato menu->Opzioni->Comportamento di modifica scegliando "lascia il segmento vuoto" e "permetti traduzione uguale all'originale" per rendere più confortevole la traduzione

6) Chiusura del programma, copia dei file sorgente (tutorial e le altre due directory compresse) nella directory scelta per il progetto di omegat dentro la sottodirectory "source"

7) Riavviando il programma si noterà il caricamento di questi file.


Creazione Repository Git
========================
1) Dopo aver installato git, con un terminale al suo interno ho scritto:

$ git config --global user.name "vinniec" (impostato il mio nick)
$ git config --global user.email fz12345@gmail.com (impostata la mia email)

$ export GIT_SSL_NO_VERIFY=false (pare che se non si modifica questa variabile d'ambiente git non riesca ad utilizzare https), in alternativa si può usare il comando $ git config http.sslVerify "false"
La cosa migliore è comunque mettere nel file ~/.gitconfig il testo:
[http]
	sslverify = false


(nota per tinycore, SCM, git normale non funziona, ssh chiede chiavi pubbliche e quindi è meglio utilizzare https)
$ git clone https://github.com/vinniec/Pytho_33_Tut.git (scarica i file del git)
$ cd ./Pytho_33_Tut/ (si dirige nel repo)

copio tutti i file della traduzione (tutorial e lo zip) più questo readme, le directory vuote non vengono caricate sul server, per cui la prima volta che si caricano queste directory vuote bisognerà inserire al loro interno dei file chiamati .gitignore al loro interno contenenti
 # Ignore everything in this directory
 *
 # Except this file
 !.gitignore
questi file andranno rimossi quando verranno riempite le directory tramite il comando /apps/git/bin/git rm ./dir/.gitignore ./dir/.gitignore e poi andrà fatto un commit nuovo, se li si cancella con le directory ancora vuote queste verranno cancellate al prossimo push!

$ git status (controllo tutte le nuove modifiche)
$ git add . (per inserire tutti i file della cartella nel repository git)
$ git commit -m "progetto di traduzione iniziale" (x commentare questo add)
$ /apps/git/bin/git push origin master (carica i file sul server)


Salvare dopo aver fatto le modifiche
====================================
Omegat pare supportare il downlaod e l'upload verso git però utilizza la libreria jgit che a sua volta si avvale solo di ssh per il login e per questo motivo io sono punto e accapo, per cui se non si utilizza ssh per questioni di chiavi di riconoscimento allora conviene scaricare a mano da git con il comando git clone https... perchè se lo si fa da omegat allora questo non riuscirà ad aggiornare.

Una volta modificato i file quindi bisognerà sempre salvare a mano le modifiche con i seguenti comandi:
1) git add . (per aggiungere tutti i nuovi file)
2) git commit -m "messaggio che spiega i cambiamenti"
3) git push origin master (per caricare sul server)

E probabilmente bisogna scaricare ogni volta che si inizia a tradurre


Risorse
=======
Un ottima guida per git è questa http://git-scm.com/book/it , anche questo sembra carino http://rogerdudler.githhtthttp://git-scm.com/book/itp://git-scm.com/book/itub.com/git-guide/index.it.html

I dizionari li ho presi da quì http://linguistico.sourceforge.net/pages/start.html , più precisamente i file .add e .dic in
http://prdownloads.sourceforge.net/linguistico/italiano_2_4_2007_09_01.zip?download


Caricamento repository git da Omegat
====================================
#sconsigliato a causa dell'impossibilità di salvare
1) menu->Progetto->Scarica il Progetto in collaborazione
scelgo git
Url Deposito: https://github.com/vinniec/Pytho_33_Tut.git
Cartella Locale: /home/tc/PROVA/Pytho_33_Tut

2)Attendo che scarichi e quando esce la finestra dei file da tradurre e seleziono  quello che mi interessa (si inizia da index.html), e poi chiudo questa finestra

3)Posso iniziare a tradurre, se faccio doppioclick su un capoverso mi fa iniziare a scrivere (i capoversi non tradotti dovrebbero essere blu e quando iniziamo a tradurre il segmento corrente dovrebbe essere vuoto, se abbiamo settato omegat come dicevamo prima)
