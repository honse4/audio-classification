<h1>Audio Classification for vehicles</h1>
<h2>Authors</h2>
Vasav Juyal
Miro Malekshahi

<h2>Introduction</h2>
This project focuses on the binary classification of audio files into predefined categories. The process involves collecting and processing audio data, extracting relevant features, and implementing a machine learning model to perform the classification. The model is then used to predict unseen data, and the results are evaluated to determine the model's accuracy.

<h2>Data Description</h2>
The dataset consists of audio recordings from vehicles, primarily collected using phone recording features in Tampere. The recordings capture vehicles either passing by or idling, resulting in a diverse set of audio samples, typically around five seconds long. The dataset is designed for binary classification, containing two distinct classes: car and tram. We collected around 25 samples each, and additional samples were sourced from freesound.org, resulting in 850 car samples and 809 tram samples.
All audio samples were converted to WAV format and normalized to ensure consistency and uniformity across the dataset.

<h2>Feature Extraction</h2>
<h3>Four features were extracted from the audio data:</h3>

<h4>Time-Domain Features:</h4>
Root Mean Square Energy (RMS): Measures the overall magnitude of a signal, corresponding to its energy.
Zero-Crossing Rate (ZCR): Counts the number of times the wave crosses the x-axis, representing the smoothness of the wave.

<h4>Frequency-Domain Features:</h4>
Mel-Frequency Cepstral Coefficients (MFCCs): Represent the short-term power spectrum of an audio signal on a mel scale.
Spectral Centroid: Indicates where the majority of a signal's energy is concentrated, reflecting the brightness of the sound.

<h2>Model Selection and Data Split</h3>
Logistic regression was chosen for the classification task. The training data consisted of 1505 samples (733 tram and 772 car), while the test data included 53 samples (24 tram and 29 car). Validation data was collected from three separate users on freesound.org, with 52 tram samples and 49 car samples.
The model was trained on each feature individually and evaluated using accuracy, precision, and recall metrics. MFCCs were selected as the best feature for the final model based on their performance.

<h2>Results</h2>
The performance of different features was evaluated using validation data. MFCCs scored highest on all metrics, making them the best feature for classification. The final model, using MFCCs, achieved perfect accuracy on the test data.

Feature	Accuracy	Precision	Recall
ZCR	0.554455	0.600000	0.244898
RMS	0.613861	0.589286	0.673469
Spectral Centroid	0.514851	0.500000	0.408163
MFCC	0.910891	0.857143	0.979592

<h2>Conclusion</h2>
The project was executed smoothly, with MFCCs proving to be the most effective feature for classification. The perfect results on the test data may be due to the small sample size. Future work could involve removing less useful MFCC bands to improve the model's performance further.
