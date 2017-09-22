  # NER Folder Structure
    .
    ├── pipeline                # the whole spacy training pipeline
    │   ├── generating_tagging_entity.py    # generate unchecked entities for pre-tagging
    │   ├── pre-tagging.py                  # pre-tagging entities
    │   ├── ner.py                          # NER model training
    │   └── utils.py                        # all the utility funcitons
    ├── model                   # NER models 
    │   ├── gold                            # production ready
    │   └── tmp                             # temprorily i.e. test model generated during the training process
    ├── data                    # Input & output along the pipeline
    │   ├── unchecked_data                  # Waiting to be tagged
    │   ├── tagged_data                     # pre-tagged data
    │   ├── training_data                   # training data
    │   └── tmp                             # temprorily i.e. training, validation data splitted from total training data
    ├── log                     # logging file from pipeline
    └── NER_README.md


# Training processor description:
## script: pipeline/ner.py
### functions:
    .
    ├── ner.py               
    │   ├--> raw_data_cleaning()    # process the tagged data under data/training_data and put them into data/training_data
    │   ├--> pseudo_rehearsal()     # generate entities from orginial model and mixed them with tagged data
    │   ├--> eval_split()           # split the training data into training & validation & evaluation
    │                                 output: data description [Example]
    │                                                  
    │   ├--> batch_training()       # train NER model
    │                                 output: loss line       
    │
    │   ├--> eval_score()           # evaluate NER model performance with evaluation data
    │                                 output: evaluation metrics description, including precision, recall and f-measurement
    │                                 
    │   ├--> validation()           # search the best tunning parameters with validation data, e.g. dropout rate
    │   └--> train_curve()          # Evaluate the requirement for more tagged data
    │                                 output: evaluation metrics with different proportion of training data
 
#### eval_split() output example
![data description](https://github.com/Shawn-Zhenshan-Jin/Grocery/blob/master/Data%20Description.png) 
#### batch_training() output example
![loss line](https://github.com/Shawn-Zhenshan-Jin/Grocery/blob/master/loss_line_new.png)     
#### eval_score() output example
![evaluation metrics description](https://github.com/Shawn-Zhenshan-Jin/Grocery/blob/master/score_output.png) 
#### train_curve() output example
![train_curve](https://github.com/Shawn-Zhenshan-Jin/Grocery/blob/master/train_curve_new.png)     

