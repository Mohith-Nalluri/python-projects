# Web Server Log Analysis - Calgary HTTP Dataset

## Overview
This project involves analyzing the Calgary HTTP web server log dataset using Python. The dataset contains one year's worth of HTTP requests to the University of Calgary's Computer Science server.

The analysis focuses on log cleaning, transformation, and extracting actionable insights from HTTP requests.

---

## Dataset
- **Source**: [Calgary HTTP Dataset](https://ita.ee.lbl.gov/html/contrib/Calgary-HTTP.html)
- **Format**: Apache Common Log Format
- **Fields Extracted**: host, timestamp, request (method, resource, protocol), status code, bytes transferred

---

## Approach

### 1. Data Loading & Cleaning
- Read the log line-by-line
- Used regex to parse log lines into structured fields
- Extracted method, filename, and protocol from HTTP request
- Converted timestamp into Python `datetime`
- Cleaned malformed or missing values
- Extracted file extensions from filenames
- Converted status and byte values into integers

### 2. Analysis Questions Answered
- Total number of log entries
- Unique hosts
- Daily unique filenames requested
- Total and most common 404 errors (file and extensions)
- Bandwidth per day in July 1995
- Hourly distribution of requests
- Most requested files
- Status code distribution

---

## Tools Used
- Python
- Pandas
- Regex
- Datetime module
- Jupyter Notebook

---

## Notes
- Timestamps were parsed from both Apache and custom formats (`"%d/%b/%Y:%H:%M:%S %z"` and `"%a %b %d %H:%M:%S %Y"`).
- Malformed lines and missing values were safely ignored or handled during parsing.
