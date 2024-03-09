# Librerie mancanti

Se Anki non si avvia, eseguilo dal terminale con il comando `anki`. Nel caso in cui venga segnalata la mancanza di una o più librerie, provvedi ad installarle e quindi riprova.

Se viene mostrato un messaggio di errore circa l'_assenza di piattaforme disponibili_, avvia Anki con il seguente comando, il quale dovrebbe mostrare le librerie mancanti:

```shell
QT_DEBUG_PLUGINS=1 anki
```

Dopo aver installato le librerie con apt-get o un altro gestore di pacchetti, ripeti la procedura. Potrebbe essere necessario effettuare l'operazione più volte finché tutte le librerie necessarie non saranno installate.
