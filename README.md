# 🚀 Mamdani Fuzzy Logic System

Welcome to the **Mamdani Fuzzy Logic System** project! This repository showcases the power of **fuzzy logic** using the Mamdani method. Fuzzy logic allows us to model human decision-making, especially when dealing with uncertain or imprecise information. Dive into the world of fuzzy rules, membership functions, and decision-making magic! ✨

![Fuzzy Logic](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Fuzzy_logic_temperature_control_example.svg/330px-Fuzzy_logic_temperature_control_example.svg.png)

## 📜 Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Example Output](#example-output)
- [Contributors](#contributors)
- [License](#license)

## 🌟 Introduction
This project implements a **Fuzzy Logic Control System** using the Mamdani method, a popular fuzzy inference approach. The system evaluates input data and generates final scores based on fuzzy rules and membership functions.

If you're interested in fuzzy decision-making, or simply want to explore AI-based control systems, you're in the right place!

## ✨ Features
- **Fuzzy Sets**: Define fuzzy sets for various variables like "good", "bad", "cheap", "expensive", and more.
- **Mamdani Inference**: Apply the Mamdani fuzzy inference method to calculate decisions based on fuzzy logic rules.
- **Customizable Rules**: Easily modify fuzzy logic rules to fit your specific decision-making needs.
- **Export Results**: Outputs final results to an Excel file for further analysis.

## ⚙️ Installation
To run this project on your machine, make sure you have Python and the required libraries installed.

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/FuzzyLogic_Mamdani.git
    ```

2. Install the dependencies:
    ```bash
    pip install pandas numpy scikit-fuzzy openpyxl
    ```

3. Run the notebook:
    Open `FuzzyLogic_Kel6_(mamdani).ipynb` in Jupyter Notebook or JupyterLab.

## 🛠️ Usage
1. Load the notebook and run all cells.
2. The system will process input data, apply the fuzzy logic rules, and output the final scores.
3. You can customize the input data and fuzzy rules to suit your problem domain.

### Sample Code:
Here's a glimpse of how fuzzy sets and rules are defined in the notebook:

```python
import numpy as np
import skfuzzy as fuzz
from skfuzzy import control as ctrl

# Define fuzzy variables
quality = ctrl.Antecedent(np.arange(0, 11, 1), 'quality')
service = ctrl.Antecedent(np.arange(0, 11, 1), 'service')
tip = ctrl.Consequent(np.arange(0, 26, 1), 'tip')

# Membership functions
quality['poor'] = fuzz.trimf(quality.universe, [0, 0, 5])
quality['average'] = fuzz.trimf(quality.universe, [0, 5, 10])
quality['good'] = fuzz.trimf(quality.universe, [5, 10, 10])

# Define fuzzy rules and apply them
rule1 = ctrl.Rule(quality['poor'] & service['poor'], tip['low'])
