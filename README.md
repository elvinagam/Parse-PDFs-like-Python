# Parse-PDFs-like-Python

# Camelot - PDF Table Parsing and Post-Processing

![Camelot Logo](https://camelot-py.readthedocs.io/en/master/_static/png/camelot-logo.png)

## Introduction

This is a simple exploration and explanation of what Camelot can do in terms of PDF parsing and the post-processing stage of an OCR pipeline.

One unique feature of Camelot, which sets it apart from other tools, is the ability to tweak the table detection algorithm based on metrics like accuracy and whitespaces.

**Stream Method**: This method is used to work with tables that have whitespaces simulating table structure, rather than actual table lines. In this case, each character is grouped into words, and words are grouped into table lines with the help of margins.

**Lattice Method**: This method is used to parse tables that have demarcated lines of cells clearly showing the table structure. It does not rely on guesses to decide on rows or cells. It uses ghostscript (which is not required in this H2O.ai version) to convert PDFs into images and then processes horizontal and vertical lines of tables, defining table/cell boundaries based on their "and" and "or" relationships to pixel intensities.

## Installation

To use Camelot, follow these installation steps:

1. Clone the Camelot repository to your local machine:

   ```bash
   git clone https://www.github.com/h2oai/camelot

   cd camelot

    pip install "camelot-py[base]"
    
    
    pip install pdf2image
    pip install python-dateutil
    apt-get install poppler-utils
    ```
## Testing on an Example PDF
To test Camelot on an example PDF named "background_lines.pdf" and process the background, you can use the following code:

```python
tables = camelot.read_pdf('/path/to/background_lines.pdf', process_background=True)
# Access the extracted table data
print(tables[1].df)
```
Replace "/path/to/background_lines.pdf" with the actual path to your PDF file.


That's it! You are now ready to leverage the power of Camelot for extracting tabular data from PDF documents and optimizing your OCR pipeline's post-processing stage.

For more information and detailed documentation, please visit the official Camelot website: https://camelot-py.readthedocs.io/

Feel free to contribute to this project by reporting issues or submitting pull requests. Happy tabular data extraction!



