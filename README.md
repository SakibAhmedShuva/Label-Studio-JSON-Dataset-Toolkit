# Label Studio JSON Dataset Toolkit

A Python toolkit for managing and manipulating Label Studio JSON datasets with ease. This toolkit provides a comprehensive set of tools for analyzing, modifying, and maintaining your Label Studio annotations. Sample JSON file provided in "samples" folder.

## Features

- 📊 View and analyze annotations
- 📈 Generate label statistics
- 🔍 Search functionality by labels and tokens
- ✏️ Label manipulation (remove, merge, rename)
- 🗑️ Delete annotations based on criteria
- 💾 Save modified datasets

## Installation

```bash
git clone https://github.com/SakibAhmedShuva/Label-Studio-JSON-Dataset-Toolkit.git
cd Label-Studio-JSON-Dataset-Toolkit
```

## Usage

```python
from ls_json_toolkit import LabelStudioEditor

# Initialize the editor
editor = LabelStudioEditor('path/to/your/labelstudio_export.json')
```

### Basic Operations

1. **View Annotations**
```python
editor.view_annotations()
```

2. **Get Label Statistics**
```python
editor.label_stats()
```

3. **Search by Label**
```python
editor.search_by_label('B-PER')
```

4. **Search by Token**
```python
editor.search_by_token("Florida")
```

### Label Manipulation

5. **Remove a Label**
```python
editor.remove_label('B-PER')
```

6. **Merge Labels**
```python
editor.merge_labels(['B-MISC', 'I-MISC', 'B-ORG'], 'C-MISC')
```

7. **Rename Labels**
```python
editor.rename_labels({
    'I-PER': 'A-MISC',
    'B-LOC': 'A-LOC'
})
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

## Author

Sakib Ahmed Shuva

## Acknowledgments

- Label Studio team for their excellent annotation tool
- Contributors to the project
