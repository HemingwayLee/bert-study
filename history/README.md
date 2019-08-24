# History

## Idea
* Context-specific word representation is the hidden layer of LSTM, we can take it and use it in other applications
* The more data we used in pre-trained stage, less data we need in our real tasks
* Similar ideas, just scaling thing: ELMO, ULMfit -> OpenAI `GTP` -> `BERT` -> OpenAI `GTP-2`

## TagLM (Pre-ELMO)
* `BiLSTM`, `char CNN`, `CRF layer`, it contains contextual information
* Architecture  
![taglm](https://user-images.githubusercontent.com/8428372/61204143-6e716880-a727-11e9-979a-eb550e6aed93.png)

![taglm2](https://user-images.githubusercontent.com/8428372/61204145-6f09ff00-a727-11e9-9922-2f7c046ececb.png)

* Ref  
https://arxiv.org/pdf/1705.00108.pdf  

## ELMO (Best Paper Award in 2018)
* Breakout version of word token vectors or contextual word vectors
* Make it easy to reuse the pretrained layers for other tasks
* TagLM uses top layer of LSTM, but ELMO uses all layers of LSTM
* Weight for each layer of LSTM is learned, and weighted layers are used in ELMO
  * We can concatenate freezed representation (learned from ELMO) into hidden layers
  * We can also use it in other way
  * Lower layer (more syntax): NER, POS tag, ...
  * Higher layer (semantics): Sentiment, QA, ...

* Ref  
https://arxiv.org/pdf/1802.05365.pdf

## ULMfit
* Similar idea to ELMO

## Transformer
* `GTP`, `BERT`, and `GTP-2` all use Transformer
* We want things to go faster so we can build a bigger model
