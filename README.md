# EEG Motor Imagery Classification with Entropy and Information-Based Features

This project analyzes EEG data from the PhysioNet Motor Movement/Imagery Dataset to classify motor execution and imagery tasks (fists vs. feet) using information-based feature extraction and machine learning. Dataset used for this experiment is from [PhysioNet EEG Motor Movement/Imagery Dataset](https://physionet.org/content/eegmmidb/1.0.0/).

## Project Structure

- `experiment.ipynb` — Main analysis notebook: feature extraction, classification, and feature importance visualization
- `eda.ipynb` — Exploratory data analysis of the EEG dataset

## Key Features

- **Feature Extraction:**
  - Spectral entropy (PSD-based Shannon entropy)
  - Permutation entropy, sample entropy, approximate entropy (AntroPy)
  - Renyi entropy
  - Hjorth mobility & complexity
  - Fractal dimensions (Higuchi, Petrosian, Katz)
  - Detrended Fluctuation Analysis (DFA)
- **Preprocessing:**
  - Channel selection and standardization
  - Bandpass filtering (7–30 Hz), notch filtering (50/60 Hz)
  - Common average referencing (projection)
  - Epoching and cropping to discriminative windows
- **Classification:**
  - KNN, Linear SVM, LDA, Random Forest, XGBoost
  - Cross-validation (StratifiedShuffleSplit)
  - Performance metrics: accuracy, precision, recall, F1
- **Feature Importance & Visualization:**
  - Mutual information and SVM/RandomForest importances
  - Barplots, boxplots, and heatmaps of feature relevance

## Usage

1. **Install dependencies:**
   - Python 3.8+
   - Required packages: `mne`, `numpy`, `pandas`, `scikit-learn`, `matplotlib`, `seaborn`, `antropy`, `xgboost`
   - Example:
     ```bash
     pip install -r requirements.txt
     ```
2. **PhysioNet EEGMI dataset** Dataset can be downloaded from [here](https://physionet.org/content/eegmmidb/1.0.0/).
3. **Open and run the notebooks**
   - Start with `eda.ipynb` for exploratory data analysis.
   - Use `experiemnt.ipynb` for feature extraction, classification, and analysis.
4. **Review results:**
   - Classification metrics are displayed and saved as CSVs.

## Notes

- Some features require the `antropy` package. If not installed, those features will be skipped or set to NaN.
- Common average referencing is applied via projection for robust spatial analysis.
- The code is modular: you can easily swap classifiers, feature sets, or preprocessing steps.

## References

- [PhysioNet EEG Motor Movement/Imagery Dataset](https://physionet.org/content/eegmmidb/1.0.0/)
- [MNE-Python Documentation](https://mne.tools/stable/index.html)
- [AntroPy: Entropy and Complexity Measures for Time Series](https://github.com/raphaelvallat/antropy)

## License

This project is for academic/research use. Please cite the PhysioNet dataset and relevant libraries if publishing results.
