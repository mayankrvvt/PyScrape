# PyScrape
API Request Monitor

This script periodically checks an API endpoint for the number of pending requests and logs the results with timestamps.
It is useful for monitoring background jobs or queues that process requests until completion.

Features

Fetches data from a given API every 5 seconds.

Extracts and prints the pendingRequestCount field.

Logs timestamps for each request.

Stops monitoring automatically when pendingRequestCount becomes 0.

Handles errors gracefully (e.g., network issues, missing fields).

Requirements

Python 3.7+

Packages:

schedule

requests

python-dotenv

Installation

Clone this repository or copy the script.

Install dependencies:

pip install schedule requests python-dotenv


Create a .env file in the project root:

API_URL=https://your-api-endpoint.com/status

Usage

Run the script with:

python monitor.py

Example Output:
Time : 2025-09-10 23:15:30 
pendingRequestCount : 12

Time : 2025-09-10 23:15:35 
pendingRequestCount : 8

Time : 2025-09-10 23:15:40 
pendingRequestCount : 0
Program end at 2025-09-10 23:15:40

Configuration

The API URL is read from the .env file (API_URL).

The script runs every 5 seconds by default.
You can adjust the interval here:

schedule.every(5).seconds.do(job)

Error Handling

If the API call fails, the script logs the error with a timestamp.

If pendingRequestCount is missing, it shows Field not found.
