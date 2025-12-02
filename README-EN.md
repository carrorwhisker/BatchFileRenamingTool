# Batch File Processing Tools

A set of simple and easy-to-use batch file processing tools, containing three independent tools to help you efficiently handle file operations.

## 📦 Tool List

### 1. 📝 Batch File Generator (`index.html`)
Generate multiple file copies with different names based on template files and data.

### 2. 🔄 Batch File Rename Tool (`rename.html`)
Batch rename files with support for replacing and deleting characters at specified positions.

### 3. 📊 Excel Batch Editor (`excel-edit.html`)
Batch edit cell contents in multiple Excel files.

---

## 🚀 Tool 1: Batch File Generator

### Features

- 📁 **Template File Support**: Select any file as a template
- 📊 **Data Management**: Manage data through tables with dynamic add/delete rows and columns
- 🎯 **Variable Templates**: Define filename templates using `{variableName}` format
- 👁️ **Real-time Preview**: Preview all file names before generation
- 🌐 **Multi-language Support**: Switch between Chinese and English interfaces
- 💾 **Batch Download**: Generate and download all files with one click

### Usage

#### 1. Select Template File

Click the "Select Template File" button and choose a file as the template. This file will be copied to generate multiple file copies with different names.

#### 2. Manage Data

In the "Data Management" area:
- Click "+ Add Data Row" to add new data rows
- Click "+ Add Column" to add new data columns
- Click the "×" button in the header to delete columns
- Click the "Delete" button in each row to delete data rows
- You can directly edit data and column names in the table

#### 3. Configure Filename Template

In the "Filename Template Configuration" area:
- Enter a filename template using `{variableName}` format to define variables
- Example: `Example_Document_{Code}_{Date}_{ProjectName}.xls`
- Variable names automatically match column names in data management
- If variable names don't match column names, select the corresponding data column from the dropdown menu

#### 4. Preview and Generate

- View the list of files to be generated in the "File Generation Preview" area
- Click "Refresh Preview" to update the preview
- After confirmation, click the "Generate Files" button
- Files will be automatically downloaded to the browser's default download directory

### Example

Suppose you have an Excel template file `template.xls` and need to generate multiple copies with different names:

1. **Select Template File**: Select `template.xls`

2. **Prepare Data**:
   - Column 1: Project Name
   - Column 2: Code
   - Column 3: Date

3. **Enter Data**:
   ```
   Project Name    Code    Date
   Example Proj A  A001     20250101
   Example Proj B  A002     20250115
   ```

4. **Set Template**: `Example_Document_{Code}_{Date}_{ProjectName}.xls`

5. **Generate Files**:
   - `Example_Document_A001_20250101_Example Proj A.xls`
   - `Example_Document_A002_20250115_Example Proj B.xls`

---

## 🔄 Tool 2: Batch File Rename Tool

### Features

- 📁 **Batch Selection**: Support selecting multiple files for renaming at once
- ✂️ **Replace Characters**: Replace characters of specified length starting from a specified position
- 🗑️ **Delete Characters**: Delete characters of specified length starting from a specified position
- 📋 **Multiple Rules**: Add multiple rules that execute in sequence
- 🎯 **Quick Select**: Interactive filename selector - click or drag to select characters
- 👁️ **Real-time Preview**: Preview all new file names before renaming
- 🌐 **Multi-language Support**: Switch between Chinese and English interfaces
- 💾 **Direct Modification**: Support direct modification of source files (requires browser support for File System Access API)

### Usage

#### 1. Select Files

Click the "Select Files" button and choose files to rename (multiple selection supported).

#### 2. Add Rename Rules

Click the "+ Add Replace Rule" or "+ Add Delete Rule" button:

**Method 1: Manual Input**
- Set start position (starting from 1, excluding extension)
- Set replace/delete length
- For replace rules, enter the replacement text

**Method 2: Quick Select (Recommended)**
- Select the file to use in the dialog
- Click or drag in the filename selector to select characters
- Position and length will be automatically filled

#### 3. Manage Rules

- Each rule can be independently configured and deleted
- Use ↑↓ buttons to adjust rule execution order
- Rules execute in sequence, and multiple rules can be applied simultaneously

#### 4. Preview and Apply

- View rename effects in the "Rename Preview" area
- After confirmation, click the "Apply Rename" button
- If the browser supports it, source files will be directly modified; otherwise, renamed files will be downloaded

### Example

Suppose you have a batch of files to rename:

**Original Filename**: `Report_2024_01_15_Final.docx`

