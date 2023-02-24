# Define base image
FROM continuumio/miniconda3

# Set working directory for the project
WORKDIR home/mandira/miniconda3/nyccontainer

# Create Conda environment from the YAML file
COPY environment.yml .
RUN conda env create -f environment.yml

# Override default shell and use bash
SHELL ["conda", "run", "-n", "pyspark", "/bin/bash", "-c"]

# Python program to run in the container
COPY nycparking.ipynb .
ENTRYPOINT ["conda", "run", "-n", "pyspark", "python", "nycparking.ipynb"]