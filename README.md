# AILabProj-NBA Scheme Classification
Repository of the NBA Classification of Scheme created for the Sapienza IA Lab a.a 2021/22 made by Michele Simeone. 

Il problema iniziale consisteva nel ricavare da dei file Json contenenti le coordinante registrate in ogni momento della partita delle immagini sulle quali lavorare per la classificazione di azioni durante il corso di una partita (Schemi), questa parte di codice è ricoperta dal Colab: Image Generation. E' stato necessario inoltre integrare i dati con quelli riportanti i ruoli dei giocatori per poter selezionare a seconda del quintetto in campo le posizioni temporanee dei giocatori.

Una volta ottenute le immagini c'è stato bisogno di un attento lavoro manuale di analisi per scegliere tra tutte le azioni di una partita quelle che potevano rientrare nelle classi prese in analisi. Queste sono servite per la creazione di un dataset nel quale, tramite un algoritmo, è stato creato del data augmentation per specchiare ogni azione in tutti e 4 i quadranti del campo da basket.

Finita la fase di creazione del dataset si è passati a quella di creazione della rete. Per valutare il problema sono state prese in esame 4 tipi di reti: 2 preallenate e 2 create da 0.
Le reti preallenate sono una Resnet50V2 e una ConvNextTiny considerate il vecchio e il nuovo standard per le CNN. Le reti costruite sono una CNN classica a 4 layer e una SVM utilizzata per l'image classification. Tutte e 4 le reti sono state testate prima su un problema di classificazione binaria e poi multiclasse.




Link Cartella Drive: https://drive.google.com/drive/folders/1Xm8pCSpW4N-RX-1HAF_WC68AHraU2rfc?usp=sharing

La cartella Drive è divisa in varie sottocartelle:

-Data: contiene i file Json delle due squadre prese in esame che sono stati forniti da SportsVU azienda che nel 2015-16 (stagione analizzata) si occupava di tracciare questi dati per l'NBA e i file CSV che servono per l'integrazione dei ruoli; questi file sono stati ottenuti da Basketball Reference e successivamente elaborati tramite delle query in Microsoft Access.

-Dataset: contiene i dataset sia per la classificazione binaria che in quella multipla; entrambi i dataset sono divisi in Train e in Test.

-Example: alcuni esempi di immagine; ci sono varie traiettorie, i markers valutati prima di decidere quello finale, il modello del campo e i file json originali.

-Model: contiene il modello CNN salvato sia per la classificazione binaria sia per la classificazione multipla.

-Result: cartella con alcuni risultati iniziali dei primi training e un file excel contenente il riassunto di training con vari iperparametri.

-Weights: pesi ottimali salvati con il checkpoint callback per ogni rete provata per questo progetto.
