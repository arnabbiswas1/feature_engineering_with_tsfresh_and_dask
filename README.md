# Automatic Feature Enegineering for Large Scale Time Series Data Using tsfresh and Dask

The internet of things, digitized health care systems, financial markets, smart cities (etc.) are continuously generating time series data of different types, sizes and complexities. Time series data is different from non-temporal data. In time series data, observation at any instance of time depends on the observations from the past based on the underlying process. Often it contains noise and redundant information. To make things more complex, most of the traditional Machine Learning algorithms are developed for non-temporal data. Thus, extracting meaningful features from raw time series plays a major role. While there are features generic across different flavors/types of time series, there are features specific to different domains. As a result, feature engineering often demands familiarity with domain specific and/or signal processing algorithms making the process complicated.  

This repository introduces to a Python library called `tsfresh`. `tsfresh` accelerates the feature engineering process by automatically generating 750+ of features for time series data.

However, if the size of the time series data is large, we start encountering two kinds problems:
- Large execution time
- Need for larger memory

This is where another Python framework `Dask` comes into picture. `Dask` parallelizes the feature extraction process of tsfresh. Also, by using out of core computing, it addresses the problem of larger than RAM dataset.

This content was used for a talk at [PyData Montreal Jan 2021 meetup](https://www.meetup.com/PyData-MTL/events/275543323/):
- [Recording of the session](https://youtu.be/vajaT1FNP6I?start=3620&autoplay=1)
- [Accompanying Slides](https://speakerdeck.com/arnabbiswas1/automatic-feature-enegineering-for-large-scale-time-series-data-using-tsfresh-and-dask)

To gather basic understanding of dask, please refer to [this](https://github.com/arnabbiswas1/dask_workshop/) repository.

### How to setup the Python Environment for this project?

```
conda env create -f environment.yml
conda activate dask_tsfresh
jupyter labextension install dask-labextension
jupyter serverextension enable dask_labextension
```


### How to get the data?

Data used in this project is from the Kaggle Competition "INGV - Volcanic Eruption Prediction"(https://www.kaggle.com/c/predict-volcanic-eruptions-ingv-oe). Please download the data from Kaggle and place into the `data` directory. Once done, the content of the `data` directory should have the following files & directories:

```
sample_submission.csv  
test/                  
train/                 
train.csv
```
