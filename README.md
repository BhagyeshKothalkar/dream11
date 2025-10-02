## use
```shell
git clone https://github.com/BhagyeshKothalkar/dream11
cd dream11
pip install -r requirements.txt
mkdir -p data data/raw data/interim data/processed data/processed/players
cd data/raw
wget https://cricsheet.org/downloads/all_json.zip
unzip all_json.zip
cd ../..
cd data_processing
python3 compute_train_data.py 
```

## what is achieved

- the code generates training data.
- added metrics: 4s/6s rate and 5wi
- adding more metrics should not be an issue

## current problems:

- there are 12 players in ipl teams (impact sub rule). the code is hard coded that it needs 11 players and it goes on till no. of columns so need to check deeply. rn, if it causes problems, just skip that file
- the venues are added as strings, as i thought how to encode them will be largely algorithm dependant. 
- the match outcome is given a rudimentary encoding -1, 0, 1. -1 if team1 wins, 0 if draw.
