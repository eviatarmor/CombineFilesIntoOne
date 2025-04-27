# File Combiner

A Python command-line tool that recursively scans directories and combines multiple files into a single output file. Perfect for code documentation, analysis, or creating comprehensive project snapshots.

## Features

- 🚀 Fast recursive directory scanning
- 🎯 Selective file inclusion/exclusion based on extensions
- 📁 Folder exclusion support
- 🕒 Execution time tracking
- 💪 Handles multiple file encodings (UTF-8, Latin-1)
- 📝 Preserves file structure with clear headers
- 🛡️ Error handling for problematic files

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/file-combiner.git
cd file-combiner
```

2. Ensure you have Python 3.6+ installed:
```bash
python --version
```

## Usage

### Basic Usage

Combine all files in a directory:
```bash
python file_combiner.py /path/to/directory output.txt
```

### Advanced Options

```bash
python file_combiner.py [directory] [output] [options]
```

#### Arguments:
- `directory`: Directory to scan for files
- `output`: Output file path

#### Options:
- `--exclude-folders`: Folders to exclude from scanning
- `--include-extensions`: Only include files with these extensions
- `--exclude-extensions`: Exclude files with these extensions

### Examples

1. Combine only Python and JavaScript files:
```bash
python file_combiner.py ./project combined.txt --include-extensions .py .js
```

2. Exclude specific folders:
```bash
python file_combiner.py ./project combined.txt --exclude-folders node_modules .git __pycache__
```

3. Exclude certain file types:
```bash
python file_combiner.py ./project combined.txt --exclude-extensions .pyc .log .tmp
```

4. Combine with multiple filters:
```bash
python file_combiner.py ./project combined.txt \
    --exclude-folders node_modules build dist \
    --include-extensions .py .js .html .css \
    --exclude-extensions .min.js .min.css
```

## Output Format

The combined file uses the following format:

```
# path/to/file1.py
[content of file1.py]


# path/to/file2.js
[content of file2.js]


```

Each file is:
- Preceded by a header showing its relative path
- Followed by its full content
- Separated by blank lines for readability

## Performance

The tool displays execution time and file count upon completion:
```
Completed in 5.2s! Combined 462 files into output.txt
```

## Error Handling

- Automatically skips binary files that can't be read as text
- Attempts multiple encodings (UTF-8, Latin-1) before failing
- Continues processing even if individual files fail
- Reports errors without stopping execution

## Use Cases

- 📚 Creating documentation from source code
- 🔍 Code review preparation
- 📊 Project analysis and metrics
- 🗃️ Archiving code for reference
- 🤖 Preparing code for AI analysis
- 📝 Creating comprehensive project snapshots

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Your Name - [@yourusername](https://github.com/yourusername)

## Acknowledgments

- Thanks to all contributors who have helped improve this tool
- Inspired by the need for better code documentation tools

---

**Note**: This tool is designed for text files. Binary files will be skipped or may produce errors in the output.
