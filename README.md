# NLP_Project: This is the root directory of this project.

This project is designed to build an NLP text summarizer. The project includes various stages such as data ingestion, data validation, data transformation, model training, and evaluation. The project is containerized using Docker for easy setup and deployment.

## Project Structure
            NLP_SUMMARIZER_PROJECT/
            ├── .github/ # GitHub-specific files (e.g., workflows)
            ├── config/
            │ ├── config.yaml # Configuration file for the project
            ├── research/
            │ ├── data_injection.ipynb # Jupyter notebook for data ingestion
            │ ├── trials.ipynb # Jupyter notebook for various trials and experiments
            ├── src/
            │ ├── nlptextSummarizer/
            │ │ ├── components/
            │ │ │ ├── init.py # Init file for components package
            │ │ │ ├── data_ingestion.py # Script for data ingestion
            │ │ │ ├── data_transformation.py # Script for data transformation
            │ │ │ ├── data_validation.py # Script for data validation
            │ │ ├── config/
            │ │ │ ├── init.py # Init file for config package
            │ │ │ ├── configuration.py # Configuration script
            │ │ ├── constants/
            │ │ │ ├── init.py # Init file for constants package
            │ │ ├── entity/
            │ │ │ ├── init.py # Init file for entity package
            │ │ ├── logging/
            │ │ │ ├── init.py # Init file for logging package
            │ │ ├── pipeline/
            │ │ │ ├── init.py # Init file for pipeline package
            │ │ │ ├── stage_01_data_ingestion.py # Script for data ingestion pipeline stage
            │ │ │ ├── stage_02_data_validation.py # Script for data validation pipeline stage
            │ │ ├── utils/
            │ │ │ ├── init.py # Init file for utils package
            ├── .gitignore # Git ignore file
            ├── app.py # Flask application script
            ├── Dockerfile # Dockerfile for containerization
            ├── LICENSE # License file
            ├── main.py # Main script to run the project
            ├── params.yaml # Parameters configuration file
            ├── README.md # Readme file for the project
            ├── requirements.txt # Requirements file for pip
            ├── setup.py # Setup script for the project
            ├── template.py # Template script for setting up directories and files

## Getting Started

### Prerequisites

- Python 3.8+
- Docker (if you want to use containerization)

### Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/username/project.git
    cd project
    ```

2. **Install the required Python packages**:
    ```sh
    pip install -r requirements.txt
    ```

3. **Configure the project**:
    Update the `config/config.yaml` and `params.yaml` files with the appropriate configuration settings for your environment.



## Workflow of the project is:
1. Update config.yaml
2. Update params.yaml
3. Update entity
4. Update the configuration manager in src config
5. Update the components
6. Update the pipeline
7. Update the main.py
8. Update the appy.py

## Running the Project

### Using Python

1. **Run the main script**:
    ```sh
    python main.py
    ```

### Using Docker

1. **Build the Docker image**:
    ```sh
    docker build -t nlp_summarizer_project 
    ```

2. **Run the Docker container**:
    ```sh
    docker run -p 4000:80 nlp_summarizer_project
    ```
    Access the application at `http://localhost:4000`

## Project Modules

### Configuration (`config`)

Contains the configuration files for the project. `config.yaml` includes general configurations, while `params.yaml` stores hyperparameters and other settings.

### Research (`research`)

Contains Jupyter notebooks for  experiments or research-related scripts and notebooks.

### Source Code (`src`)

- **Components**:
  - `data_ingestion.py`: Script for data ingestion.
  - `data_transformation.py`: Script for data transformation.
  - `data_validation.py`: Script for data validation.

- **Config**:
  - `configuration.py`: Script for loading and managing configuration settings.

- **Constants**:
  - Contains constant values used across the project.

- **Entity**:
  - Contains data classes for configuration entities.

- **Logging**:
  - Contains logging setup for the project.

- **Pipeline**:
  - `stage_01_data_ingestion.py`: Data ingestion stage of the pipeline.
  - `stage_02_data_validation.py`: Data validation stage of the pipeline.

        nlptextSummarizer/
                ├── pipeline/
                │   ├── __init__.py
                │   ├── data_ingestion.py
                │   ├── data_preprocessing.py
                │   ├── feature_engineering.py
                │   ├── model_training.py
                │   ├── model_evaluation.py
                │   ├── model_deployment.py
                │   ├── pipeline_orchestration.py
                │   ├── config/
                │   │   ├── pipeline_config.yaml
                │   │   └── preprocessing_config.yaml
- **Utils**:
  - Utility scripts(classes and functions) used across the project.

### App Script (`app.py`)

The entry point for the Flask web application.

### Dockerfile

Contains instructions for building the Docker image for the project.

for example:
-**1st step:- FROM python:3.9-slim**
- This line specifies the base image to use for the Docker image. In this case, it's a slim version of Python 3.9.

-**2nd:- WORKDIR /app**
- This sets the working directory inside the container to /app.

-**3rd: COPY . /app**
- This copies the current directory contents (where the Dockerfile is located) into the container at /app.

-**4th:- RUN pip install --no-cache-dir -r requirements.txt**
- This installs the Python packages specified in the requirements.txt file. 
- The --no-cache-dir option prevents pip from caching the packages, which reduces the image size.

-**5th:- EXPOSE 80**
-This makes port 80 available for use by the container. This is the port that the Flask application will listen on.

-**6th: ENV NAME World**
- This sets an environment variable NAME with the value World. Environment variables can be used to configure the application.

-**7th:- CMD ["python", "app.py"]**
- This specifies the command to run when the container starts. In this case, it runs the app.py script using Python.


### Main Script (`main.py`)

Orchestrates the entire pipeline, calling functions from the various pipeline scripts.

## License

This project is licensed under the MIT License - see the file for details.

## Setup

## Setup Script (`setup.py`)

The Setup file conatins metadata, dependencies, and entry points.

**Key Sections**:

- **Metadata**:
  - Includes the project name, version, author details, and description.
- **Packages**:
  - Lists the Python packages to be included in the distribution.
- **Dependencies**:
  - Specifies the external libraries required for the project.
- **Entry Points**:
  - Defines the command-line scripts provided by the package.



This `README.md` file provides a clear and concise overview of the project structure, setup instructions, and explanations of each module and its purpose.

