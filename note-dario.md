

## DNABERT 2 Improvements

DNABERT 2 explore the BPE (BytePair Encoding) approach instead of the k-mer by demostrating as they said:

> We demonstrate that BPE not only overcomes the limitations of k-mer tokenization but also benefits from the computational efficiency of non-overlapping tokenization.

What's this issue in k-mer overlapping ?

## Improvements
Could be interesting to explore both the Promoter prediction with k-mer tokenization and BPE tokenization (DNABERT vs DNABERT 2 approach).

## DNABERT 

"-249 +50 bp around the TSS (Transcription Start Site)" means:

They take the DNA sequence starting 249 base pairs upstream of the TSS (i.e., before the TSS, in the 5' direction), which is position -249.
They continue through the TSS (position 0) and up to 50 base pairs downstream of the TSS (i.e., after the TSS, in the 3' direction), which is position +50.


```python3
cd examples

export KMER=6
export MODEL_PATH=PATH_TO_THE_PRETRAINED_MODEL
export DATA_PATH=sample_data/ft/$KMER
export OUTPUT_PATH=./ft/$KMER

python run_finetune.py \
    --model_type dna \
    --tokenizer_name=dna$KMER \
    --model_name_or_path $MODEL_PATH \
    --task_name dnaprom \
    --do_train \
    --do_eval \
    --data_dir $DATA_PATH \
    --max_seq_length 100 \
    --per_gpu_eval_batch_size=32   \
    --per_gpu_train_batch_size=32   \
    --learning_rate 2e-4 \
    --num_train_epochs 5.0 \
    --output_dir $OUTPUT_PATH \
    --evaluate_during_training \
    --logging_steps 100 \
    --save_steps 4000 \
    --warmup_percent 0.1 \
    --hidden_dropout_prob 0.1 \
    --overwrite_output \
    --weight_decay 0.01 \
    --n_process 8
```


bisogna partire dallo script originale "run_finetune.py" e pulirlo da tutte le cose non necessarie.
Dovremmo provare a fare solamente finetuning partendo da un modello preaddrestrato.


## Note installazione

Python 3.8 sembra ok, di meno non riusciamo a fare.

tokenizers da problemi durante l'instllazione (tokenizers viene installato quando si fa il setup.py `python3 -m pip install --editable .`) e quindi è necessario installare il Rust perchè funzioni...

Invece per installare i requirements.txt in examples è necessario prima installare sentencepiece manualmente (e installerà la 0.2.0 per ora) e commentare la linea nel file requirements.txt riguardo sentencpiece, il resto dovrebbe installarsi senza problemi.
