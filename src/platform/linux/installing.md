# Installazione e aggiornamento di Anki su Linux

<!-- toc -->

## Requisiti

Il pacchetto di Anki richiede un sistema Linux a 64 bit recente con processore Intel/AMD, glibc e librerie comuni come libwayland-client e systemd. Se utilizzi un'architettura diversa (ad esempio ARM/AArch64) o una distribuzione Linux minimale, non potrai utilizzare il pacchetto, ma potresti provare con i [wheel di Python](https://betas.ankiweb.net/#via-pypipip).

Se utilizzi Debian o una distribuzione derivata, come Ubuntu e [Chromebook con Linux abilitato](https://support.google.com/chromebook/answer/9145439?hl=it), esegui il seguente comando prima dell'installazione:

```shell
sudo apt install libxcb-xinerama0 libxcb-cursor0 libnss3
```

Nel caso in cui Anki non si avvii dopo l'installazione, potrebbero esserci delle [librerie mancanti](./missing-libraries.md).

Se utilizzi la versione 24.04 di Ubuntu, vedi [questa discussione](https://forums.ankiweb.net/t/issues-running-on-ubuntu-24-04/40974) (inglese).

Il sistema di build di Anki supporta solo glibc, pertanto le distribuzioni basate su musl non sono attualmente supportate.

## Installazione

Per installare Anki:

1. Scarica il file di installazione da <https://apps.ankiweb.net> e salvalo nella cartella Download. La sezione successiva spiega come scegliere tra le versioni -qt5 e -qt6.
2. Verifica se zstd è installato sul tuo sistema, altrimenti provvedi alla sua installazione (ad esempio con `sudo apt install zstd`).
3. Apri il terminale ed esegui i seguenti comandi, sostituendo il nome del file con quello della versione scaricata.

```shell
tar xaf Downloads/anki-2XXX-linux-qt6.tar.zst
cd anki-2XXX-linux-qt6
sudo ./install.sh
```

Su alcuni sistemi Linux potrebbe essere necessario utilizzare il comando `tar xaf --use-compress-program=unzstd`.

4. Al termine dell'installazione, avvia Anki digitando "anki" a premendo invio. Se dovessi riscontrare problemi, consulta i link a sinistra.

## Qt5 vs. Qt6

Le versioni recenti di Anki sono disponibili in due varianti separate: Qt5 e Qt6.
La versione Qt6 è quella consigliata per la maggior parte degli utenti.

Vantaggi della versione Qt6:

- Correzione di diversi bug, incluso un miglior supporto per le lingue meno diffuse.
- Compatibilità con le versioni recenti di glibc (risolve il [problema della schermata bianca sulle distribuzioni più recenti](./blank-window.md)).
- Miglior supporto per l'HiDPI.
- Aggiornamenti di sicurezza. Il supporto per la libreria Qt5 è stato interrotto a novembre del 2020, il che significa che eventuali falle di sicurezza scoperte da allora non saranno risolte.
- Miglior supporto per Wayland.

Svantaggi della versione Qt6:

- Alcuni add-on al momento funzionano solo con la versione Qt5.

## Aggiornamento

Se in precedenza utilizzavi una versione di Anki installata tramite un pacchetto .deb/.rpm/ecc., assicurati di rimuovere la versione di sistema prima di procedere con l'installazione del pacchetto fornito qui.

Se invece stai effettuando l'aggiornamento da un pacchetto installato in precedenza, ripeti semplicemente i passaggi di installazione per ottenere la versione più recente. I tuoi dati utente verranno preservati.

Qualora tu desideri effettuare il downgrade ad una versione precedente, assicurati prima di [effettuare il downgrade](http://changes.ankiweb.net)

## Compatibilità degli add-on

Alcuni add-on potrebbero non funzionare con la versione più recente di Anki. Se hai effettuato l'aggiornamento all'ultima versione di Anki e scopri che un componente aggiuntivo indispensabile non funziona più, puoi scaricare una delle versioni precedenti di Anki dalla [pagina delle release](https://github.com/ankitects/anki/releases).

## Problemi

Se riscontri problemi durante l'installazione o l'avvio di Anki, consulta le seguenti pagine:
- [Librerie mancanti](missing-libraries.md)
- [Problemi grafici](display-issues.md)
- [Finestra principale bianca](blank-window.md)
- [Pacchetti per distribuzioni Linux](distro-packages.md)
- [Tema GTK errato](gtk-theme.md)
- [Wayland](wayland.md)
- [Metodi di input](input-methods.md)

