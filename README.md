# PROGETTO_PDGT_2019_CLIENT
Lato client che sfrutta i srvizi forniti dalle api descritte nella repository PROGETTO_PDGT_2019

# Documentazione CLIENT

Il file client.php è stato sviluppato per interagire con le API, è scritto in linguaggio PHP ed è stato ottimizzato per un'esecuzione da CLI. <br />
Una volta aperto da riga di comando, il programma stampa a video un breve messaggio di introduzione (info programmatore e info del client) seguito da un menù di selezione riguardante le varie funzioni messe a disposizione dal client, ognuna delle quali selezionabile inserendo il numero che la precede e identifica, seguito dal tasto 'invio'. <br />
Selezionando l'opzione '1' viene stampata a schermo la lista completa dei campionamenti del numero di veicoli contenuti nel database ,le informazioni vengono prelevate tramite richiesta HTTP all' API 'stampa_db_num_veicoli.php'.<br />
Selezionando l'opzione '2',viene richiesto di inserire la provincia con la quale filtrare il database, le informazioni vengono prelevate mediante richiesta HTTP all' API 'stampa_dati_sel_num_veicoli.php'.<br />
Selezionando l'opzione '3',viene richiesto di inserire il comune con la quale filtrare il database, le informazioni vengono prelevate mediante richiesta HTTP all' API 'stampa_dati_sel_num_veicoli.php'.<br />
Selezionando l'opzione '4',viene richiesto di inserire l'anno con la quale filtrare il database, le informazioni vengono prelevate mediante richiesta HTTP all' API 'stampa_dati_sel_num_veicoli.php'.<br />
Selezionando l'opzione '5',viene richiesto di inserire il comune e successivamente l'anno con i quali filtrare il database, le informazioni vengono prelevate mediante richiesta HTTP all' API 'stampa_sel_doppia_num_veicoli.php'.<br />
Selezionando l'opzione '6',viene richiesto di inserire i seguenti dati ognuno seguito da invio: username, password, provincia, comune, anno, numero di veicoli da inserire, le informazioni vengono inviate al database mediante richiesta HTTP all' API 'inserire_dati_nel_database.php'.<br />
Selezionando l'opzione '7',viene richiesto di inserire i seguenti dati ognuno seguito da invio: username, password, provincia, comune, anno, numero di veicoli da eliminare, le informazioni vengono inviate al database mediante richiesta HTTP all' API 'eliminare_dati_nel_database.php'.<br />
Selezionando l'opzione '8',viene terminato il client.<br />
(PHP version 7.3.12).
. <br /><br />

# Documentazione CLIENT CON INTERFACCIA HTML
I file che includono lo sviluppo del client con interfaccia grafica (html/css) e l'utilizzo delle API di google maps per l'implementazione della mappa per la visualizzazione del comune selezionato sono i seguenti:

<table>
  <tr>
    <td><b>File</b></td>
    <td><b>Tipo</b></td>
    <td><b>Descrizione</b></td>
  </tr>
  <tr>
    <td>loginaccess.php</td>
    <td>PHP/HTML</td>
    <td>Pagina iniziale di login per l'aquisizione di username (userpass) e password (testuserpass) e li invia alla pagina verifica_login.php.</td>
  </tr>
  <tr>
    <td>verifica_login.php</td>
    <td>PHP/HTML</td>
    <td>Riceve i dati di login dalla pagina di loginaccess.php e li invia tramite richiesta POST alla pagina login_.php.</td>
  </tr>
  <tr>
    <td>login_.php</td>
    <td>PHP/HTML</td>
    <td>Si trova sul server di altervista e si occupa di verificare se i dati di login ricevuti tramite metodo POST sono presenti sulla tabella del database relativa al login restituendo una risposta di avvenuto login o meno.
    </td>
  </tr>
  <tr>
    <td>Ricerca_numveicoli.php</td>
    <td>PHP/HTML/JAVASCRIPT</td>
    <td>Pagina principale che mostra i comuni e gli anni presenti nel database ed implementa la mappa in cui viene indicato il comune selzionato al momento della ricerca, si connette con le pagine style.css(Grafica HTML), campi_selezione.php, select_comune.php, campi_anno.php, select_anno.php, richiesta_database.php, inserimento_rimozione_dati.php (mediante collegamento ipertestuale).</td>
  </tr>
   <tr>
    <td>campi_selezione.php</td>
    <td>PHP/HTML</td>
    <td>Pagina che utilizza la API stampa_db_num_veicoli.php per aggiornare i campi di selezione dei comuni.
    </td>
  </tr>
  <tr>
    <td>campi_anno.php</td>
    <td>PHP/HTML</td>
    <td>Pagina che utilizza la API stampa_db_num_veicoli.php per aggiornare i campi di selezione degli anni.
    </td>
  </tr>
   <tr>
    <td>select_comune.php</td>
    <td>PHP/HTML/JAVASCRIPT</td>
    <td>Pagina che effettua la richiesta di geocoding del comune selezionato mediante il metodo google.maps.Geocoder() messo a disposizione dalle api di google.maps per poter ricavare le coordinate geografiche del comune e rapparesentare il marker sulla mappa.
    </td>
  </tr>
   <tr>
    <td>richiesta_database.php</td>
    <td>PHP/HTML</td>
    <td>Pagina che utilizza la API stampa_sel_doppia_num_veicoli.php alla quale vengono inviati dati selezionati (comune e anno) e viene ricevuto in risposta il numero di veicoli presenti.
    </td>
  </tr>
   <tr>
    <td>inserimento_rimozione_dati.php</td>
    <td>PHP/HTML</td>
    <td>L'accesso a questa pagina viene effettuato mediante collegamento ipertestuale dalla pagina Ricerca_numveicoli.php. Questa pagina si occupa dell'acquisizione dati da inserire o da rimuovere dal database i dati aqcuisiti vengono inviati tramite metodo post alla pagina gestione_ins_rim.php .
    </td>
  </tr>
  <tr>
    <td>gestione_ins_rim.php</td>
    <td>PHP/HTML</td>
    <td>Pagina per la getione delle richieste di inserimento ed eliminazione dei dati mediante l'utilizzo delle API inserire_dati_nel_database.php, eliminare_dati_nel_database.php .
    </td>
  </tr>
</table>
Questo tipo di Client è stato realizzato con Brackets e viene visualizzato nel broswer mediante il server Localhost WampServer (version 3.2.0).


