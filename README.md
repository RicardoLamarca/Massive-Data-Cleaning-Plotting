# Massive-Data-Cleaning-&-Plotting

![Julia](https://img.shields.io/badge/Julia-1.6%2B-9558B2?style=for-the-badge&logo=julia)
![Plots.jl](https://img.shields.io/badge/Plots.jl-Enabled-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

A lightweight Julia utility to **parse unstructured text logs**, extract specific numerical datasets, and generate a **dual-plot visualization**.

## 📝 Overview

This script parses raw text (such as simulation logs or console output), filters for specific target sentences, and extracts numerical values using Regular Expressions.

It creates **two distinct plots** to visualize different aspects of the data simultaneously:
1.  **Data 1:** Standard trend line.
2.  **Data 2:** Normalized or bounded data (fixed Y-limits 0-1).

## ⚙️ How It Works

The script iterates through the input text line-by-line:

* **Pattern Matching:** It searches for two different context sentences:
    * *"Sentence previous to data"*
    * *"Sentence previous to other data"*
* **Extraction:** When a target line is found, it extracts the number immediately following the keyword `"gives"`.
* **Plotting:** It generates two separate plot objects and renders them in a shared window.

## 📊 Visualization Details

The script generates a single figure containing **two plots** arranged vertically:

* **Top Plot (Data 1):**
    * Visualizes the first dataset.
    * Y-axis scales automatically to fit the data range.
* **Bottom Plot (Data 2):**
    * Visualizes the second dataset.
    * **Y-axis is fixed** between `0` and `1`.
* **X-Axis:** Both plots share the same X-axis definition (iteration count/index).

## 🚀 Usage

1.  **Paste Data:** Insert your raw text into the `data` variable inside the script.
2.  **Run:**
    ```bash
    julia script_name.jl
    ```
3.  **Result:** A window will open displaying the two plots stacked (2 rows, 1 column).

## 🛠️ Dependencies

* **Plots.jl:** For plotting.
* **Printf:** For console output formatting.

## 📄 License

Open source.
