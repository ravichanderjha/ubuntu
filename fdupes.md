# fdupes

`fdupes` is a command-line tool for identifying and managing duplicate files within specified directories on Unix-like systems, including Ubuntu.

## Installation

To install `fdupes`, run the following command in your terminal:

```bash
sudo apt-get install fdupes
```

## Usage

### Basic Command

To search for duplicate files in a directory:

```bash
fdupes /path/to/directory
```

### Recursive Search

To search for duplicate files recursively within subdirectories:

```bash
fdupes -r /path/to/directory
```

### Interactive Deletion

To search for duplicates and interactively delete files:

```bash
fdupes -r -d /path/to/directory
```

Use this option with caution. You will be prompted to choose which files to keep.

### Summarize Duplicates

To show a summary of duplicate files:

```bash
fdupes -r -S /path/to/directory
```

### List Size of Duplicate Files

To list duplicate files along with their sizes:

```bash
fdupes -r -S /path/to/directory
```

### Excluding Empty Files

To exclude zero-length (empty) files from the search:

```bash
fdupes -r --noempty /path/to/directory
```

### Comparing File Content

To compare files by their content:

```bash
fdupes -r -n /path/to/directory
```

This will compare files by their content instead of relying on file sizes or names.

## Options

- `-r` : Recursively search directories.
- `-d` : Prompt the user to select which files to delete.
- `-S` : Show size of duplicate files.
- `-n` : Do not prompt or delete, just compare file content.
- `--noempty` : Exclude zero-length files from consideration.
- `-h` : Display help message and exit.

## Example Commands

1. **Simple search for duplicates:**
    ```bash
    fdupes /home/user/documents
    ```

2. **Recursive search in directory and subdirectories:**
    ```bash
    fdupes -r /home/user/documents
    ```

3. **Interactive deletion of duplicate files:**
    ```bash
    fdupes -r -d /home/user/documents
    ```

4. **Show size of duplicate files:**
    ```bash
    fdupes -r -S /home/user/documents
    ```

5. **Exclude empty files from the search:**
    ```bash
    fdupes -r --noempty /home/user/documents
    ```

## License

`fdupes` is licensed under the MIT License.