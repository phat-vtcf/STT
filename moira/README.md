## Evaluation of Coqui STT on New Voice Data

In this directory we are running and evaluating the Coqui STT system on a set of English voice data. The focus of our task is to calculate and evaluate the Word Error Rate.

The data consists of 286 quotes of Moira, a character from the multiplayer team-based first-person shooter game Overwatch. Each quote is available as a wav file, while a csv file that contains for each wav file the text of its audio, called moira_quote_index.csv, is also available.

The files can be downloaded from the following link: https://drive.google.com/drive/folders/1nqQyZBaVbXDly6lntzY-Z0WkRyaZESlH?usp=sharing 

When you download them, make sure you place them as follows: the wav files within a new directory '/wavs' in the existing directory '/moira' and the csv file within the directory '/moira'.

The pretrained model we use is the English STT v1.0.0 (Large Vocabulary) and it is available in the directory '/moira/model'.

The evaluation is done by calculating the overall Word Error Rate.

### Running the code

To run the evaluation first install the requirements:

```shell
pip install -r moira/requirements.txt
```
Please note that we have used Python 3.8, so it's recommended that you do the same.

Then, if you are not a Mac user, make sure you have installed the SoX sound processing utility (http://sox.sourceforge.net)

Then go to the directory moira and execute the evaluation script:

```shell
cd moira
python stt_moira
```
The script takes the wav file of each quote and uses the stt model to infer its text. Then it compares the inferred text with the actual text (after some preprocessing) and calculates the corresponding Word  Error Rate. In the end it calculates the overall Word Error Rate.
