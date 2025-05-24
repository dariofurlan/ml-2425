1. Introduzione
	•	Motivazione dello studio del DNA con tecniche di NLP
	•	Limiti dei metodi precedenti (CNN, RNN)
	•	Obiettivi del nostro progetto: analisi di DNABERT, confronto con DNABERT-2, esperimento sul task di promoter prediction

⸻

2. Il modello DNABERT
	•	Cos’è DNABERT
	•	Architettura: Transformer, k-mer come token, addestramento su genoma umano
	•	Pretraining: masking su span di k-mer, obiettivo di tipo “masked language modeling”
	•	Fine-tuning: adattamento a task specifici (es. promoter, splice site, TFBS)

⸻

3. DNABERT-2: miglioramenti e differenze
	•	Limiti di DNABERT: input corto, efficienza bassa, solo genoma umano
	•	Novità introdotte:
	•	Tokenizzazione con BPE (più compatta, senza overlapping)
	•	Supporto multi-specie
	•	Uso di ALiBi per gestire sequenze lunghe
	•	Miglioramento efficienza con FlashAttention
	•	Vantaggi misurati: meno parametri, meno tempo di addestramento, performance migliori in GUE benchmark

⸻

4. Il task di promoter prediction
	•	Definizione di promotore e importanza biologica
	•	Dataset usato (EPDnew): promotori TATA e non-TATA
	•	Modalità di valutazione (DNABERT-Prom-300 e DNABERT-Prom-scan)
	•	Risultati ottenuti nel paper originale: F1-score, MCC, confronto con altri modelli

⸻

5. Ricreazione del task in Python
	•	Scopo del notebook: replicare il fine-tuning di DNABERT sul promoter prediction
	•	Scelte fatte: modello DNABERT-6, uso di huggingface o repo ufficiale
	•	Risultati preliminari ottenuti (se già disponibili)
	•	Difficoltà incontrate o considerazioni (es. tempi, GPU, preprocessing)

⸻

6. Conclusioni
	•	Riflessione su quanto DNABERT sia un buon punto di partenza per modellare il DNA
	•	DNABERT-2 migliora l’efficienza, ma introduce più complessità
	•	Possibili sviluppi futuri: applicazioni a nuovi task, fine-tuning su altri organismi

⸻

Appendice (se serve)
	•	Codice Python (link o estratto)
	•	Parametri di training usati
	•	Screenshot dei risultati ottenuti
