# Paper
Focusing knowledge-based graph argument mining via topic modeling

# Environments

# Data
Download from *** and extract as `data` folder into the `project` folder.
Download from *** and extract as `embeddings` folder into the `classifier` folder.

# Training and testing
Run the following in the `project` folder to generate the data:
```
python run.py \
--topic "school_uniforms"\
--num_cases 200 \
--depth 10 \
--include_lda True \
--include_wordvec True \
--par_query True \
--include_openie True
```
Run the following in the main folder to fill the classifier with the data:
```
move project\results\* classifier\results\UKPSententialArgMin\knowledge_graph\wikidata_no_paths
```
Run the following in the `classifier` folder to execute the classifier on the data:
```
py -3.6 generate_data_and_train.py \
--config configs/model_configs/UKPSententialArgMin/knowledge_graph/KBiLSTM_UKP_wikidata.json \
--predict-test 1
```