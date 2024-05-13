# Serif-Health-TakeHome-Sai

Project Title: JSON to CSV Transformation and Data Filtering with Dask

Description
This project involves a Python script that initially utilizes jq to convert JSON data into a CSV format focusing on specific fields (description and location). Post this conversion, the script uses Dask, a powerful Python library for parallel data processing, to further transform, clean, and filter this data based on specific criteria (e.g., entries related to "New York" and "PPO"). The goal is to produce a filtered CSV file that highlights certain records from the initial dataset.

Installation
Before running the script
1. Ensure that you have your input Gzipped file
2. Ensure that you have Python installed on your system along with the following dependencies:

Prerequisites
Python 3.6 or later
jq (Command-line JSON processor)
Dask
Pandas

Setup
Clone this repository or download the script to your local machine.
Install the required Python libraries using pip:

In bash Run 
pip install dask 
pip install pandas

Ensure jq is installed on your system. On most Unix-like systems, you can install it via your package manager. For example, on Ubuntu:

In bash Run
sudo apt-get install jq

Usage
To run the script, simply execute it from your command line:

In bash Run
python script_name.py

Make sure to replace script_name.py with the actual name of the Python script.

Outputs
The script will output a CSV file named Anthem_NY_PPO.csv. This file contains the filtered records that are associated with NY PPO.

Development and Performance
Development Time: The script took approximately 1.5 hour to write and test thoroughly.

Execution Time: The typical run time of the script is around 10 minutes, depending on the size of the input JSON file and the processing capabilities of the machine.

Trade-offs and Decisions
1. Choice of Dask over Spark: Dask was chosen due to its simplicity and lower overhead compared to Spark, making it ideal for medium-sized datasets and simpler deployment.
2. Use of jq for Initial Processing: Utilizing jq for the initial conversion from JSON to CSV offloads some data processing outside of Python, allowing for more efficient handling of large JSON files before loading them into Python.

Future Improvements
Error Handling: Enhance the script's robustness by adding more comprehensive error handling and logging.
Scalability: Modify the script to Spark and scale the clusters efficiently to handle even larger datasets.
User Interface: Implement a command-line interface (CLI) to provide users with more options for specifying input files and configuring output preferences.


This README file provides a comprehensive overview that guides users on how to setup, use, and understand the project, including detailing the choices made during development and potential areas for future improvements.


Note::: Since it is mentioned in the take home assessment that the program should run in any machine, I've therefore used JQ and DASK, my intial thought to process this huge file was to use Databricks/Spark for distributed data processing


There are several otherways by which we can do this:
1. Using Spark
2. Using ijson
3. breaking the json file into smaller chunks and store in S3 and then process it