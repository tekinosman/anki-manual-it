# Installazione e aggiornamento di Anki su Windows

<!-- toc -->

## Requisiti

Le versioni recenti di Anki richiedono un computer con Windows 10 o 11 a 64 bit.

- L'ultima versione di Anki che supporta Windows 7 e 8.1 è la 2.1.49.
- L'ultima versione di Anki che supporta Windows a 32 bit è la [2.1.35-alternate](https://github.com/ankitects/anki/releases/tag/2.1.35).

Se possiedi un vecchio computer, puoi scaricare le versioni precedenti dalla [pagina delle release](https://github.com/ankitects/anki/releases).

## Installazione

Per installare Anki:

1. Scarica Anki da <https://apps.ankiweb.net>. La sezione successiva spiega come scegliere
   tra la versione -qt5 e -qt6.
2. Salva l'installer sul desktop o nella cartella di download.
3. Fai doppio clic sull'installer per eseguirlo. Se viene mostrato un messaggio di errore,
   consulta la [pagina dei problemi di installazione](installation-issues.md).
4. Una volta installato Anki, fai doppio clic sulla nuova icona a forma di stella sul desktop
   per avviare il programma.

## Qt5 vs. Qt6

Le versioni recenti di Anki sono disponibili in due varianti separate: Qt5 e Qt6.
La versione Qt6 è quella consigliata per la maggior parte degli utenti.

Vantaggi della versione Qt6:

- Correzione di diversi bug, incluso un miglior supporto per le lingue meno diffuse.
- Caricamento più veloce delle immagini di grandi dimensioni rispetto alla versione Qt5.
- Aggiornamenti di sicurezza. Il supporto per la libreria Qt5 è stato interrotto a novembre del 2020, il che significa che eventuali falle di sicurezza scoperte da allora non saranno risolte.
- Alcuni utenti riscontrano dei blocchi quando utilizzano [un tasto di scorciatoia personalizzato per cambiare la lingua di input](https://github.com/ankitects/anki/issues/1105) (inglese)
  in Qt5.

Svantaggi della versione Qt6:

- Alcuni add-on al momento funzionano solo con la versione Qt5.

## Aggiornamento

Se stai effettuando l'aggiornamento da Anki 2.1.6 o versioni successive, non è necessario disinstallare la versione precedente, ma è sufficiente chiudere Anki qualora sia aperto e quindi seguire le istruzioni di installazione descritte in precedenza. Le tue carte verranno preservate durante l'aggiornamento.

Se invece stai effettuando l'aggiornamento da una versione di Anki precedente alla 2.1.6, oppure passi dalla versione standard a quella alternativa o viceversa, è consigliato disinstallare prima la vecchia versione. Tale operazione rimuoverà i dati di programma di Anki, ma non eliminerà i dati delle tue carte.

Se desideri effettuare il downgrade a una versione precedente, assicurati prima di [effettuare il downgrade](http://changes.ankiweb.net)

## Compatibilità degli add-on

Alcuni add-on potrebbero non funzionare con la versione più recente di Anki. Se hai effettuato l'aggiornamento all'ultima versione di Anki e scopri che un componente aggiuntivo indispensabile non funziona più, puoi scaricare una delle versioni precedenti di Anki dalla [pagina delle release](https://github.com/ankitects/anki/releases).

## Problemi

Se riscontri problemi durante l'installazione o l'avvio di Anki consulta le seguenti pagine:

- [Problemi di installazione](installation-issues.html)
- [Problemi di avvio](startup-issues.html)
- [Problemi grafici](display-issues.html)
- [Problemi con i permessi](permission-problems.html)

Se riscontri problemi con l'interfaccia consulta le seguenti pagine:
- [Problemi con il copia-incolla](copy-and-paste.md)
- [Problemi con la dimensione del testo](text-size.md)
