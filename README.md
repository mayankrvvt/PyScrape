# PyScrape
🚀 API Request Monitor

A lightweight Python script to monitor API request queues in real-time.
It periodically checks an API endpoint, logs the number of pending requests, and stops automatically when no requests are left.

✨ Features

⏱️ Runs every 5 seconds (configurable).

📡 Fetches request count from your API.

📝 Logs results with timestamps.

✅ Automatically stops when pendingRequestCount = 0.

⚡ Handles API failures and missing fields gracefully.

📂 Project Structure
.
├── monitor.py     # Main script
├── .env           # Environment variables (API_URL)
└── README.md      # Documentation

🔧 Installation
1. Clone or copy this project
git clone https://github.com/yourusername/api-request-monitor.git
cd api-request-monitor

2. Install dependencies
pip install schedule requests python-dotenv

3. Configure your API URL

Create a .env file in the project root:

API_URL=https://your-api-endpoint.com/status

▶️ Usage

Run the script:

python monitor.py

✅ Example Output
Time : 2025-09-10 23:15:30 
pendingRequestCount : 12

Time : 2025-09-10 23:15:35 
pendingRequestCount : 8

Time : 2025-09-10 23:15:40 
pendingRequestCount : 0
Program end at 2025-09-10 23:15:40

⚙️ Configuration

Change the API URL in .env:

API_URL=https://new-api-url.com/status


Modify the interval in monitor.py:

schedule.every(10).seconds.do(job)  # runs every 10 seconds

🛡️ Error Handling

If the API call fails → logs an error with timestamp.

If pendingRequestCount is missing → shows Field not found.

If API is unreachable → shows HTTP status code.
