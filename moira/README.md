## Evaluation of Coqui STT on New Voice Data

In this directory we are running and evaluating the Coqui STT system on a set of English voice data. 

The data consists of 286 quotes of Moira, a character from the multiplayer team-based first-person shooter game Overwatch. These quotes are available as wav files in the directory wavs, while their texts are in the file moira_quote_index.csv.

The audio files, along with a csv file that contains for each wav file the text of its audio, can be downloaded from the following link: https://drive.google.com/drive/folders/1nqQyZBaVbXDly6lntzY-Z0WkRyaZESlH?usp=sharing

The pretrained model we use is the English STT v1.0.0 (Large Vocabulary) and it is available in the directory model.

The evaluation is done by calculating the overall Word Error Rate.

### Running the code

To run the evaluation first install the requirements:

```shell
pip install -r moira/requirements.txt
```
Then go to the directory moira and execute the evaluation script:

```shell
cd moira
python stt_moira
```
The script takes the wav file of each quote and uses the stt model to infer its text. Then it compares the inferred text with the actual text (after some preprocessing) and calculates the corresponding Word  Error Rate. In the end it calculates the overall Word Error Rate.
