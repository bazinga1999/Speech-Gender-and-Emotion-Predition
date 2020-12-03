

**README**

**Overview:**

In the present natural NLP scenario, most of the work has been done, in the field of text

processing but with the growing internet and abundance of video and audio now

available to us, We as a team have tried to work and study the processing of these

audio data and analyze the emotions of the speaker. Furthermore, we have even tried

to identify the gender(Male or female) of the person. Below is a brief description of our

work. The datasets we used, features we tried to learn, and different ML models we

tried to implement.

**Files:**

\1. **CNN\_Best.ipynb**: The best performing CNN model with 9 layers with clear

descriptions and comments for easy readability. The code includes the statistical

analysis of the model by evaluating the precision, recall and F1-score.

\2. **MLP\_and\_Random\_Forest.ipynb**: Complete MLP and Random Forest on the

audio features we extracted from the dataset.

\3. **SVM.ipynb**: SVM model implementation and accuracy.

\4. **Predictions.csv**: Actual and Predicted values on the test set.

\5. **Model.json**: Model Architecture file **(Needed for loading the model)**

\6. **mfcc\_eng\_CNN.h5**: Weights of the training dataset **(Needed for loading the**

**model)**

\7. X\_test.npy, X\_train.npy, Y\_test.npy, Y\_train.npy: Numpy Arrays **(Needed for**

**loading the model)**

**Datasets:**

The code takes an input of a dataset of around 2000 voice datasets of different actors

both male and female with different emotions that are already labeled, which we have

used to train our various models in which CNN with 18 layers performed best.

RAVDESS: <https://zenodo.org/record/1188976#.X8TreWgzap4>

SAVEE: <http://kahlan.eps.surrey.ac.uk/savee/Download.html>

CREMA-D: <https://www.kaggle.com/ejlok1/cremad>

**Methodology**:

**Audio Features Extracted:**

**1. MFCC-** Extraction technique basically includes dividing the signal in

signals, applying the DFT(Fourier transformation), taking the log of the

magnitude, and then scaling it on a Mel scale, followed by applying the

inverse DCT (Cosine transformation).





**2. Energy-** Root means square energy, using the STFT(Short Time Fourier

Transformation) transformation.

**3. Chromagram-** Contains features; each expressing how the pitch content

within the divided time chunks is spread over the twelve chroma bands.

**4. Zero\_cross-** Rate of sign change(slope) in a signal in each time frame

present.

**5. Mel Spectrogram**- Converts the frequencies to the mel scale.

**6. Spectral Rolloff**- Is the frequency below which a specified percentage of

the total spectral energy, e.g. 85%, lies.

**7. Spectral Centroid**- Provides the location of the center of mass for the

spectrum. In other words, it provides us with the brightness of the audio.

**8. Envelope Derivative Operator**- Frequency Based Energy Operator

**9. Teager-Kaiser operator**- Detects the level of stress, resulting due to the

alteration of the airflow during the production of sound.

**10.Pitch**- Pitch of an audio across the time frame.

**11.Harmonic to Noise Ratio (HNR)-** Measures the ratio between the

periodic and non-periodic components of the audio. Jitter, shimmer and

harmonics to noise ratio detects the involuntary changes on the physical

properties of the vocal tract.

**12.PLP(Perceptual Linear Prediction) and RASTA-** Pattern recognition

system for speech recognition from audio signals

**Note -** All these features have been extracted from the \*.wav files present in our

dataset, all these features define the audio in different sorts of ways. Finding the

best combination of features which would really help in identifying the emotion as

well as the gender turned out to be a very tedious task.

According to our research and implementations the best feature combination was

found to be **MFCC, Energy** (dimension: 432 columns). Therefore all the current

outputs of our different models have been trained on this set of features.

**\*Different combinations of features and outputs will be included in our final**

**report.**

**Models and Accuracies:**

**CNN** (Present in: CNN\_best.ipynb)

CNN had the best performance in our project with the validation set accuracies

as,





CNN was easily able to predict the gender of the audio with **63.43%** accuracy

Emotion with the accuracy of **85.07%** Gender and emotion together with the

accuracy of **55.22%**.

**CNN model:-**





**SVM** (Present in - SVM\_RandomForest.ipynb)**:**

Accuracy of detection gender an emotion together on validation set:

**26%**

**RandomForestClassifier** (Present in - SVM\_RandomForest.ipynb)**:**

Accuracy of detection gender an emotion together on validation set:

**37%**

**MLP** (Present in - MLP.ipynb)**:**

Accuracy of detection gender an emotion together on validation set:

**15%**

Activation used is relu with alpha=0.0001

