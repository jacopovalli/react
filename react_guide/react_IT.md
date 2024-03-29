#React

[https://react.dev/learn/react-developer-tools]
_______________________________________________________________


1. Creare cartella

2. Accedere ad essa

3. Aprire Editor (VSC, nel mio caso)

4. Aprire un terminale, che andrà lasciato aperto, e dare il comando **npx create-react-app nome_progetto_react** e seguire le istruzioni

5. **Accedere da terminale alla cartella del progetto** inclusa nella cartella creata precedentemente

6. **npm i**

7. Aprire un temrinale, che lasceremo aperto, e accertarsi di essere nella cartella del progetto React al quale stiamo lavorando e lanciare il comando:

 **npm run start**

8. Andare in src e aprire il file **App.js** ed effettuare una modifica, che si vedrà nel browser alla finestra aperta precedentemente lanciando il comando al punto 5.

9. Lavoreremo sempre attraverso la cartella **src** ed i files contenuti in essa.
Possiamo andare a modificare anche il file **index.html** presente in **public**, ***ma è attraverso il file con lo stesso nome – index.html – presente in src, che andiamo ad agire direttamente su ciò che poi vediamo nel browser attraverso il file presente in public*** (public è relativa a ciò che vediamo lato client, come in Laravel)

10. Installare l'estensione VSC chiamata ES7+ React/Redux/React-Native snippets, di dsznajder per avere le shortcuts di React

11. creare cartella **components** in src

12. nella nuova cartella components, **creare file js** componente (per esempio, component_1.js) – **il nome dei componenti, in React, deve sempre iniziare con una lettera maiuscola!**

***Consideriamo che anche quando all'inizion abbiamo lanciato il comando npx create-react-app nome_progetto_react, abbiamo tecnicamente creato un componente, che, in quel caso, è il file App.js che troviamo in src***


13. **Apriamo** il componente appena creato, il file **Component_1.js**, e, utilizzando una dele shortcuts permesse dall'estensione scaricata prima, scriviamo:

**rafce**

***rafce (React Arrow Function Component Export) è una shortcuts che creerà un metodo arrow function***

oppure, scriviamo:

**rfce**

***rfce (React Function Component Export) creerà un metodo non con sinstassi arrow function***


14. in **App.js**, importare, con sintassi ES6, il componente creato sopra:

**import component_1 from './components/Component_1';**


15. **Ogni componente deve sempre ritornare qualcosa, e non può ritornare più di un elemento HTML dinamicamente creato alla volta. Quindi, se per esempio vogliamo ritornare un <h1> ed un <h2>, o li chiudiamo in un <div>, che verrà identificato come unico elemento; oppure, abbiamo due modalità:**

**a) <> contenuto elemento </>**

**b) <React.Fragment>contenuto elemento</React.Fragment>**


 **il return deve essere sempre seguito dalle parentesi tonde, che conterranno l'elemento ritornato. Se non presenti tali parentesi, il tag HTML di apertura dovrà necessariamente essere sulla stessa linea del comando return.**

 ***Questi tag HTML sono in realtà tag di tipo JSX, ovvero, JavaScript per React, e, a differenza dei tag HTML "puri" devono sempre (!) essere chiusi.***


 16. **Per annidare più subcomponents all'interno din un component primario: dichiariamo diversi subcomponenti (funzioni che ritornano subelementi) e poi, nel return del componente primario, li richiamiamo sottoforma di tag JSX**


17. Il file **index.css** che troviamo in **src** è anch'esso collegato al file **index.html** che troviamo in **public**: quindi, agiremo su quel CSS per le modifiche di stile.
_______________________________________________________________

**Creazione component Card**:


18. Creare Component per la card (nel nostro caso, **Products.js**)

19. [non necessario, ma necessario se vogliamo usare la sintassi <React.Fragment></React.Fragment>]* **importare react in App.js con import React from 'react';**

20. **Inseriamo le CDN di Bootsrap per JavaScript e CSS rispettivamente nel Body e nella Head del file index.html che si trova nella cartella public**

21. Nel nostro component, alla funzione Products, ritorniamo la card di Bootstrap

***Ricordiamo che, lavorando in JSX, dobbiamo controllare che ogni tag sia chiuso, e, per quel che riguarda le classi, come in JavaScript, non dobiamo usare class ma dobbiamo usare className***

