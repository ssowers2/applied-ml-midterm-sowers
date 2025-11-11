# Mushroom Classification Project

This project uses the Agaricus-Lepiota Mushroom dataset to classify mushrooms as **edible (e)** or **poisonous (p)** based on their observable characteristics.

## Dataset

- Source: UCI Machine Learning Repository  
- File: `agaricus-lepiota.data`  
- The dataset contains 8,124 rows and 23 categorical features.

## Project Steps (So Far)

### 1. Load the Dataset
The dataset was loaded from the `Data/` directory using `pandas.read_csv`, specifying:
- `header=None` (no header row in file)
- `names=column_names` to apply readable column names
- `na_values=["?"]` to treat `?` as missing

### 2. Rename Column Headers
The original encoded column names were replaced with clearer, descriptive names:

```python
column_names = [
    "class", "cap_shape", "cap_surface", "cap_color",
    "bruises", "odor", "gill_attachment", "gill_spacing", "gill_size",
    "gill_color", "stalk_shape", "stalk_root",
    "stalk_surface_above_ring", "stalk_surface_below_ring",
    "stalk_color_above_ring", "stalk_color_below_ring",
    "veil_type", "veil_color", "ring_number", "ring_type",
    "spore_print_color", "population", "habitat"
]

### Setup virtual environment
1. uv venv
2. uv python pin 3.12
3. uv sync --extra dev --extra docs --upgrade
4. .\.venv\Scripts\Activate
5. uv add --dev pre-commit ruff
6. uv run python --version