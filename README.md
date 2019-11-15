# The BigBank Project

▪ Sviluppato in Java, usando Spring Boot framework. ▪ Maven (Project management tool)

## Configurazione

Dopo aver scaricato questo progetto, bisogna configurare il database nel file application.properties In particolare le prossime righe per potere creare il database locale con MySQL:

spring.datasource.url=jdbc:mysql://localhost:3306/bigbank?autoReconnect=true&useSSL=false spring.datasource.username = springuser <------ dipende dalle impostazioni spring.datasource.password = springpassword <------ idem spring.jpa.hibernate.ddl-auto=create <------ questa riga si cambia da create a update dopo il primo giro del programma

Il codice in questo file sopra è commentato per facilitare le modifiche delle impostazioni.

## REST APIs:

Durante lo svilupo ho usato Postman per mandare le richieste e ottenere le risposte.

Il punto d’accesso: http://localhost:5000/bigbank/.
Per rispondere alle esigenze: si collega all’’url in alto, poi si passano i parametri come nei casi seguenti:

Con: 

- Metodo POST: “…/uploadfile “ => concede il caricamento solo dei tre tipi di files, che risulta all scrittura nel database dopo l’analizzi (parsing) dei dati.

GET: “…/account/movements”: per visionale i movimenti sul conte e i lori totali. Qui servono i parametri per variare le richieste. I parametri sono: "account", "month", "year" (conto numero, mese e anno)

GET: “…/card/movements”: per i movimenti solo allaga alle carte di credito e i lolo totali.

Per vedere tutte gli accessi messi a disposizione, aprire il file RestApi.java nel programma. Path: ...\bbproject\src\main\java\com\bigbankpro\controller\RestApis.java

### I test unitari 
purtroppo, non son stati inclusi nel codice a causa del tempo stretto. Ma i testi sono stati effettuati mano a mano che ogni unità era pronto, per assicurami del suo corretto funzionamento.
