# Speech Emotion Analyzer

Speech Emotion Analyzer is a machine learning project designed to detect human emotions based on voice input. In today’s world, personalization is critical to enhancing user experiences. This project explores how audio-based emotion detection can contribute to personalization in various industries such as marketing, entertainment, and even autonomous vehicles.

# **Project Idea**

Humans express emotions through tone and speech patterns, and this information can be used to tailor experiences. Imagine a system that recognizes when you're sad and recommends uplifting music—or a car that slows down if it detects you're stressed. The goal of this project is to lay the groundwork for such emotion-aware systems by building a machine learning model capable of classifying emotions from audio clips.

# **Datasets Used**

We used two publicly available datasets to train and test our model:

**1. RAVDESS**
Description: Contains ~1,500 audio recordings by 24 professional actors (12 male, 12 female).

Emotions: Neutral, calm, happy, sad, angry, fearful, disgusted, surprised.

Naming Convention: The 7th character in each filename represents the emotion category.

**2. SAVEE**
Description: Includes ~500 recordings from 4 male actors.

Emotion Encoding: The first two characters of the filename indicate the emotion.

# **Audio Analysis**

Before training, we visualized audio signals to understand their structure:

Waveform: Plotted to inspect amplitude over time.

Spectrogram: Used to observe how frequencies vary over time.

# **Feature Extraction**

We used the LibROSA library for audio feature extraction. Key preprocessing steps include:

Uniform Duration: All audio clips were trimmed or padded to 3 seconds.

Sampling Rate Adjustment: Sampling rate was doubled to improve feature richness for smaller datasets.

Feature Format: Extracted features are numerical arrays with corresponding emotion labels.

# **Model Building**

Since the task is multi-class classification, we experimented with several deep learning architectures:

Multilayer Perceptrons (MLP): Underperformed on validation data.

Long Short-Term Memory (LSTM): Also showed low accuracy.

Convolutional Neural Network (CNN): Provided the best performance, achieving 70%+ validation accuracy.

We started with a simple architecture and gradually tuned the layers for optimal performance without overfitting.

# **Predictions**

Once trained, the CNN model was tested on unseen audio data. Here’s a snapshot of model performance:

Accuracy: ~70% on emotion classification.

Gender Detection: 100% accuracy in distinguishing male vs. female voices.

# **Live Voice Testing**

To evaluate the model’s generalization capability, we recorded new voice clips expressing different emotions. For example:

Input: A male voice saying “This coffee sucks” in an angry tone.

Output: Correctly identified as male_angry.

# **Emotion Labels**
0 - female_angry  
1 - female_calm  
2 - female_fearful  
3 - female_happy  
4 - female_sad  
5 - male_angry  
6 - male_calm  
7 - male_fearful  
8 - male_happy  
9 - male_sad  

# Conclusion
This project demonstrates the potential of emotion detection using audio inputs. Though achieving high accuracy is challenging due to the complex nature of emotions and variability in voice, our model performs well with:

100% accuracy for gender detection

70%+ accuracy for emotion classification

The performance can be further improved by:

Incorporating more diverse datasets

Fine-tuning the model

Experimenting with more advanced architectures


