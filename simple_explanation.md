# Alloy Composition Parsing and Data Transformation

This Python script is designed to parse alloy compositions from an input dataset, extract the elements and their respective ratios, and transform the data into a structured format. The code utilizes the Pandas and NumPy libraries to handle data manipulation and extraction.

## Functions

The script consists of two primary functions:

### `parse(comp, element_set)`

This function takes an alloy composition string `comp` and a set of unique elements `element_set`. It parses the composition, extracts the elements, and calculates their ratios. The elements and ratios are then returned as lists.

### `decode(alloy_name, element_set)`

This function is responsible for decoding alloy names, which may include parentheses and nested compositions. It calls the `parse` function for parsing, and when parentheses are encountered, it calculates the ratios within the parentheses and distributes them across the elements accordingly. The final elements and ratios are returned as lists.

## Main Execution

The script's main execution is triggered when `if __name__ == '__main__':` is true. It performs the following tasks:

1. Reads an Excel dataset named 'HEA_mechanical_dataset.xlsx' using Pandas.

2. Initializes an empty set `element_set` to keep track of unique elements in the dataset.

3. Extracts the alloy compositions and phase information from the dataset.

4. Iterates over each alloy composition and uses the `decode` function to obtain the elements and ratios. It also normalizes the ratios to ensure they sum up to 1.

5. Creates a sorted list of unique elements from `element_set`.

6. Constructs a NumPy array `ele_ratio_array` to store the molar ratios for each alloy.

7. Converts the phase information into a binary representation and stores it in a separate NumPy array `phase_array`.

8. Combines the original dataset, the phase information, and the parsed ratios into a new Pandas DataFrame `output_df`.

9. Writes the resulting DataFrame to an Excel file named 'parsed_result.xlsx'.

## Output

The output of this script is a structured dataset where each alloy composition has been parsed into its constituent elements and their respective molar ratios. Additionally, the phase information has been represented in a binary format (FCC, BCC, HCP, IM). The output is stored in an Excel file, making it convenient for further analysis and data manipulation.

This code is particularly useful for researchers or engineers working with alloy compositions and requires a standardized and structured dataset for analysis and modeling.