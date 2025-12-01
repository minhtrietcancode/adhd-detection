# ADHD Detection using EEG Data

This repository contains code and data for classifying ADHD (Attention-Deficit/Hyperactivity Disorder) and control subjects based on EEG (Electroencephalogram) recordings. The project focuses on preprocessing and analyzing time-series EEG data to identify key characteristics related to ADHD.

## Repository Structure

```
.
├── adhdata.csv                  # The raw EEG dataset
├── dataset_description.md       # Detailed description of the EEG dataset, including its origin, collection methodology, and features.
├── README.md                    # This file, providing an overview of the repository and guidance for readers.
└── src/                         # Source code directory
    ├── notes/                   # Directory containing analysis reports and summaries generated during preprocessing.
    │   ├── participant_analysis_report.txt # A comprehensive report detailing participant record ranges, duration statistics, and data integrity checks.
    │   └── participant_summary.csv         # A CSV file summarizing key information for each participant (e.g., ID, class, record counts, durations).
    └── preprocess.ipynb         # Jupyter Notebook for initial data loading, exploration, and time-series characteristic analysis.
```

## Getting Started

To understand this repository, it is recommended to follow these steps:

1.  **Understand the Dataset**: Start by reading `dataset_description.md` to get a comprehensive understanding of the EEG dataset, its features, and the time-series nature of the data.

2.  **Explore Data Preprocessing and Characteristics**: Proceed to `src/preprocess.ipynb`. This Jupyter Notebook guides you through:
    *   Loading the `adhdata.csv` dataset.
    *   Displaying the initial rows of the DataFrame (`df.head()`).
    *   Performing detailed validation checks on the dataset's integrity.
    *   Generating a summary of participant data, including record ranges and recording durations.
    *   Analyzing key time-series characteristics of the dataset, such as average, minimum, maximum, and median recording durations, both overall and by class (ADHD vs. Control).

3.  **Review Analysis Outputs**: After running the `preprocess.ipynb` notebook, examine the generated files in the `src/notes/` directory:
    *   `src/notes/participant_analysis_report.txt`: Contains a detailed textual report of the data validation, participant record ranges, and recording duration statistics.
    *   `src/notes/participant_summary.csv`: Provides a tabular summary of each participant's data, which can be useful for further analysis.
