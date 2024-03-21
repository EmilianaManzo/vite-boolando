# Title : Vite Boolando
________

Descrizione
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout.
Non esagerate con i componenti: less is more.
L’esercizio già lo conoscete (html-css-boolando), ma la sfida è suddividerlo in componenti e provare a sfruttare SASS per rendere il nostro stile più leggibile e flessibile (di quali variabili potreste avere bisogno?).
Bonus
Popoliamo le voci dell’header (sia le tre voci testuali che le tre icone) dinamicamente.

## Svolgimento 
1. creo una nuova cartella con powershell 
2. apro vsc, installo nel terminale
3. installo le librerie di cui ho bisogno (sass, fontsource, fontawesome ) e le importo 
<!-- fontawesome deve essere importato in main.js, è stato molto faticoso farlo funzionare-->
4. faccio partire il server
5. creo i le cartelle e i file sass ( main, variant e general)
6. creo le mie varianti e importo il file dove mi serve
7. importo main.scss in app.vue
8. creo i miei componeti vue (header, main , footer) che importo in App.vue 
9. creo all'interno di ogni componente la parte html di cui ho bisogno
8. aggiungo gli stili con il nesting


## Bonus
<!-- fatto sia per header che per footer, inserito il logo in modo dinamico con una funzione -->
1. creo degli array di oggetti 
2. faccio dei cicli v-for dove ne ho bisogno e stampo dinamicamente