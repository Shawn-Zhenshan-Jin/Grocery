  # Folder Structure
    .
    ├── pipeline                # the whole spacy training pipeline
    │   ├── generating_tagging_entity.py    # generate unchecked entities for pre-tagging
    │   ├── pre-tagging.py                  # pre-tagging entities
    │   ├── ner.py                          # train NER model
    │   └── utils.py                        # all the utility funcitons
    ├── model                   # NER models 
    │   ├── gold                            # production ready
    │   └── tmp                             # temprorily i.e. test model generated during the training process
    ├── data                   
    │   ├── training_data                   # pre-tagged data
    │   ├── unchecked_data                  # Waiting to be tagged
    │   └── tmp                             # temprorily i.e. training, validation data splitted from total training data
    ├── log                     # logging file from pipeline
    └── NER_README.md
    
    ## ner.py
