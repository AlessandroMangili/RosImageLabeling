# Web tool for Labeling

Semplice web app che permette di labellare un set di immagini estratte da un file bag.

Una volta avviato il server, l'app presenta la pagina home in cui si ha la possibilità o di caricare un file bag, e quindi di estrarre il suo contenuto e creare un'instanza locale, oppure di selezionare una delle istanze locali già presenti per accedere all'area di annotazione.


![homepage](https://github.com/AlessandroMangili/WebToolLabelImage/assets/86318455/a5d12ba4-f62c-40b6-9db6-95560274947f)

Una volta selezionata l'istanza locale, si verrà ridirezionati all'interno della pagina di annotazione che si presenta con due colonne, una a sinistra e una a destra, mentre al centro si trova un riquadro contenente le immagini del topic selezionato. \
In alto possiamo trovare altre due funzionalità: una selezione per cambiare il topic, e una checkbox che servirà per mantenere i bounding box così da non dover ricrearli per ogni immagine.

![label](https://github.com/AlessandroMangili/WebToolLabelImage/assets/86318455/5434998b-f6a5-4221-affa-4dab316f9066)

Nella colonna di sinistra troviamo un pulsante che ci permette di creare una classe per i bounding box con il rispettivo colore, mentre nella colonna di destra, ci sarà una checkbox da spuntare ogni qualvolta si ha la necessità di dover creare delle sottoclassi per migliorare la granularità dell'annotazione.

Prima di poter disegnare un buonding box è necessario creare e selezionare una delle classi create, soltanto dopo tramite la combinazione di tasti `ctrl + click mouse` e trascinando il mouse sarà possibile creare i bounding box.

Sui bounding box è possibile compiere le operazioni di traslazione e ridimensionamento, inoltre è possibile rimuoverli selezionando il bounding box da rimuovere, e premendo il tasto `canc`. Per rimuovere tutti i bounding box di una classe/sottoclasse, è sufficiente fare doppio click su di essa in modo tale cancellare tutti i bounding box relativi a quella classe/sottoclasse.

Si può sempre interrompere il lavoro per poi riprendere in un secondo momento in quanto i dati delle classi, sottoclassi e bounding box disegnati sono tutti salvati nell'istanza locale di MongoDB, all'interno il database `roslog`. Per salvare è sufficiente ritornare alla homepage oppure usare la combinazione di tasti `CTRL + C` sul server nodejs.

Una volta finito di labellare l'intero set di immagini, è possibile esportare il set di immagini labellate, salvate all'interno dell'istanza locale di MongoDB.

## Dipendenze

- Ubuntu 20.04 (consigliata)
- [ROS noetic](http://wiki.ros.org/noetic/Installation/Ubuntu)
  - Installazione `ros-noetic-desktop`
  - Pacchetti aggiuntivi `ros-noetic-mongodb-store` e `ros-noetic-mongodb-log`
- [NodeJS](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04) versione consigliata `14.21.3`  
  - Prima eseguire`npm uninstall opencv4nodejs` per rimuovere tutte le dipendenze e poi `npm install opencv4nodejs`. \
    Per poter aggiungere `opencv4nodejs`, bisogna prima avere __cmake__ e __git__ installati
- Per far funzionare i pacchetti `mongodb_store` e `mongodb_log`, bisogna installare:
  - `python-is-python3`
  - `pip install pymongo==2.7`

## Consigli

Ogni volta che si riavvia il sistema, bisogna fermare il processo MongoDB con `sudo systemctl stop mongodb`.

---

## English
