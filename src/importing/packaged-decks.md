# Mazzi impacchettati

<!-- toc -->

I pacchetti Anki (file .apkg) permettono di importare mazzi, note, tipi di note e carte da altri utenti. Sono comunemente condivisi su [AnkiWeb](https://ankiweb.net/shared/decks).

## Pianificazione

I pacchetti Anki possono contenere anche informazioni sulla pianificazione, utili se desideri trasferire mazzi tra dispositivi o profili. Tuttavia, quando importi un mazzo condiviso da qualcun altro, non è generalmente desiderabile utilizzare i loro intervalli di ripasso o la cronologia delle ripetizioni.

Se le carte importate hanno intervalli inaspettatamente grandi, l'autore del mazzo potrebbe aver accidentalmente incluso le sue informazioni di pianificazione. È possibile utilizzare la funzione [Imposta Data di Scadenza](../browsing.md#cards) per reimpostare le carte importate. A partire da Anki 23.10, è possibile rimuovere le informazioni di pianificazione durante il processo di importazione, lasciando deselezionata l'opzione "Importa anche eventuali progressi di apprendimento". In questo modo verranno anche rimosse eventuali etichette sanguisuga (leech) o contrassegnate (marked) dalle carte importate.

## Aggiornamento

Quando importi un file .apkg, Anki identifica tutte le note in esso presenti che sono già presenti nella tua collezione per via di un'importazione precedente. Se le note nel file sono più recenti della tua copia locale, verrano aggiornate con il contenuto del file per impostazione predefinita.

Questo processo di aggiornamento non è generalmente possibile se il tipo di nota viene modificato (ad esempio, se tu o l'autore del mazzo avete aggiunto un campo extra al tipo di nota). Tuttavia, puoi comunque importare tutte le note mancanti dal file, ma le note che hai importato in precedenza non verranno aggiornate se l'autore del mazzo ha apportato delle modifiche.

### Anki 23.10 e versioni successive

La versione 23.10 di Anki ha introdotto una maggiore flessibilità: è ora possibile scegliere di aggiornare incondizionatamente le note e i tipi di nota, sovrascrivendo sempre le modifiche apportate, oppure, al contrario, di non aggiornare mai gli oggetti esistenti.

Inoltre, se sia tu che l'autore del mazzo avete modificato lo stesso tipo di nota, ora puoi decidere di _unire_ le due versioni. In questo modo si preservano tutti i modelli e i campi contenuti nell'uno o nell'altro, richiedendo però una sincronizzazione completa e potrebbe contrassegnare altre note esistenti come modificate.

#### Nota agli autori dei mazzi

L'unione si basa sugli id dei modelli e dei campi, che sono stati introdotti nella versione 2.1.67 di Anki. Se un modello o un campo non ha un id, perché creato con una versione precedente, Anki cerca di trovare un equivalente mediante il confronto dei nomi.

Consulta [questo add-on](https://ankiweb.net/shared/info/2063785767) per capire perché è vantaggioso condividere i tipi di nota con id di campo e modello, e come aggiungerli a quelli esistenti.

### Soluzione per Anki 2.1.66 e versioni precedenti

Se sai che l'autore del mazzo ha apportato delle modifiche e desideri accedervi, ripristinare il tipo di nota è possibile, ma la procedura è piuttosto complessa. Ecco i passaggi da seguire:

- Crea un nuovo profilo e importa il file .apkg.
- Nella schermata Sfoglia, individua una delle note che non si è aggiornata e selezionala.
- Usa i tasti Campi e Carte per controllare i nomi dei campi e del modello e annotali.
- Usa la [console di debug](https://docs.ankiweb.net/misc.html#debug-console) per determinare l'id del tipo di nota. L'id è il numero che compare alla fine della riga.

```
nt = bcard().note().note_type()
print("L'id del tipo di nota", nt["name"], "è", nt["id"])
```

- Torna al profilo normale, individua la stessa carta e selezionala. Quindi esegui quanto segue:

```
nt = bcard().note().note_type()
print("attuale: l'id di", nt["name"], "è", nt["id"])
nt = mw.col.models.get(xxx)
print("desiderato: l'id di", nt["name"], "è", nt["id"])
```

- Se i nomi dei due tipi di nota sono diversi, utilizza l'azione Modifica Tipo di Nota per cambiare il tipo di nota delle note esistenti con quello desiderato.

- Usa i tasti Campi e Carte per verificare che i nomi dei campi e del modello corrispondano _esattamente_ a quello del profilo di test. Non devono esserci campi in meno o in più, e devono essere scritti alla stessa identica maniera.
