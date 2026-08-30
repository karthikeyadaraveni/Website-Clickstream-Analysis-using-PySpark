# Website Clickstream Analysis Using PySpark

## Project Overview

Website Clickstream Analysis is a data analysis project developed using **Apache PySpark** to analyze user activity on different pages of a website.

The project processes website clickstream data and identifies the number of visits to each webpage and the average time users spend on each page. The results are also visualized using Python's Matplotlib library.

## Objectives

* Analyze website user activity.
* Calculate the number of visits to each webpage.
* Calculate the average duration spent on each webpage.
* Convert PySpark results into a Pandas DataFrame.
* Visualize webpage visits using a bar chart.
* Generate a CSV report containing the analysis results.

## Technologies Used

* Python
* Apache PySpark
* Pandas
* Matplotlib
* Google Colab / Jupyter Notebook

## Dataset

The dataset contains website clickstream information such as:

* User information
* Website page visited
* Duration spent on the webpage
* User activity

The dataset is processed using PySpark DataFrames.

## Methodology

The project follows these steps:

1. Create a Spark Session.
2. Load the website clickstream data.
3. Convert the data into a PySpark DataFrame.
4. Display the first five records.
5. Group the data by webpage.
6. Calculate the number of visits for each webpage.
7. Calculate the average duration spent on each webpage.
8. Convert the PySpark results into a Pandas DataFrame.
9. Create a bar chart to visualize webpage visits.
10. Export the analysis results as a CSV file.

## Analysis Performed

### 1. Page Visit Analysis

The number of visits for each webpage is calculated using PySpark's `groupBy()` and `count()` functions.

```python
pg = spark_df.groupBy("page").count()
```

### 2. Average Time Spent

The average duration spent on each webpage is calculated using the `avg()` function.

```python
avg_t = spark_df.groupBy("page").avg("duration")
```

### 3. Data Visualization

The webpage visit counts are converted into a Pandas DataFrame and visualized using a bar chart.

```python
plt.bar(pg_visits["page"], pg_visits["count"])
```

### 4. Report Generation

The webpage visit analysis is saved as a CSV file.

```python
pg_visits.to_csv("website_click_analysis_report.csv", index=False)
```

## Project Structure

```text
Website-Clickstream-Analysis/
│
├── README.md
├── website_click_analysis.py
├── requirements.txt
└── website_click_analysis_report.csv
```

## How to Run the Project

### Step 1: Install the required libraries

```bash
pip install -r requirements.txt
```

### Step 2: Make sure the dataset is available

The Python program expects the clickstream data to be available in the variable `data`.

### Step 3: Run the Python program

```bash
python website_click_analysis.py
```

### Step 4: View the results

The program displays:

* First five records
* Number of visits for each webpage
* Average duration for each webpage
* Bar chart showing webpage visits

It also generates:

```text
website_click_analysis_report.csv
```

## Output

The project produces a CSV report containing the number of visits for each webpage.

Example:

| Page     | Number of Visits |
| -------- | ---------------- |
| Home     | 120              |
| Products | 95               |
| About    | 60               |
| Contact  | 45               |

The actual values depend on the dataset used.

## Key Benefits

* Uses PySpark for efficient data processing.
* Provides useful insights into website user activity.
* Identifies popular webpages.
* Helps understand user engagement through time spent on pages.
* Generates a reusable CSV report.

## Future Enhancements

* Add most active user analysis.
* Analyze user navigation patterns.
* Identify the most frequently visited pages.
* Add interactive dashboards.
* Analyze traffic by date and time.
* Add user session analysis.
* Use larger clickstream datasets for distributed processing.

## Conclusion

The Website Clickstream Analysis project demonstrates how **PySpark can be used to process and analyze website activity data**. The project identifies webpage visit counts and average time spent on webpages and presents the results through data visualization and a CSV report.

