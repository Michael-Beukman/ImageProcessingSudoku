# ImageProcessingSudoku - Michael Beukman
This is a project for the Digital Image Processing course, and it involved writing a program that used image processing techniques to read in images of sudoku grids and parse them to text files representing the grids.

## Requirements
To run the code, you will need a python environment with the appropriate packages installed. You can do this by running
```
conda env create -f env.yml
conda activate dip
jupyter notebook
```

## Data
The data used for this project was obtained from [Sudoku Dataset](https://github.com/wichtounet/sudoku_dataset) by Baptiste Wicht, licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).

We made a few changes, specifically removing 6 images that were rotated, and we moved 8 images into the subfolder `data/images/train_data_imgs`.

We then cropped these 8 images, and manually labelled the digits to act as a training set of around 230 images of digits.
## Method
The method is described in detail in the `report.pdf` file, and the code can be found in `code/SudokuImageRecognition.ipynb`
The main points are:
- Extract the main grid
- Locate and segment all the gridlines, to crop each individual cell.
- Determine if each cell is empty or not,
- Use Linear Discriminant Analysis (LDA) to classify each digit to the correct class.
- Write the final predicted grid out to a text file.

## Folder structure
The folder structure is as follows:
```
├── README.md
├── code
│   ├── SudokuImageRecognition.ipynb    -> Notebook 
containing all of the code
│   ├── parsed_grids                    -> Contains the resultant grids as .txt files
│   └── results                         -> Contains some resultant images
└── data                                -> The dataset
        └── train_data_imgs             -> Some individual digit images, with filenames indicating which digit it is.
```