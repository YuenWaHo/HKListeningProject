# Data Visualization

## Types of Visualizations

### 1. Spectrograms

```python
import librosa
import librosa.display
import matplotlib.pyplot as plt

# Create spectrogram
plt.figure(figsize=(12, 8))
librosa.display.specshow(D)
plt.colorbar(format='%+2.0f dB')
plt.title('Spectrogram')
```

### 2. Waveforms

- Time domain representation
- Amplitude visualization
- Pattern identification

### 3. Statistical Plots

- Box plots
- Violin plots
- Scatter plots
- Heat maps

## Visualization Tools

### Python Libraries

- Matplotlib
- Seaborn
- Plotly
- Bokeh

### R Packages

- ggplot2
- viridis
- plotly
- gridExtra

## Best Practices

### Design Principles

1. **Clarity**

   - Clear labels
   - Appropriate scales
   - Consistent colors

2. **Accuracy**

   - Data integrity
   - Proper scaling
   - Error representation

3. **Accessibility**
   - Color-blind friendly
   - High contrast
   - Clear typography

### Interactive Visualization

- Zoom capabilities
- Pan functions
- Selection tools
- Dynamic filtering

## Examples

### Species Comparison

```python
# Example code for species comparison plot
plt.figure(figsize=(10, 6))
sns.boxplot(data=df, x='species', y='frequency')
plt.title('Frequency Distribution by Species')
```

### Temporal Patterns

```python
# Example code for temporal pattern visualization
plt.figure(figsize=(12, 4))
plt.plot(time, amplitude)
plt.title('Temporal Pattern Analysis')
```
