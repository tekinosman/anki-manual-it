# File di testo

<!-- toc -->

Anki può importare qualsiasi file di **testo semplice** contenente campi separati da virgole, punti e virgola o tabulazioni, purché siano soddisfatte alcune condizioni.

- I file devono essere puramente testuali (miofile.txt). Altri formati come
  miofile.xls, miofile.rtf, miofile.doc devono essere prima salvati prima come
  file di testo semplice. 

- I file devono essere codificati nel formato UTF-8 (vedi sotto).

- La prima riga definisce anche il carattere di separazione: se Anki trova
  un punto e virgola (;) nella prima riga userà quello, se trova una virgola (,)
  userà quella, ecc.

- Anki determina il numero di campi nel file analizzando la prima riga _non commentata_.
  Se alcune delle righe successive contengono un numero inferiore di campi, Anki considera quelli mancanti come vuoti. Se alcune righe contengono campi aggiuntivi, il contenuto extra non viene importato.

I campi del file di testo possono essere mappati a qualsiasi campo delle tue note, incluso il campo delle etichette. Durante l'importazione è possibile scegliere quale campo del file di testo corrisponde ad uno specifico campo della nota.

Quando importi un file di testo, puoi scegliere in quale mazzo inserire le carte. Tieni presente, però, che se hai abilitato l'opzione di sovrascrittura del mazzo per uno o più dei tuoi modelli, le carte verranno inserite in quel mazzo specifico anziché in quello selezionato durante l'importazione.

Questo è un esempio di un file valido avente tre campi:

    mela;banana;uva
    del testo;altro testo;ancora più testo

Ci sono due modi per includere righe a capo o il separatore di campo stesso, all'interno dei campi.

**Delimitare il contenuto del campo con le virgolette**:

    ciao;"questa è
    una risposta su due righe"
    due;questo è un campo su una riga
    "questo include ; (punto e virgola)";un altro campo

Poiché le virgolette delimitano l'inizio e la fine di un campo, se desideri inserirle all'interno del campo stesso, devi sostituire ogni singola virgoletta con due virgolette per "escluderle" dall'interpretazione predefinita, come mostrato nel seguente esempio:

    campo uno;"campo due con ""virgolette doppie"" al suo interno"

Quando utilizzi un programma di fogli di calcolo come LibreOffice per creare il file CSV, questo si occupa automaticamente di codificare correttamente le virgolette.

**Utilizzare il tag HTML &lt;br&gt;**:

    ciao; questa è<br>una risposta su due righe
    due; questa è una riga unica

Per abilitare le interruzioni di riga HTML, devi spuntare la casella "Consenti l'HTML nei campi" nella finestra di dialogo di importazione.

Le righe multiple correttamente codificate non funzionano correttamente se utilizzi eliminazioni cloze
su più righe. In questo caso, è necessario usare le interruzioni di riga HTML.

Puoi anche includere le etichette in un altro campo e selezionarli come campo delle etichette nel dialogo di importazione:

    primo campo;secondo campo;etichette

