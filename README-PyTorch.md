DeepFormants in PyTorch
=======================

Jason Dien

This is a modification of the original DeepFormants package that converts the Torch7 neural network models to a PyTorch-compliant format so it can be run purely in Python. This is built upon [another modification](https://github.com/iskunk/DeepFormants/tree/revamp) that converts the original Python 2 code to Python 3.

Note: only formant estimation features are supported at this point

---

## Installation instructions

Install Python dependencies in requirements.txt:
```
pip install -r requirements.txt
```

Then, follow the instructions [here](https://pytorch.org/) to install PyTorch on your platform.

Install SoX with the following command (or download [here](https://sourceforge.net/projects/sox/files/sox/) if on Windows):
```
sudo apt install sox
```

## Recommended folder structure
* Store audio files and TextGrid files in the `data` folder
* Create an `output` folder to store formant calculations

## How to use:
For vowel formant estimation, call the main script in a terminal with the following inputs: wav file, formant output filename, and the vowel begin and end times:

```
python formants.py data/examples/Example.wav output/ExamplePredictions.csv --begin 1.2 --end 1.3
```

or the vowel begin and end times can be taken from a TextGrid file (here the name of the TextGrid is Example.TextGrid and the vowel is taken from a tier called "VOWEL"):

```
python formants.py data/examples/Example.wav output/examplePredictions.csv --textgrid_filename data/Example.TextGrid \
          --textgrid_tier VOWEL
```
