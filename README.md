# SenForFlood

A global multi-modeal dataset for flood mapping with images before and during flood.

Paper: [SenForFlood: A New Global Dataset for Flooded Area Detection](https://isprs-archives.copernicus.org/articles/XLVIII-M-7-2025/97/2025/)

DOI: [10.5194/isprs-archives-XLVIII-M-7-2025-97-2025](https://doi.org/10.5194/isprs-archives-XLVIII-M-7-2025-97-2025)

Lab: [GEOHUM](https://geohum.eu)

## Access

The dataset can be accessed through the following platforms:
  - [Harvard Dataverse](https://doi.org/10.7910/DVN/ZQCODX)
  - [Huggingface](https://huggingface.co/datasets/matosak/SenForFlood) (upload in progress)

### Bulk Download

For using the Harvard Dataverse platform for downloading, one option is to use `aria2`, `curl`, and `jq` as indicated in the following command.

```
aria2c --input-file <(curl "https://dataverse.harvard.edu/api/datasets/export?exporter=schema.org&persistentId=doi%3A10.7910/DVN/ZQCODX" | jq -r ".distribution[].contentUrl")
```

> [!WARNING]  
> Make sure to have enough free space on your storage to save the dataset. The total download size is approximately 254 GB.

To unzip the files that contain the dataset, the following command can be used:

```
tar -xvf SenForFloods-001.tar.gz
```

## Abstract

> Floods are devastating hazards that cause human displacement, loss of life and damage of properties. Getting accurate information about the extent and severity of floods is essential for planning proper humanitarian emergency assistance. Though integrating earth observation with deep learning models supports rapid information extraction, mapping floods accurately is still a challenging task, because of the necessity of extensive, representative datasets with high quality labels to train models. While there exist some datasets that focus on providing satellite imagery for flood events, these are typically limited to data either from few floods or for specific regions. Moreover, the majority of these datasets provide images captured only during the flood event, which hinders methods that rely on detecting change. Therefore, in this work, we created a global dataset for mapping flood extent (SentForFlood), including images before and during flood from Sentinel-1 and -2, terrain elevation and slope, Land Use and Land Cover (LULC), and flood masks. The samples included in each flood event were selected by analysts considering quality of flood mask and completeness of the available satellite imagery. The dataset incorporated data from over 350 distinct flood events, encompassing all continents except Antarctica. The dataset was tested by training a convolutional neural network for detecting floods without permanent water bodies and the results are discussed. We expect that the dataset will facilitate the development of robust, transferable models for automatic flood mapping, thereby contributing to the humanitarian emergency repose in crisis situations.

## Dataset Information

A total of 353 flood events around the globe were included in the dataset, separated into DFO and CEMS. The samples from DFO possess flood masks created using an automatic change detection algorithm, while samples in CEMS have high-quality, analyst created flood masks from previous emercency activations.

![Dataset Sample Count by Region](Images/MapSampleCount_hex.png)