**Requirement**: Remove date separators, replace `2024_01_15` with `20240115`

**Steps**:
1. Select files
2. Add delete rule: Position 4, Length 1 (delete underscore)
3. Add delete rule: Position 7, Length 1 (delete underscore)
4. Add replace rule: Position 4, Length 10, Replace with `20240115`

**Result**: `Report_20240115_Final.docx`

---

## 📊 Tool 3: Excel Batch Editor

### Features

- 📁 **Batch Processing**: Support processing multiple Excel files simultaneously
- 📝 **Cell Editing**: Precisely modify contents of specified cells
- 📊 **Table Configuration**: Configure batch modification rules through tables
- 💾 **Batch Download**: Batch download modified files after processing

### Usage

#### 1. Upload Excel Files

Click the file selection button and choose one or more Excel files (.xlsx or .xls format).

#### 2. Configure Modification Rules

In the "Cell Modification Configuration" area:
- Default columns: File, Cell Coordinate, New Content
- You can add more columns to extend configuration
- Each row represents a cell modification configuration

**Configuration Example**:
```
File          Cell Coordinate  New Content
report1.xlsx  A1               New Title
report1.xlsx  B5               New Data
report2.xlsx  C3               Updated Content
```

#### 3. Start Processing

- Click the "Start Processing" button
- The tool will batch modify all files according to the configuration
- After processing, modified files will be automatically downloaded

### ⚠️ Important Limitations

**Merged Cells Limitation**:
- ⚠️ **This tool does NOT support Excel files with merged cells**
- If an Excel file contains merged cells, errors will occur during processing
- Please ensure Excel files have no merged cells before use
- If you must process files with merged cells, please unmerge them first before using this tool

### Example

Suppose you need to batch update titles in multiple report files:

1. **Upload Files**: Select `report1.xlsx`, `report2.xlsx`, `report3.xlsx`

2. **Configure Rules**:
   ```
   File          Cell Coordinate  New Content
   report1.xlsx  A1               2024 Annual Report
   report2.xlsx  A1               2024 Annual Report
   report3.xlsx  A1               2024 Annual Report
   ```

3. **Process Files**: Click "Start Processing", and all files' A1 cells will be updated to "2024 Annual Report"

---

## 🛠️ Technical Details

### Common Features

- **Pure Frontend Implementation**: All tools are pure frontend implementations, no server required
- **Browser Compatibility**:
  - Chrome/Edge (Recommended)
  - Firefox
  - Safari

### Tool-Specific Technical Details

#### Batch File Generator
- Uses HTML5 File API to read files
- Uses Blob API to create file copies
- Supports all file types (Excel, Word, PDF, images, etc.)

#### Batch File Rename Tool
- Uses HTML5 File API to read files
- Supports File System Access API (Chrome/Edge) for direct source file modification
- Automatically falls back to download mode when not supported

#### Excel Batch Editor
- Uses ExcelJS library to process Excel files
- Supports .xlsx and .xls formats
- ⚠️ **Does NOT support merged cells**

---

## 📝 Notes

### Batch File Generator
- When generating many files, the browser may prompt for permission to allow multiple downloads
- It's recommended to generate no more than 50 files at a time
- File extensions are automatically inherited from the template file

### Batch File Rename Tool
- Position counting starts from 1 and excludes file extensions
- Rules execute in sequence, with later rules based on results from previous rules
- If the browser doesn't support File System Access API, renamed files will be downloaded

### Excel Batch Editor
- ⚠️ **Does NOT support Excel files with merged cells**
- Cell coordinates use Excel standard format (e.g., A1, B5, C3)
- It's recommended to backup original files first

---

## 🌐 Language Switching

All tools support switching between Chinese and English interfaces:
- Click the language switch button (EN/中文) in the top right corner
- The interface will immediately switch to the corresponding language

---

## 📄 File Description

- `index.html` - Batch File Generator
- `rename.html` - Batch File Rename Tool
- `excel-edit.html` - Excel Batch Editor

---

## 💡 Usage Recommendations

1. **Batch File Generator**: Suitable for scenarios requiring batch file generation based on data
2. **Batch File Rename Tool**: Suitable for scenarios requiring batch file name standardization
3. **Excel Batch Editor**: Suitable for scenarios requiring batch Excel file content updates (note merged cells limitation)

---

## ⚠️ Disclaimer

- All tools are pure frontend implementations, with file processing completed locally in the browser
- It's recommended to backup important files before processing
- Excel Editor does not support merged cells, please ensure files meet requirements before use
