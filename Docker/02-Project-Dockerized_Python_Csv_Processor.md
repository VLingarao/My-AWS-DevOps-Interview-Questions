# Project 2: Dockerizing a Python CSV Processing Script

## Project Name

**docker-python-csv-processor**

---

## Project Objective

The objective of this project is to containerize a simple Python script using **Docker**. The script reads data from a CSV file using the **pandas** library and prints statistical information.

This project helps beginners understand how Docker is used to:

* Run Python scripts in isolated environments
* Manage Python dependencies using Docker
* Make data-processing scripts portable and reproducible

---

## Technologies Used

* Docker
* Python 3.9
* pandas
* CSV files
* WSL2 (Linux on Windows)

---

## Project Structure

```
02-python-docker-project/
│── Dockerfile
│── requirements.txt
│── process_data.py
│── data.csv
│── README.md
```

---

## Step 1: Create Project Directory

```bash
mkdir 02-python-docker-project
cd 02-python-docker-project
```

---

## Step 2: Create CSV File

This file contains sample data for processing.

**data.csv**

```csv
age,salary
25,30000
30,45000
35,60000
40,80000
```

---

## Step 3: Create Python Script

This script reads the CSV file and prints summary statistics.

**process_data.py**

```python
import pandas as pd

# Read CSV file
df = pd.read_csv("data.csv")

print("CSV Data Summary:")
print(df.describe())
```

---

## Step 4: Create requirements.txt

This file defines the Python dependencies required by the script.

**requirements.txt**

```text
pandas
```

---

## Step 5: Create Dockerfile

The Dockerfile defines how the Docker image is built.

**Dockerfile**

```dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY process_data.py .
COPY data.csv .

CMD ["python", "process_data.py"]
```

### Dockerfile Explanation

* `FROM python:3.9-slim` → Lightweight Python base image
* `WORKDIR /app` → Sets working directory inside container
* `RUN pip install` → Installs pandas dependency
* `COPY` → Copies script and CSV file into container
* `CMD` → Runs Python script when container starts

---

## Step 6: Build Docker Image

```bash
docker build -t 02-python-docker-project .
```

Verify image:

```bash
docker images
```

---

## Step 7: Run Docker Container

```bash
docker run 02-python-docker-project
```

### Expected Output

```text
CSV Data Summary:
              age        salary
count    4.000000      4.000000
mean    32.500000  53750.000000
std      6.454972  21602.468994
min     25.000000  30000.000000
max     40.000000  80000.000000
```

---

## Important Docker Concept Learned

### Docker Images Are Immutable

* After building an image, code changes on the host do NOT affect the container
* To apply changes, either rebuild the image or use volume mounting

---

## Optional: Run Using Volume Mount (Advanced)

This allows code changes without rebuilding the image.

```bash
docker run -v $(pwd):/app 02-python-docker-project
```

---

## Common Errors & Fixes

### Error: AttributeError (method not found)

Cause: Typo in Python method name

Fix:

```python
df.describe()
```

### Error: FileNotFoundError

Cause: Incorrect CSV file path

Fix: Ensure CSV file exists in container working directory

---

## Project Outcome

* Python script successfully executed inside Docker
* pandas installed via Dockerfile
* CSV data processed correctly

---

## Learning Outcome

By completing this project, you learned:

* How to Dockerize Python scripts
* How to manage Python dependencies in Docker
* Difference between images and containers
* When to rebuild images vs use volumes

---

**Author:** DevVenkat
