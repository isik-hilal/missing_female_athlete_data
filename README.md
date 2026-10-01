# Missing Female Data

This repository contains the notebooks and analysis behind a talk about female-specific variation in data, research and modelling.

The project started with a fairly personal question: as a woman and recreational athlete, I kept coming across advice about training, recovery and performance that was supposed to be useful for female athletes. I wanted to understand what kind of evidence sits behind those recommendations, what gets measured, and what happens when female-specific variation is missing from the data or from the model.

As a data analyst, I ended up approaching the question through the part I know best: the data.

The modelling section uses a small longitudinal dataset from my own training history to explore one specific question:

**What changes when we represent cycle timing differently in a model?**

The notebooks compare:

1. Phase categories
2. Sine / cosine cyclical terms
3. A cyclic GAM

The dataset is small and personal. It is not intended to make claims about women or menstrual-cycle effects in general. It is a practical modelling experiment for looking at how assumptions about representation can change what a model can see.

`cycle_position` represents position within a 28-day oral-contraceptive schedule. It should not be interpreted as a verified biological menstrual-cycle phase or as equivalent to a natural menstrual cycle.

## Notebooks

- `data_prep.ipynb` — cleaning and preparing the training data
- `modelling.ipynb` — comparing different representations of cycle timing

## Requirements

- Python 3.11+
- [uv](https://docs.astral.sh/uv/)
- Jupyter

Python packages:

- pandas
- numpy
- matplotlib
- statsmodels
- pygam
- jupyter

## Installation

Install `uv` if you don't already have it.

### macOS / Linux

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### Windows

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/missing-female-data.git
cd missing-female-data
```

Create the environment:

```bash
uv venv
```

Install the dependencies:

```bash
uv pip install pandas numpy matplotlib statsmodels pygam jupyter
```

Start Jupyter:

```bash
uv run jupyter notebook
```

## References

### Female data and menstrual-cycle research

**Meignié, A., Toussaint, J.-F., & Antero, J. (2022).**  
*Dealing with menstrual cycle in sport: stop finding excuses to exclude women from research.*

A letter discussing the exclusion of women from sports research because of menstrual-cycle variation.

**Meignié, A., et al. (2021).**  
*Effects of Menstrual Cycle Phase on Elite Athlete Performance: A Critical and Systematic Review.*

A systematic review examining the evidence on menstrual-cycle phase and elite athlete performance.

**Perović, M., Heffernan, E. M., Einstein, G., & Mack, M. L. (2023).**  
*Learning exceptions to category rules varies across the menstrual cycle.*

Uses continuous cycle position and a generalized additive model to investigate non-linear relationships across the cycle. [Paper](https://www.nature.com/articles/s41598-023-48628-x?utm_source=chatgpt.com)

**Perović, M., & Mack, M. L. (2026).**  
*A standardized non-linear approach to studying menstrual cycle effects on brain and behavior.*

Introduces the standardized **Cyclepoint** approach for modelling cycle position continuously and non-linearly. [Paper](https://www.frontiersin.org/journals/cognition/articles/10.3389/fcogn.2026.1839153/full?utm_source=chatgpt.com)

### Cyclepoint

The authors provide an open-source toolkit with code and examples for standardized, non-linear menstrual-cycle analysis.

[Cyclepoint GitHub repository](https://github.com/macklab/cyclepoint?utm_source=chatgpt.com)

## A note about the data

The dataset in this repository comes from my own training history.

It is included to make the modelling process concrete and reproducible, not to represent female athletes generally.

The interesting part of the project is not whether this dataset proves an effect. It is what happens when the same underlying observations are represented in different ways.
