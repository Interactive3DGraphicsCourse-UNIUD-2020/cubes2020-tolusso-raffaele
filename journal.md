# progetto Tolusso Raffaele 

l'idea è quella di una scena al cui interno si muove un treno a vapore fatto con i cubettis
il treno percorrà un circuito e una volta inserita l'heightmap cercherò di adattare i movimenti del treno a quest'ultima

## costruzione treno 

Mi sono dedicato alla costruzione del treno e delle sue parti ho preso la decisione di avere un oggetto3d (Treno per l'appunto) in cui ho inserito le sue parti per la precisione 3 vagoni e una locomotiva.

- Ogni vagone è composto da un carico e dalle sue ruote che si muoveranno a coppia di due.
- La locomotiva è composta dalla cabina, dalla motrice e dal camino (anch'esso suddiviso in due parti).
## problematiche di animazione del treno

Ho iniziato l'animazione del treno:

- ho costruito la semplice animazione delle ruote facendo ruotare l'oggetto 'setDiRuote" attorno al suo asse z senza riscontrare alcun problema.
- ho costruito la translazione del treno senza riscontrare alcun problema
- ho costruito una rotazione del treno rispetto a un pivot (altrimenti il treno avrebbe ovviamente ruotato su se stesso senza alcun senso), mi sono accorto che l' animazione di questo tipo non era una buona animazione perchè il treno era troppo lungo e ruotando aveva un effetto strano nei punti lontani dal baricentro.
Ho ripensato all'animazione e deciso di suddividere le varie parti del treno attribuendo ad ognuna di esse un un pivot in modo da farle ruotare in tempi diversi (prima la parte del treno più in avanti e poi le successiva mano a mano). A questo punto anche la translazione doveva essere ricostruita e attribuita ad ognuno dei pivot ( in modo che raggiungano tutti uno stesso punto attorno al quali copiere una rotazione). 

Sto lavorando su come basare il quando finire la translazione e far iniziare la rotazione e su come basare i parametri che le gestiscono.

Ho aggiunto una piccola rotazione ad ogni parte del treno nelle fasi di rotazione e scelto la maniera in cui il treno dovrà ruotare. A seconda della parte del percorso che deve essere percorsa basta dividere i valori ottenuti dal clock e usare il resto della divisione per rappresentare una parte del percorso. Il circuito di base è una traslazione seguita da una rotazione di 180° attorno a un centro seguita da un' altra traslazione nel verso inverso seguita ancora una volta da una rotazione di 180° che completi i 360° e riporti il treno al punto di partenza. Una volta costruito il plane seguendo l'heightmap cercherò di modificarlo ulteriormente in modo che segua la posizione dei cubi inseriti attraverso heightmap.