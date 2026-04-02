# T1DSim_AI

<img alt="Supported Python versions" src="https://img.shields.io/badge/Supported_Python_Versions-3.9-blue">

-----

## Physiologically-constrained Neural Network Digital Twin Framework for Replicating Glucose Dynamics in Type 1 Diabetes

Valentina Roquemen-Echeverri, Taisa Kushner, Peter G. Jacobs, and Clara Mosquera-Lopez

This repository contains a framework to create  physiologically-constrained neural network (NN) digital  twins for simulating glucose dynamics in type 1 diabetes (T1D).

This framework provides a new tool for individualized  in-silico pre-clinical testing of new technologies and  treatment strategies for T1D management.

Read More: [Pre-print](https://www.arxiv.org/pdf/2508.05705),[Neural Computing and Applications](https://doi.org/10.1007/s00521-026-12018-x) 

![framework](example/img/figure_DigitalTwinOverview.jpg)

## Table of Contents


- [Installation](#installation)
- [Simulation](#simulation)
- [Creation of a Digital Twin](#creation-of-a-digital-twin)
- [Citation](#citation)
- [License](#license)


## Installation

```console
pip install t1dsim-ai
```

## Simulation

This work presents a novel framework for constructing physiologically-constrained NN digital twins that can replicate the glucose dynamics of individuals with T1D. We developed a novel NN state-space model architecture that allows for observability and interpretability of simulation outputs. This model adheres to known glucose-insulin dynamics as verified by our conformance verification analysis. When augmented with individual-level data, the resulting adaptive digital twin models can capture both inter- and intra-individual variability and incorporate various factors influencing glucose response, such as sleep and physical activity, leading to improved simulation accuracy when compared to ODE-based digital twins.

*Note: This tool is a methodology designed to create digital twins that adapt to the specific data of the individual used for training. It is not intended for use as a virtual patient population to simulate different scenarios.*


Run the following command to simulate one day of the digital twin #1.

```bash
python example/runDigitalTwin.py
```

After running the example, the simulation will look as follows:

![example](example/img/example_digitaltwin0.png)

## Creation of a Digital Twin

A digital twin model can be trained using a dataset containing CGM (Continuous Glucose Monitoring) data, sleep efficiency, heart rate, meals, insulin, and time information. An example of the required dataset structure is provided in:

```
example/example_model/data_example.csv
```

To train the model, run the following command:

```bash
python example/trainDigitalTwin.py
```

This will generate:

- The trained model
- The scaler used for preprocessing
- Training process information

Configurable Parameters: The training process allows customization of:

- Number of epochs
- Learning rate
- Number of neurons and depth (network architecture)
- Batch size
- Overlap percentage for data segmentation

## Citation

If you used this package in your research, please cite it:

```
@Misc{,
    author = {Valentina Roquemen-Echeverri and Clara Mosquera-Lopez},
    title = {T1DSim AI},
    year = {2024--},
    url = "https://github.com/mosqueralopez/T1DSim_AI"
}
```
