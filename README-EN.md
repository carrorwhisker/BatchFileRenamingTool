# Batch File Generator

A simple and easy-to-use batch file generation tool that can generate multiple file copies with different names based on template files and data.

## Features

- 📁 **Template File Support**: Select any file as a template
- 📊 **Data Management**: Manage data through tables, support dynamic addition/deletion of rows and columns
- 🎯 **Variable Templates**: Define filename templates using `{variableName}` format
- 👁️ **Real-time Preview**: Preview all file names before generation
- 🌐 **Multi-language Support**: Support Chinese and English interface switching
- 💾 **Batch Download**: Generate and download all files with one click

## How to Use

### 1. Select Template File

Click the "Select Template File" button and choose a file as the template. This file will be copied and renamed with different names.

### 2. Manage Data

In the "Data Management" area:
- Click "+ Add Data Row" to add a new data row
- Click "+ Add Column" to add a new data column
- Click the "×" button in the table header to delete a column
- Click the "Delete" button in each row to delete a data row
- You can directly edit data and column names in the table

### 3. Configure Filename Template

In the "Filename Template Configuration" area:
- Enter the filename template using `{variableName}` format to define variables
- Example: `Example_Document_{Code}_{Date}_{ProjectName}.xls`
- Variable names will automatically match column names in data management
- If variable names don't match column names, you need to select the corresponding data column from the dropdown menu

### 4. Preview and Generate

- View the list of files to be generated in the "File Generation Preview" area
- Click "Refresh Preview" to update the preview
- After confirming, click the "Generate Files" button
- Files will be automatically downloaded to the browser's default download directory

## Usage Example

Suppose you have an Excel template file `template.xls` and need to generate multiple copies with different names:

1. **Select Template File**: Choose `template.xls`

2. **Prepare Data**:
   - Column 1: Project Name
   - Column 2: Code
   - Column 3: Date

3. **Fill in Data**:
   ```
   Project Name    Code    Date
   Example A       A001    20250101
   Example B       A002    20250115
   ```

4. **Set Template**: `Example_Document_{Code}_{Date}_{ProjectName}.xls`

5. **Generate Files**:
   - `Example_Document_A001_20250101_Example A.xls`
   - `Example_Document_A002_20250115_Example B.xls`

## Technical Details

- Pure frontend implementation, no server required
- Uses HTML5 File API to read files
- Uses Blob API to create file copies
- Supports all file types (Excel, Word, PDF, images, etc.)

## Browser Compatibility

- Chrome/Edge (Recommended)
- Firefox
- Safari

## Notes

- When generating a large number of files, the browser may prompt whether to allow multiple downloads
- It is recommended to generate no more than 50 files at a time
- File extensions will be automatically inherited from the template file. If there is no extension in the template, the template file's extension will be used

## Language Switching

Click the language switch button (EN/中文) in the top right corner to switch between Chinese and English interfaces.

