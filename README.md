 Here is a re-written README.md file for this battery RUL prediction project:

# Battery Remaining Useful Life Prediction with CNN-LSTM

This repository contains code for a hybrid CNN-LSTM model to predict remaining useful life (RUL) of lithium-ion batteries using multi-channel charging profile data.

## Model Architecture

The model consists of:

- Multiple 1D CNN branches that extract features from the voltage, current, and temperature charging profiles separately.

- An LSTM branch that extracts temporal features from the historical capacity discharge data. 

- The CNN and LSTM feature outputs are concatenated and fed into further fully connected layers to regress the final RUL.

The CNN captures cross-channel spatial correlations and the LSTM captures long-term temporal dynamics in the data.

![Model Architecture](architecture.png)

## Data 

The data consists of multi-channel time series profiles for voltage, current, temperature and capacity during charge and discharge cycles of batteries until end-of-life.

## Usage

The model is implemented in PyTorch. To train:

```
python train.py --data_dir /path/to/data
```

## Results

The CNN-LSTM model achieves much lower error compared to LSTM baselines:

| Model           | RMSE  | MAE   | MAPE (%) |
|-----------------|-------|-------|----------|
| LSTM            | 0.062 | 0.055 | 3.608    | 
| CNN-LSTM (ours) | 0.027 | 0.022 | 1.421    |

## Citation

```
@inproceedings{...}
```

