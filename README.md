# EEG Analysis of Financial Decision Making

This project analyzes EEG data collected during financial decision-making tasks to compare brain activity patterns between male and female participants. The data was collected using an EMOTIV 14-channel EEG headset.

## Project Overview

The analysis pipeline processes EEG data to:
- Compare brain activity patterns between male and female participants
- Generate topographic maps of brain activity
- Create interactive 3D brain visualizations
- Analyze time-frequency patterns during decision-making tasks

## Data Structure

### Required Data Organization
```
project_directory/
├── eeg_data/
│   ├── metadata.csv
│   ├── subject_001.csv
│   ├── subject_002.csv
│   └── ...
└── eeg_visualizations/
    ├── male_topographic.html
    ├── female_topographic.html
    ├── time_frequency_comparison.html
    └── 3d_brain_comparison.html
```

### Metadata Format
The `metadata.csv` file should contain the following columns:
- subject_id: Unique identifier for each participant
- gender: 'male' or 'female'
- filename: Name of the corresponding EEG data file

### EEG Data Format
Each subject's CSV file should contain:
- Time column
- EEG channel columns (AF3, F7, F3, FC5, T7, P7, O1, O2, P8, T8, FC6, F4, F8, AF4)

## Requirements

```python
pip install numpy pandas mne plotly
```

## Usage

1. Ensure your data is organized in the required structure
2. Run the analysis:
```python
# Define paths to your data
data_dir = "eeg_data"
metadata_path = "eeg_data/metadata.csv"

# Load and process data
raw_objects = load_eeg_data(data_dir, metadata_path)
processed_data = preprocess_data(raw_objects)

# Generate visualizations
save_plots_to_html(processed_data)
save_3d_plots(processed_data)
```

## Output Visualizations

1. **Topographic Maps** (`male_topographic.html`, `female_topographic.html`)
   - 2D representations of brain activity
   - Color-coded power values
   - Interactive electrode position markers

2. **Time-Frequency Analysis** (`time_frequency_comparison.html`)
   - Heatmap of brain activity over time
   - Channel-wise temporal patterns
   - Comparative view of male and female data

3. **3D Brain Visualization** (`3d_brain_comparison.html`)
   - Interactive 3D brain model
   - Mapped EEG channel positions
   - Color-coded activity levels
   - Side-by-side male/female comparison

## Features

- **ICA-based Preprocessing**: Removes artifacts and noise from raw EEG data
- **Interactive Visualizations**: All plots are interactive HTML files
- **Comparative Analysis**: Direct comparison between male and female brain activity patterns
- **3D Brain Mapping**: Spatial representation of EEG activity on a 3D brain model

## Notes

- Data should be collected using the EMOTIV 14-channel EEG headset
- EEG recordings should be taken during financial decision-making tasks
- Ensure consistent sampling rates across all recordings
- Data files should be properly formatted and cleaned before analysis

## Contact

For questions or issues regarding the analysis pipeline, please open an issue in the repository.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
