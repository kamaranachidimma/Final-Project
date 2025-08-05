# Income and Spending Survey Tool

## Navigation

- [Overview](#income-and-spending-survey-tool)
- [Key Features](#key-features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Local Setup and Execution Guide](#local-setup-and-execution-guide)
- [Data Processing and Analysis](#data-processing-and-analysis)

## Live Demo

The application is deployed and accessible at:
[http://ec2-18-234-157-64.compute-1.amazonaws.com/](http://ec2-18-234-157-64.compute-1.amazonaws.com/)

## Overview

This project is a comprehensive web application designed to collect, store, process, and visualize user data on income and spending habits. It was developed as a survey tool for a data analysis company in Washington, DC, to prepare for a new product launch in the healthcare industry.

The application features a user-friendly web form built with Flask and styled with Bootstrap, a MongoDB database for robust data storage, and a data analysis pipeline using Python's Pandas library and Jupyter Notebook for visualizations.

## Key Features

- **Modern Web Interface**: A clean, responsive, and user-friendly survey form built with **Flask** and styled professionally using **Bootstrap 5**.
- **Robust Data Storage**: Utilizes **MongoDB** to store user submissions, providing a flexible, NoSQL database solution.
- **Data Processing Pipeline**: A dedicated Python script (`data_processor.py`) fetches data from MongoDB and exports it into a clean CSV format, ready for analysis.
- **In-Depth Data Analysis**: A **Jupyter Notebook** (`data_analysis.ipynb`) uses Pandas for data manipulation and Matplotlib/Seaborn to generate insightful visualizations, such as:
  - Ages with the highest income.
  - Gender distribution across spending categories.
- **Cloud-Ready Deployment**: Fully configured for deployment on **Amazon Web Services (AWS)** using Elastic Beanstalk, with instructions for both the EB CLI and the AWS Management Console.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Python (3.8 or newer)
- `pip` (Python's package installer)
- Git for version control
- MongoDB Community Edition (and ensure the server is running)
- An AWS Account (for cloud deployment)

## Local Setup and Execution Guide

Follow these steps to run the application on your local machine.

### 1. Clone the Repository

Open your terminal and clone the project repository.

```bash
git clone <your-repository-link>
cd final-project
```

### 2. Create and Activate a Virtual Environment

This isolates the project's dependencies.

```bash
# Create the virtual environment
python -m venv venv

# Activate it
# On macOS/Linux:
source venv/bin/activate
# On Windows (Command Prompt):
# .\venv\Scripts\activate
# On Windows (PowerShell):
# .\venv\Scripts\Activate.ps1
```

Your terminal prompt should now be prefixed with `(venv)`.

### 3. Install Dependencies

Install all the required Python packages from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

### 4. Run the Flask Web Application

Ensure your local MongoDB server is running. Then, set the `FLASK_APP` environment variable and run the application.

**On PowerShell (Windows):**

```powershell
$env:FLASK_APP = "app.main"
flask run
```

**On Command Prompt (Windows):**

```cmd
set FLASK_APP=app.main
flask run
```

**On macOS/Linux:**

```bash
export FLASK_APP=app.main
flask run
```

Open your web browser and navigate to `http://127.0.0.1:5000`. Fill out and submit the form a few times to populate the database with sample data.

## Data Processing and Analysis

After collecting some data, you can process it and generate visualizations.

### 1. Generate the CSV File

Run the `data_processor.py` script. This will connect to your local MongoDB, fetch all the survey responses, and save them into a `user_data.csv` file inside the `analysis` folder.

```bash
python data_processing/data_processor.py
```

You should see a success message in your terminal.

### 2. Perform Data Analysis

Launch Jupyter Lab to run the analysis notebook.

```bash
jupyter lab
```

This will open a new tab in your browser.

- In the Jupyter interface, navigate into the `analysis` directory.
- Open the `data_analysis.ipynb` notebook.
- Run each cell in the notebook from top to bottom.
- The visualizations will be displayed directly in the notebook and also saved as `.png` files in the `analysis/charts/` directory, ready for use in presentations.

### 3. View the Generated Charts

The charts generated from the analysis will be saved in the `analysis/charts/` directory. You can view them directly in your file explorer or include them in reports.

### 4. Clean Up

After you're done, you can deactivate the virtual environment:

```bash
deactivate
```

