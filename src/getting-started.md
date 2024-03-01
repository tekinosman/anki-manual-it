# Per iniziare

<!-- toc -->

## Installazione e aggiornamento

Consulta le istruzioni per il tuo computer:

- [Windows](./platform/windows/installing.md)
- [Mac](./platform/mac/installing.md)
- [Linux](./platform/linux/installing.md)

## Video

Per una rapida immersione in Anki, dai un'occhiata ai seguenti
video introduttivi. Alcuni sono stati realizzati per versioni precedenti
di Anki, ma i concetti restano gli stessi.

- [Mazzi condivisi e nozioni di basi sulla revisione (inglese)](http://www.youtube.com/watch?v=QS2G-k2hQyg&yt:cc=on)

- [Sincronizzazione (inglese)](https://www.youtube.com/watch?v=YkiM4DPzSVc&list=PLGgmaKOIHykFoomqkBJAyGiDQ2kyiuTao&yt:cc=on)

- [Modificare l'ordine delle carte (inglese)](http://www.youtube.com/watch?v=DnbKwHEQ1mA&yt:cc=on)

- [Personalizzare lo stile delle carte (inglese)](http://www.youtube.com/watch?v=F1j1Zx0mXME&yt:cc=on)

- [Digitare una risposta (inglese)](http://www.youtube.com/watch?v=5tYObQ3ocrw&yt:cc=on)

Se YouTube non è disponibile, puoi invece scaricare i video [qui](https://apps.ankiweb.net/downloads/archive/screencasts/2.0/).

## Concetti chiave

### Carte

Una coppia di domanda e risposta è chiamata "carta" e si basa sul concetto
di una carta fisica con la domanda su un lato e la risposta sull'altro.
In Anki, però, le carte non sono come le carte fisiche e,
quando ti viene mostrato il lato della risposta, la domanda rimane visibile
per impostazione predefinita. Ad esempio, se stai studiando le basi
della chimica, potresti avere una domanda come:

    D: Simbolo chimico dell'ossigeno?

Dopo averci pensato e aver deciso che la risposta è O, puoi decidere
di cliccare sul pulsante di risposta. A quel punto ti verrà mostrato:

    D: Simbolo chimico dell'ossigeno?
    R: O

Dopo aver confermato la correttezza della tua risposta, puoi indicare
ad Anki quanto bene ricordi la risposta, e Anki sceglierà il momento
in cui mostrartela nuovamente.

#### Tipologie di carta

- **Nuova:** Carta che hai scaricato o creato, ma che non hai ancora
studiato.

- **In apprendimento:** Carta vista per la prima volta di recente e ancora
in fase di apprendimento.

- **Di ripasso:** Carta che ha superato la fase di apprendimento
e che necessita di essere ripassata per non essere dimenticata.
Questa tipologia si distingue in:
    - **Giovane:** Carta con un intervallo inferiore a 21 giorni,
    ma non in fase di apprendimento.
    - **Matura:** Carta con un intervallo di 21 giorni o superiore.

- **Riapprendimento:** Carta che hai sbagliato in modalità di ripetizione,
tornando quindi in modalità di riapprendimento per essere riappresa.

### Mazzi

Un "mazzo" è un gruppo di carte. Puoi organizzare le carte in diversi mazzi
per studiarne una parte anziché tutte insieme. Ciascun mazzo può avere
impostazioni diverse, come ad esempio il numero di carte nuove da mostrare
ogni giorno o l'intervallo di tempo da attendere
prima di ripresentare le carte.

Un mazzo può contenere altri mazzi, permettendoti di organizzarli
in una struttura ad albero. Anki utilizza "::" per separare
i diversi livelli. Ad esempio, un mazzo chiamato "Cinese::Hanzi"
si riferisce a un mazzo "Hanzi" contenuto all'interno del mazzo "Cinese".
Se selezioni "Hanzi", vedrai solo le carte Hanzi; se selezioni "Cinese",
vedrai tutte le carte cinesi, incluse quelle Hanzi.

Per inserire un mazzo all'interno di un altro, puoi utilizzare "::"
nel suo nome oppure trascinarlo e rilasciarlo dall'elenco dei mazzi.
Il mazzo nidificato sotto un altro (quindi quello che ha almeno un "::"
nel nome) è spesso chiamato "sottomazzo", mentre il mazzo
di livello superiore a volte è definito "mazzo principale" o "mazzo padre".

Anki include un mazzo iniziale chiamato "Predefinito"; qualsiasi carta
che per qualche motivo si è separata dagli altri mazzi finirà qui.
Se tale mazzo non contiene carte e hai aggiunto altri mazzi, Anki
lo nasconderà. In alternativa, puoi rinominare questo mazzo
e utilizzarlo per altre carte.

I mazzi sono visualizzati nell'elenco dei mazzi in ordine alfabetico.
Questo può risultare in un ordine inaspettato se i mazzi
contengono numeri: ad esempio, "Mazzo 10" verrà prima di "Mazzo 9",
poiché 1 precede 9. Se desideri numerare i tuoi mazzi,
puoi aggiungere uno "0" davanti ai numeri a cifra singola,
ottenendo "Mazzo 01", "Mazzo 02" ... "Mazzo 10".

I mazzi sono più adatti a contenere categorie ampie di carte, piuttosto che
argomenti specifici come "verbi della cucina" o "lezione 1".
Se vuoi approfondire, consulta la sezione
[utilizzo appropriato dei mazzi]( editing.md#using-decks-appropriately).

Per informazioni su come i mazzi influiscono sull'ordine
di visualizzazione delle carte, consulta
la sezione [ordine di presentazione](studying.md#ordine-di-presentazione).

### Note e campi

Quando crei una carta, spesso è desiderabile crearne più di una
per la stessa informazione.
Ad esempio, se stai studiando il francese e scopri che la parola "bonjour"
significa "ciao", potresti voler creare una carta che mostra "bonjour"
e ti chiede di ricordare "ciao", e un'altra carta che mostra "ciao"
e ti chiede di ricordare "bonjour". La prima carta testa la tua capacità
nel riconoscere la parola straniera, mentre la seconda testa
la tua capacità nel produrla.

Con le carte fisiche, l'unica opzione è scrivere le informazioni due volte
su ogni carta. Alcuni programmi di carte per computer semplificano la vita
permettendoti di capovolgere il lato anteriore e posteriore.
Questo è un miglioramento rispetto alla situazione su carta,
ma tale sistema presenta due svantaggi principali:

- Poiché tali programmi non tracciano separatamente le tue
prestazioni di riconoscimento e produzione, le carte tenderanno
a non esserti mostrate nel momento ottimale, portandoti a dimenticare
più di quanto vorresti o a studiare più del necessario.

- Invertire la domanda e la risposta funziona solo quando il contenuto
è lo stesso su entrambi i lati. Ciò significa che non è possibile mostrare
informazioni aggiuntive sul retro.

Anki risolve questi problemi consentendoti di dividere il contenuto
delle carte in parti diverse. Puoi specificare quali informazioni
vuoi avere su ciascuna carta e Anki si occuperà di creare le carte
e aggiornarle se apporterai modifiche in futuro.

Supponiamo di voler studiare il lessico francese e includere
il numero della pagina sul retro di ciascuna carta. Vogliamo che
le nostre carte siano simili a questa:

    D: Bonjour
    R: Buongiorno
       Pagina #12

E:

    D: Buongiorno
    R: Bonjour
       Pagina #12

In questo esempio, abbiamo tre informazioni correlate: il termine francese,
il significato in italiano e il numero della pagina.
Se le mettessimo insieme, si presenterebbero come segue:

    Francese: Bonjour
    Italiano: Buongiorno
    Pagina: 12

In Anki, queste informazioni correlate vengono chiamate "nota",
e ciascuna informazione è chiamata "campo".
In questo caso, il tipo di nota ha tre campi: Francese, Italiano e Pagina.

Per aggiungere e modificare i campi, clicca sul pulsante "Campi..."
durante l'aggiunta o la modifica delle note.
Per ulteriori informazioni sui campi,
consulta la sezione [Personalizzazione dei campi](editing.md#customizing-fields).

### Tipi di carta

Per far sì che Anki crei delle carte basate sulle nostre note,
è necessario fornirgli un modello che indichi quali campi devono
essere mostrati sul lato anteriore e posteriore di ciascuna carta.
Questo modello è conosciuto come "tipo di carta".
Ciascun tipo di nota può avere uno o più tipi di carta;
quando aggiungi una nota, Anki creerà una carta per ogni
tipo di carta associato.

Ciascun tipo di carta ha due "modelli", uno per la domanda e uno per
la risposta. Nell'esempio francese di cui sopra, volevamo che la carta
di riconoscimento apparisse così:

    D: Bonjour
    R: Buongiorno
       Pagina #12

Per ottenere questo risultato, possiamo configurare i modelli per
la domanda e la risposta come segue:

    D: {{Francese}}
    R: {{Italiano}}<br>
       Pagina #{{Pagina}}

Racchiudendo il nome di un campo tra doppie parentesi graffe,
diciamo ad Anki di sostituirlo con il valore effettivo del campo.
Tutto ciò che non è racchiuso tra parentesi graffe rimane invariato.
Non è necessario digitare "Pagina #" nel campo Pagina
quando si aggiunge del materiale, in quanto viene aggiunto automaticamente
a ogni carta. "<br>" è un codice speciale che dice ad Anki
di andare a capo; per approfondire consulta la sezione [modelli](templates/intro.md).

I modelli per le carte di produzione funzionano in maniera analoga:

    D: {{Inglese}}
    R: {{Francese}}<br>
       Pagina #{{Pagina}}

Una volta creato un tipo di carta, quando aggiungi una nuova nota,
verrà creata una carta basata su quel tipo di carta. I tipi di carta
consentono di mantenere una formattazione coerente delle carte
e possono ridurre notevolmente lo sforzo necessario
per aggiungere informazioni.
Inoltre, permettono ad Anki di evitare che le carte correlate
appaiano troppo vicine tra loro e ti permettono di correggere un errore
di battitura o un errore fattuale una sola volta e di aggiornare
tutte le carte correlate contemporaneamente.

Per aggiungere e modificare i tipi di carta, clicca sul pulsante "Carte..."
durante l'aggiunta o la modifica delle note. Per ulteriori informazioni
sui tipi di carta, consulta la sezione [Carte e modelli](templates/intro.md).

### Tipi di nota

Anki consente di creare diversi tipi di note per diversi tipi di materiale.
Ogni tipo di nota ha il proprio set di campi e tipi di carta.
È consigliabile creare un tipo di nota separato per ciascun argomento
generale che stai studiando. Nell'esempio francese precedente,
potremmo creare un tipo di nota chiamato "Francese" e,
se volessimo imparare le capitali, potremmo creare un tipo di nota separato
con campi come "Paese" e "Capitale".

Quando Anki controlla i duplicati, confronta solo le altre note
dello stesso tipo. Pertanto, se aggiungi una capitale chiamata "Arancione"
utilizzando il tipo di nota "Capitale", non vedrai un messaggio di duplicato
quando verrà il momento di imparare a dire "Arancione" in francese.

Quando crei una nuova collezione, Anki aggiunge automaticamente alcuni tipi
di nota standard. Questi tipi di nota sono forniti
per facilitarel'utilizzo di Anki per i nuovi utenti, ma nel lungo termine
è consigliato creare i propri tipi di nota per il contenuto
che stai imparando. I tipi di nota standard sono:

- **Basilare**\
  Contiene i campi Fronte e Retro e crea una carta. Il testo inserito
  in Fronte apparirà sul lato fronte della carta e il testo inserito
  in Retro apparirà sul retro della carta.

- **Basilare (e carta inversa)**\
  Come Basilare, ma crea due carte per lo stesso testo: una fronte→retro
  e una retro→fronte.

- **Basilare (carta inversa opzionale)**\
  Si tratta di una carta fronte→retro e, facoltativamente,
  di una carta retro→fronte. Presenta un terzo campo
  chiamato "Aggiungi inversa". Se inserisci del testo in quel campo,
  verrà creata una carta inversa. Maggiori informazioni sono disponibili
  nella sezione [Carte e modelli](templates/intro.md).

- **Basilare (digita la risposta)**\
  Simile a Basilare, ma con una casella di testo aggiuntiva sul lato fronte
  in cui puoi digitare la risposta. Quando mostri il retro della carta,
  il tuo input verrà controllato e confrontato con la risposta.
  Maggiori informazioni sono disponibili
  nella sezione [Controlla la risposta](templates/fields.md#checking-your-answer).

- **Cloze**\
  Permette di selezionare una parte del testo e trasformarla in una
  cancellazione Cloze (esempio: "L'uomo è sbarcato sulla luna
  nel \[…​\]" → "L'uomo è sbarcato sulla luna nel 1969").
  Maggiori informazioni sono disponibili nella sezione [Cancellazione cloze](editing.md#cloze-deletion).

- **Occludi Immagine**\
  Simile al tipo di nota Cloze, ma usa le immagini invece del testo,
  particolarmente utile quando si studia materiale basato su immagini,
  come anatomia, geografia e altro. Per approfondire,
  consulta la sezione [Occlusione immagine](editing.md#image-occlusion). 

Per aggiungere nuovi tipi di nota e modificare quelli esistenti,
vai su Strumenti → Gestisci i tipi di nota dalla schermata principale
di Anki.

Note e tipi di nota sono comuni a tutta la tua collezione e non limitati
a un singolo mazzo. Ciò significa che puoi utilizzare diversi tipi di nota
in un particolare mazzo o avere diverse carte generate
da una particolare nota in mazzi diversi. Quando aggiungi una nota
attraverso la schermata Aggiungi, puoi scegliere
quale tipo di nota utilizzare e in quale mazzo inserire la nota,
e queste scelte sono completamente indipendenti l'una dall'altra.
Puoi anche modificare il tipo di nota di alcune note [dopo averle create](browsing.md).

### Collezione

Una "collezione" è l'insieme del materiale archiviato in Anki: carte,
note, mazzi, tipi di nota, opzioni del mazzo e così via.

## Mazzi condivisi

Su Youtube puoi trovare
[un video sul concetto di mazzi condivisi e basi sulla ripetizione](http://www.youtube.com/watch?v=QS2G-k2hQyg&yt:cc=on) (inglese).

Il modo più semplice per iniziare con Anki è quello di scaricare
un mazzo di carte condiviso da qualcuno:

1. Clicca sul pulsante "Ottieni mazzi condivisi" in fondo
alla lista dei mazzi.

2. Trova un mazzo che ti interessa, quindi clicca sul pulsante "Download"
per scaricare il pacchetto del mazzo.

3. Fai doppio clic sul pacchetto scaricato per caricarlo in Anki, oppure
vai su File→Importa per importarlo.

Tieni presente che al momento non è possibile aggiungere mazzi condivisi
direttamente su AnkiWeb. Devi prima importarli usando la versione di Anki
per computer, quindi sincronizzare per caricarli su AnkiWeb.

Creare il proprio mazzo è il modo più efficace per imparare
una materia complessa. Materie come le lingue e le scienze non possono
essere comprese semplicemente memorizzando dei fatti,
ma richiedono spiegazioni e contesto per apprenderle in maniera efficace.
Inoltre, creare carte tu stesso ti costringe a decidere quali sono
i punti chiave, favorendo così una migliore comprensione.

Se sei uno studente di lingue, potresti essere tentato di scaricare
una lunga lista di parole e delle loro traduzioni corrispondenti,
ma questo non ti insegnerà la lingua tanto quanto memorizzare
equazioni scientifiche ti insegnerà l'astrofisica.
Per imparare correttamente, hai bisogno di libri, insegnanti
o dell'esposizione a frasi del mondo reale.

    Do not learn if you do not understand (non imparare se non capisci).
    --SuperMemo

La maggior parte dei mazzi condivisi sono creati da persone
che apprendono il materiale al di fuori di Anki – da libri, lezioni, TV, ecc.
Selezionano gli aspetti interessanti di ciò che imparano e li aggiungono
ad Anki. Non si sforzano di aggiungere il contesto o spiegazioni alle carte,
perché già comprendono l'argomento. Di conseguenza, quando qualcun altro
scarica il loro mazzo e cerca di usarlo, lo troverà molto difficile a causa
della mancanza di contesto e spiegazioni.

Questo non significa che i mazzi condivisi siano inutili, ma semplicemente
che per materie complesse dovrebbero essere utilizzati come "integrazione"
al materiale esterno, non come "sostituto". Se stai studiando il libro ABC
e qualcuno ha condiviso un mazzo di idee di idee provenienti da tale libro,
questo è un ottimo modo per risparmiare tempo. Per materie semplici
che sono fondamentalmente una lista di fatti, come i nomi delle capitali
o i quiz di cultura generale, probabilmente non hai bisogno
di materiale esterno. Se però provi a studiare argomenti complessi
senza materiale esterno, otterrai probabilmente risultati deludenti.