Questo è un esempio di un file valido, in cui la prima riga è ignorata (\#):

    # questo è un commento ed è ignorato
    pippo pluto;pluto paperino;paperino quaquo
    campo1;campo2;campo3

## Fogli di calcolo e UTF-8

Se il tuo file contiene caratteri non latini (come gli accenti, il giapponese ecc.), Anki si aspetta che sia salvato con la codifica "UTF-8". Il modo più semplice per farlo è quello di utilizzare il programma gratuito LibreOffice Calc al posto di Excel per modificare il file, poiché supporta facilmente UTF-8 e, a differenza di Excel, esporta correttamente i contenuti multi-riga. Se invece preferisci continuare a utilizzare Excel, consulta [questo post del forum](https://docs.google.com/document/d/12YE_FS6A9ANLTESJNtPP116ti4nNmCBghyoJBRtno_k/edit?usp=sharing) (inglese) per maggiori informazioni.

Per salvare il tuo foglio di calcolo in un file che Anki possa leggere, usando LibreOffice, vai su File&gt; Salva con nome e quindi seleziona CSV come tipo di file. Dopo aver accettato le opzioni predefinite, LibreOffice salverà il file e potrai quindi importarlo in Anki.

## HTML

Anki può interpretare il testo importato da file testuali come HTML (il linguaggio usato per le pagine web). Ciò significa che il testo in grassetto, corsivo e altre formattazioni può essere esportato in un file di testo e successivamente reimportato. Se desideri includere la formattazione HTML, puoi spuntare la casella "Consenti HTML nei campi" durante l'importazione. È però consigliato disattivare questa opzione se stai cercando di importare carte che contengono parentesi uncinate (&lt;&gt;) o altra sintassi HTML.

If you wish to use HTML for formatting your file but also wish to
include angle brackets or ampersands, you may use the following replacements:

Se vuoi utilizzare l'HTML per formattare il tuo file, ma devi anche includere le parentesi uncinate, puoi usare le seguenti sostituzioni:

| Carattere | Sostituzione |
| --------- | ----------- |
| &lt;      | `&lt;`      |
| &gt;      | `&gt;`      |
| &amp;     | `&amp;`     |

## Importazione di file multimediali

Se vuoi includere audio e immagini durante l'importazione da un file di testo, devi copiare i file nella [cartella collection.media](../files.md). **Non creare sottocartelle all'interno della cartella "media", poiché potrebbe causare malfunzionamenti.**

Dopo aver copiato i file, modifica uno dei campi nel tuo file di testo come segue:

    <img src="miaimmagine.jpg">

oppure

    [sound:mioaudio.mp3]

Alternativamente, puoi utilizzare la funzionalità [Trova e sostituisci](../browsing.md) nella schermata "Sfoglia" per aggiornare tutti i campi contemporaneamente. Se ciascun campo contiene testo come "mioaudio" e vuoi che riproduca un suono, puoi cercare (.\*) e sostituirlo con "\[sound:\\1.mp3\]", avendo l'accortezza di abilitare l'opzione 'Considera l'immissione come espressione regolare'.

When importing a text file with these references, you must make sure to
enable the "Allow HTML" option.

Quando importi un file testuale con tali riferimenti, assicurati di abilitare l'opzione "Consenti HTML".

You might be tempted to do this in a template, like:

Potresti essere tentato di fare ciò in un modello, come per esempio:

    <img src="{{nome del campo}}">

Tuttavia Anki non lo supporta per due motivi: la ricerca dei media è dispendiosa, in quanto ogni singola carta deve essere elaborata, e tale funzionalità non è ovvia per gli utenti dei mazzi condivisi. Utilizza invece la tecnica del "Trova e sostituisci".

## Importazione in massa di file multimediali

Un'altra opzione per importare grandi quantità di file multimediali in una volta sola è quella di usare l'[add-on per l'importazione dei file multimediali](https://ankiweb.net/shared/info/1531997860). Questo add-on crea automaticamente delle note per tutti i file presenti in una cartella selezionata, con i nomi dei file sul fronte (senza l'estensione del file, per cui se hai un file chiamato "mela.jpg", il fronte riporterà la dicitura "mela") e le immagini o l'audio sul retro. Se desideri una disposizione diversa dei file multimediali e dei nomi dei file, puoi successivamente [cambiare il tipo di nota](../browsing.md) delle carte create.

## Aggiunta di etichette

Se vuoi aggiungere le etichette "etichetta1" ed "etichetta2" a ogni riga che importi, inserisci quanto segue all'inizio del file testuale:

    tags:etichetta1 etichetta2

## Duplicati e aggiornamento

Durante l'importazione di file di testo, Anki utilizza il primo campo per determinare
se una nota è unica. Per impostazione predefinita, se il file da importare contiene un primo campo
che corrisponde a una delle note già presenti nella tua collezione e la nota esistente
è dello stesso tipo di quella che stai importando, tutti gli altri campi della nota esistente
vengono aggiornati in base al contenuto del file importato. Un menù a tendina
nella schermata di importazione ti consente di modificare questo comportamento, dandoti la possibilità di
ignorare completamente i duplicati o di importarli come nuove note
invece di aggiornare quelle esistenti.

L'opzione "Ambito di corrispondenza" determina come vengono identificati i duplicati. Quando è impostata al valore "Tipo di nota", Anki identifica un duplicato se un'altra nota dello stesso tipo ha lo stesso primo campo. Quando invece è impostata al valore "Tipo di nota e mazzo", un duplicato viene segnalato soltanto se la nota esistente si trova anche nel mazzo in cui la stai importando.

Se hai abilitato l'aggiornamento e nella collezione sono già presenti versioni precedenti delle note che stai importando, queste vengono aggiornate nella loro posizione originale (nei loro mazzi attuali) anziché essere spostate nel mazzo impostato nella finestra di dialogo di importazione. Qualora le note vengano aggiornate in loco, le informazioni di pianificazione relative a tutte le loro carte vengono preservate.

Per informazioni su come vengono gestiti i duplicati nei file .apkg, consulta la sezione [Pacchetti di mazzi](../exporting.md#packaged-decks).

## Intestazione dei file

Anki 2.1.54 e versioni successive supportano alcune intestazioni che possono essere incluse nel file di testo per
rendere l'importazione più potente o conveniente. Queste intestazioni consistono in coppie `#chiave:valore`
e devono essere elencate in righe separate in cima al file, sebbene la [riga delle etichette](#aggiunta-di-etichette) possa precederle. Poiché le righe di intestazione iniziano con il carattere di commento `#`, i client Anki precedenti le ignorano.

Per poter utilizzare questa funzionalità nella versione 2.1.54, è necessario abilitare la nuova opzione di importazione nella schermata delle preferenze. Nella versione 2.1.55, il nuovo percorso di importazione è quello predefinito.

| Chiave            | Valori consentiti                                                                           | Comportamento                                                                                                   |
| ----------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| `separator`       | `Comma`, `Semicolon`, `Tab`, `Space`, `Pipe`, `Colon`, o i rispettivi caratteri letterali  | Determina il separatore di campo.                                                                               |
| `html`            | `true`, `false`                                                                            | Determina se il file è trattato come HTML.                                                                      |
| `tags`            | Elenco di etichette, separata da spazi                                                      | Identico alla [vecchia sintassi](#aggiunta-di-etichette).                                                                 |
| `columns`         | Elenco di nomi, separati dal separatore precedentemente impostato                           | Determina il numero di colonne e mostra i nomi a loro assegnati durante l'importazione.                         |
| `notetype`        | Nome o id del tipo di nota                                                                  | Preimposta il tipo di nota, se esiste.                                                                          |
| `deck`            | Nome o id del mazzo                                                                         | Preimposta il mazzo, se esiste.                                                                                 |
| `notetype column` | `1`, `2`, `3`, ...                                                                         | Determina quale colonna contiene il nome o l'id del tipo di nota di ciascuna nota, vedi [Colonna del tipo di nota](#colonna-del-tipo-di-nota).                                                                                 |
| `deck column`     | `1`, `2`, `3`, ...                                                                         | Determina quale colonna contiene il nome o l'id del mazzo di ciascuna nota, vedi [Colonna del mazzo](#colonna-del-mazzo).                                                                                                       |
| `tags column`     | `1`, `2`, `3`, ...                                                                         | Determina quale colonna contiene le etichette di ciascuna nota.                                                 |
| `guid column`     | `1`, `2`, `3`, ...                                                                         | Determina quale colonna contiene il GUID di ciascuna nota, vedi [Colonna del GUID](#colonna-del-guid).          |

**N.B.**: Ad eccezione dei valori di _tags_, _columns_, _notetype_ e _deck_, tutte le altre coppie chiave:valore devono essere in inglese.

Alcune intestazioni hanno ulteriori implicazioni.

### Colonna del tipo di nota

Solitamente, tutte le note provenienti da un file vengono mappate a un singolo tipo di nota, ed è possibile scegliere quale colonna viene mappata a un campo specifico di quel tipo di nota.

La situazione cambia se è presente una colonna con i nomi o gli id dei tipi di nota. In tal caso, è possibile importare note con tipi di nota diversi, i cui campi saranno mappati implicitamente: la prima colonna normale viene utilizzata per il primo campo di qualsiasi nota, indipendentemente dal suo tipo di nota, la seconda colonna normale per il secondo campo, e così via. Una "colonna normale" è una colonna che non contiene informazioni speciali come mazzi, etichette, tipi di nota o GUID.

### Colonna del mazzo

In genere, tutte le nuove carte create a seguito dell'importazione di un file testuale vengono inserite in un singolo mazzo a propria scelta ma, se il file contiene una colonna dedicata al mazzo, le nuove carte di una nota vengono inserite nel mazzo specificato. Se il mazzo non esiste, viene creato un nuovo mazzo con il nome specificato.

### Colonna del GUID

GUID, acronimo di _Globally Unique Identifier_ (Identificatore Univoco Globale), è un ID univoco che Anki assegna a ciascuna nota creata. Questo ID può essere utilizzato per la verifica dei duplicati. Se esporti le tue note includendo il GUID, puoi modificarle e, purché non modifichi il campo GUID, puoi reimportarle per aggiornare le note esistenti.

Sebbene Anki sia progettato per creare il GUID automaticamente, se preferisci creare ID personalizzati, come per esempio MIANOTA0001, è consigliato inserirli nel primo campo, anziché assegnarli al GUID interno. In fase di importazione, Anki può utilizzare sia il primo campo che il GUID per la verifica dei duplicati, quindi non è necessario che gli ID siano dei GUID per poter aggiornare le note. Va inoltre sottolineato che l'opzione "duplica" non funziona per le righe contenenti un GUID non vuoto. Se viene fornito un GUID e questo esiste già nella collezione, non viene creato alcun duplicato.
