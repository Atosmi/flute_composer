# Digital Bansuri

This repository contains a 3-layer LSTM model that can be trained on MIDI files to generate an output MIDI file. 

## Usage Instructions

    Clone this repository and create a virtual environment by running the following command in your terminal:
```
python3 -m venv lstmmodel
```
Install all required packages by running the following command in your terminal:
```
python3 -m pip install -r requirements.txt
```
To train the network, run the following command in your terminal:
```
python3 lstm.py
```
Note: Each note, chord, and rest is tokenized without their duration, so the model does not learn the beat. Chords are embedded using normal order in the form of "#.#.#.#". The default number of epochs is 400, but you can stop the training at any point. The latest epoch weights will be saved in the root folder.

To generate music, run the following command in your terminal:

    python3 predict.py

    The default weights used by the model are from the file weights.hdf5. The generated MIDI file is saved to test_output.midi. Note that since the model does not learn the beat, each note duration is randomly sampled from a probability distribution that you specify. The default duration distribution is 0.65 for eighth notes, 0.25 for 16th notes, and 0.05 for half and quarter notes. Rests are always generated as 16th rests.

Credit: Huge thanks to Skuldur's [repository](https://github.com/Skuldur/Classical-Piano-Composer) for their contributions.
