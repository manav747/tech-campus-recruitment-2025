# Log Extraction Script - `extract_logs.js`

## Overview
This Node.js script extracts logs for a specified date from a log file (`logs_2024.log`), transforms them into a human-readable format, and saves them to an output file.

## Features
- Reads logs from `logs_2024.log`
- Extracts logs for a specific date (passed as an argument)
- Transforms log format from **ISO timestamp** to a readable format
- Saves extracted logs in `../output/output_<YYYY-MM-DD>.txt`
- Handles missing logs by deleting empty output files

---

## **Log Format Transformation**
### **Expected Log Format (Input)**
2024-12-02T02:23:37.0000 - DEBUG - Cache cleared successfully.

markdown
Copy
Edit
### **Transformed Format (Output)**
2024-12-02 02:23:37 DEBUG Cache cleared successfully.

yaml
Copy
Edit

---

## **How to Run the Script**
### **Prerequisites**
- Node.js installed
- Ensure the log file `logs_2024.log` is in the correct path (`../logs_2024.log`)

### **Run the Script**
Use the command:
```bash
node extract_logs.js <YYYY-MM-DD>
Example:

``` bash
node extract_logs.js 2024-12-02
Output File
The extracted logs will be saved in:
```
```bash

../output/output_2024-12-02.txt
Error Handling
If the date is not provided, the script exits with an error.
If logs for the given date are not found, an empty output file is removed.
Any file read/write issues are logged to the console.
How It Works
The script reads logs_2024.log line by line.
It checks if the line starts with the given date.
If the log matches, it transforms the line format.
The transformed log is written to the output file.
If no logs are found for the date, the output file is deleted.
```
## Directory Structure
 lua
project/
│-- extract_logs.js
│-- logs_2024.log
│-- output/  <-- (Logs will be saved here)
## Example Output

``` bash

Extracting logs for 2024-12-02...
Logs for 2024-12-02 extracted successfully to ../output/output_2024-12-02.txt
If no logs are found:

bash
Copy
Edit
No logs found for 2024-12-02.
