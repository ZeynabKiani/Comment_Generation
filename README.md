# Comment_Generation 
Generate text based on entities extracted by "ner-english-ontonotes-large" model from input text
The recognized entity are below

              | entity      | meaning              |
              |-------------+----------------------|
              | CARDINAL    | cardinal value       |
              | DATE        | date value           |
              | EVENT       | event name           |
              | FAC         | building name        |
              | GPE         | geo-political entity |
              | LANGUAGE    | language name        |
              | LAW         | law name             |
              | LOC         | location name        |
              | MONEY       | money name           |
              | NORP        | affiliation          |
              | ORDINAL     | ordinal value        |
              | ORG         | organization name    |
              | PERCENT     | percent value        |
              | PERSON      | person name          |
              | PRODUCT     | product name         |
              | QUANTITY    | quantity value       |
              | TIME        | time value           |
              | WORK_OF_ART | name of work of art  |
              
Extract Topic of input text by facebook/bart-large-mnli' model, the input text is classified into these categories ["artifacts", "animals", "food", "sport","technology",'travel', 'exploration', 'dancing', 'cooking']

 'gpt2' is used as pretrained model for generating text 
 
  PERSON,GPE,ORG,DATE entities extracted from input text are combined and combination of (PERSON+" "+GPE),(PERSON+" "+ORG),(PERSON+" "+DATE) are passed to gpt2 text generation model
  Finally new data in the form of {"_id":generated text,"topic":extracted topic} saved in database
 
 ## Requirements 
transformers 

flair

### Usage
 Pass the parameters of Comment_Generator Class to create a database connection
 
 Run main.py