22. in App.js, importiamo il nostro component

23. **nel return della funzione di App.js, embeddiamo il nostro component importato:**

***a questo punto, avendo più di un component embeddato nel return della funzione, dobbiamo racchiudere il tutto in un fragment, usando una delle seguenti sintassi JSX: <></> oppure <div></div> oppure <React.Fragment></React.Fragment>***

24. A questo punto, possiamo lavorare alla card nel component:

**dichiariamo una costante alla quale diamo come valore il percorso dell'immagine che vogliamo usare per la card**

**dichiariamo anche una costante per il titolo, una per il body, e, se presente, una per il testo del button**


25. **in React, quando dobbiamo richiamare il valore di una costante o variabile inun elemento, dobbiamo istruire il programma ad integrare codice propriamente JavaScript: per fare ciò, inseriamo due graffe { codice Javascript } (!):**

***il risultato, per esempio, è questo [le coppie di graffe implicate sono due]:***

***{ `${valore_costante_o_variabile}``}***
_______________________________________________________________


**props**


26. **Le props sono i parametri formali delle funzioni che ritornano gli elementi di un componente**

***props è una dicitura standard convenzionale: è bene usarla, per ragioni di intelligibilità del codice***


27. Nel componente [per l'occasione, è stato creato un terzo componente chiamato **Component_props.js**], abbiamo passo il parametro formale **props**

28. facendo un console.log di props, vediamo che essa è un oggetto.

29. In **App.js**, al componente embeddato, abbiamo aggiunto una proprietà (name, con valore 'John'), attraverso questa sintassi:

**chiave={valore}**

30. Ora, al console.log(props); , vediamo che l'oggetto ha una proprietà: nel nostro caso, la proprietà name con valore 'John'.

31. **In App.js, instanziamo 3 oggetti [nel nostro caso: hello_1, hello_2, hello_3].**

32. **Modificando le proprietà dei componenti embeddati, possiamo vederle in console. La modifica avviene secondo la seguente sintassi:**

***<componente chiave={nomeoggetto.proprietà_oggetto}></componente>***

32. **Nel file del componente [Component_props.js], abbiamo passato i parametri reali, derivanti dagli oggetti instanziati in App.js e da lì passati come attributi dell'oggetto componente embeddato, all'elemento da renderizzare ritornato dalla funzione del componente stesso.**

_______________________________________________________________
_______________________________________________________________
***Ogni Component è un oggetto il cui valore è l'elemento da renderizzare ritornato dalla funzione. ***
***La props è il Component stesso.***
***Alla Props, ovvero all'oggetto Component, possono essere attribuite delle proprietà (chiave : valore), che possiamo dare attraverso la sintassi discussa sopra, eventualmente andandole a prendere da oggetti appositamente instanziati.***
_______________________________________________________________
_______________________________________________________________


33. **Un altro modo, più comodo e sintetico, per passare proprietà ai componenti embeddati a partire da oggetti instanziati, è attraverso lo spread operator introdotto dalle graffe relative alla JSX Syntax:**

***<componente {...nome_oggetto}></componente>***


34. Successivamente, nel file relativo al component, possiamo effettuare **Destrutturazione dell'Oggetto:**

***const {chiave, chiave} = props;***


35. **Ora, possiamo modificare la sintassi anche all'interno della funzione che ritorna gli elementi da renderizzare, passando non più {props.chiave},ma direttamente ***{chiave}***. Per esempio:

***<h2>{chiave}</h2>***
_______________________________________________________________


**props children**


36. I **props children** sono proprietà assegnabili a determinati Component.

**children** è una **parola riservata**.

**Possiamo implementare un props child all'interno del tag JSX relativo al componente embeddato nel "file di gestione" JavaScript (ad esempio, nel nostro caso, App.js).**

**Implementandolo come ***react fragment***, possiamo passarlo al Component, e, se taleComponent è embeddato più volte, possiamo passarlo anche solo una volta, se così vogliamo, inserendolo solo all'interno del tag che desideriamo.**

**Nel file relativo al Component, passiamo ***children*** nella Deconstruct dell'oggetto props, e anche all'nterno del fragment nel punto in cui vogliamo renderizzarlo, attraverso la sintassi JSX ***{children}***.
_______________________________________________________________
