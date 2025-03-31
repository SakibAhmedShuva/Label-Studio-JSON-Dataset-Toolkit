# Label Studio JSON Dataset Toolkit

A Python toolkit for managing, manipulating, and splitting Label Studio JSON datasets with ease. This toolkit provides a comprehensive set of tools for analyzing, modifying, maintaining, and splitting your Label Studio annotations. Sample JSON file provided in "samples" folder.

## Features

- 📊 View and analyze annotations
- 📈 Generate label statistics
- 🔍 Search functionality by labels and tokens
- ✏️ Label manipulation (remove, merge, rename)
- 🗑️ Delete annotations based on criteria
- 💾 Save modified datasets
- 📂 Split datasets into train/test/validation sets with customizable ratios
- 📉 Analyze label distribution across splits

## Installation

```bash
git clone https://github.com/SakibAhmedShuva/Label-Studio-JSON-Dataset-Toolkit.git
cd Label-Studio-JSON-Dataset-Toolkit
```

## Usage

### Basic Operations

```python
from ls_json_toolkit import LabelStudioEditor

# Initialize the editor
editor = LabelStudioEditor('path/to/your/labelstudio_export.json')

# View annotations
editor.view_annotations()

# Get label statistics
editor.label_stats()

# Search by label
editor.search_by_label('B-PER')

#Search by Token
editor.search_by_token("Florida")

```

### Advanced Operations

```python
# Remove a label
editor.remove_label('B-LOC')

# Merge labels
editor.merge_labels(['B-PER', 'I-PER'], 'PERSON')

# Rename labels
editor.rename_labels({'B-ORG': 'ORGANIZATION', 'I-ORG': 'ORGANIZATION'})

# Delete annotations with specific label
editor.delete_annotations_with_label('B-MISC')

# Save modified dataset
editor.save('path/to/output.json')
```

### Dataset Splitting

```python
from ls_json_toolkit import LabelStudioSplitter

# Initialize the splitter
splitter = LabelStudioSplitter('path/to/your/labelstudio_export.json')

# Split into train/val/test with 70/15/15 ratio
splits = splitter.split_with_ratios([0.7, 0.15, 0.15], seed=42, 
                                   output_dir="./splits", analyze=True)

# Alternative: use string format for ratios
splits = splitter.split_with_ratios("0.7:0.15:0.15", seed=42,
                                   output_dir="./splits", analyze=True)

# Just split without saving
splits = splitter.split_data([0.8, 0.2], seed=42)

# Analyze label distribution in splits
splitter.analyze_splits(splits)
```

## Example Output

When analyzing splits, you'll get detailed information about label distribution:

```
===== Label Distribution Analysis =====
Total items: 100
Total annotations: 1500

Split 1 (80 items, 1200 annotations):
  Person: 500 (83.3% of total)
  Organization: 400 (80.0% of total)
  Location: 300 (75.0% of total)

Split 2 (20 items, 300 annotations):
  Person: 100 (16.7% of total)
  Organization: 100 (20.0% of total)
  Location: 100 (25.0% of total)
```


### Save Changes

```python
editor.save('updated_dataset.json')
```

## Error Handling

The toolkit includes robust error handling for:
- File encoding issues
- JSON parsing errors
- File saving failures

## Requirements

- Python 3.6+
- JSON processing capabilities

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## Acknowledgments

- Label Studio team for their excellent annotation tool
- Contributors to the project
