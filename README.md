🔧 How It Works
Working Hours (8 AM to 8 PM):
The script checks if any of the websites in the block list are missing from the hosts file. If not already present, it appends entries like 127.0.0.1, effectively redirecting them to localhost and preventing access.

Non-Working Hours (Before 8 AM and After 8 PM):
The script scans the hosts file and removes any lines related to the blocked websites, restoring access.

The script runs in a loop, checking every 5 seconds.

📝 Features
Time-based automatic website blocking/unblocking

Customizable list of websites to block

Real-time monitoring with 5-second intervals

Uses the system-level hosts file (requires admin privileges on Windows)

⚙️ Requirements
Python 3.x

Windows OS

Must run the script as Administrator to allow editing the system hosts file

📌 Note
For safety or testing, modify the host_path in the script to point to a temporary file instead of the actual hosts file. You can rename the script to .pyw to make it run silently without opening a terminal window.

🚀 Steps to Run This Script Automatically on Startup
Open Task Scheduler (Press Win + S and search for Task Scheduler)

Click Create Task... (not Basic Task)

Under the General tab:

Name the task: Website Blocker

Check Run with highest privileges

Set "Configure for" to Windows 10/11

Go to the Triggers tab:

Click New...

Set "Begin the task" to At startup

(Optional) Check Delay task for 30 seconds

Click OK

Go to the Actions tab:

Click New...

Action: Start a program

In Program/script, browse to and select your Python interpreter (pythonw.exe)
Example: C:\Users\<YourUsername>\AppData\Local\Programs\Python\Python311\pythonw.exe

In Add arguments, enter the full path to your script in quotes
Example: "C:\Path\To\Website_Blocker.pyw"

Go to the Conditions tab:

(Optional) Uncheck Start the task only if the computer is on AC power

Go to the Settings tab:

Check Allow task to be run on demand

Check If the task fails, restart every 1 minute, attempt up to 3 times

Click OK to save the task

Restart your PC and the script will automatically run at startup, blocking the specified websites during working hours.

