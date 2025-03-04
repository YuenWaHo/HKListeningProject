# Basic Sound Analysis

This tutorial will guide you through the basics of sound analysis using Python.

## Setup

First, let's import the required libraries:

```python
import librosa
import librosa.display
import numpy as np
import matplotlib.pyplot as plt
```

## Loading Audio Files

To load an audio file:

```python
# Load the audio file
audio_path = "path/to/your/audio.wav"
y, sr = librosa.load(audio_path)

print(f"Sample rate: {sr}")
print(f"Audio duration: {len(y)/sr:.2f} seconds")
```

## Creating Spectrograms

A spectrogram is a visual representation of the frequencies in an audio signal over time:

```python
# Create and display a spectrogram
plt.figure(figsize=(12, 8))
D = librosa.amplitude_to_db(np.abs(librosa.stft(y)), ref=np.max)
librosa.display.specshow(D, y_axis='log', x_axis='time')
plt.colorbar(format='%+2.0f dB')
plt.title('Spectrogram')
plt.show()
```

## Basic Feature Extraction

Let's extract some basic features from our audio:

```python
# Extract features
tempo, _ = librosa.beat.beat_track(y=y, sr=sr)
mfccs = librosa.feature.mfcc(y=y, sr=sr)
spectral_centroid = librosa.feature.spectral_centroid(y=y, sr=sr)

print(f"Estimated tempo: {tempo:.2f} BPM")
print(f"Number of MFCCs: {len(mfccs)}")
```

## Visualization

Here's how to create some basic visualizations:

```python
# Plot waveform
plt.figure(figsize=(12, 4))
librosa.display.waveshow(y, sr=sr)
plt.title('Waveform')
plt.show()

# Plot MFCCs
plt.figure(figsize=(12, 8))
librosa.display.specshow(mfccs, x_axis='time')
plt.colorbar()
plt.title('MFCCs')
plt.show()
```

## Next Steps

Now that you've learned the basics, you can:

- Experiment with different audio files
- Try other feature extraction methods
- Create more complex visualizations
- Apply these techniques to your own research
