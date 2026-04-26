# Linux-system-monitoring
# 🚀 Linux System Monitoring Tool (Shell Scripting)

A real-time system monitoring tool built using **Shell Scripting** to track CPU, Memory, and Disk usage with automation, logging, and alerting — similar to real-world production monitoring systems.

---

## 📌 Overview

This project demonstrates how to build a lightweight monitoring solution using native Linux tools without any external dependencies.

It continuously monitors system resources, logs activity, automates execution, and manages logs efficiently.

---

## 🔧 Features

✔️ Monitors CPU, Memory, and Disk usage  
✔️ Generates structured system health reports  
✔️ Uses real Linux commands (`mpstat`, `free`, `df`, `awk`)  
✔️ Logs system activity with timestamps  
✔️ Real-time log monitoring using `tail -f`  
✔️ Automated execution using cron (every 5 minutes)  
✔️ Log management using logrotate (prevents disk overflow)  
✔️ Threshold-based alerting system 🚨  

---

## 🛠️ Technologies Used

- Shell Scripting  
- Linux Commands: `mpstat`, `free`, `df`, `awk`  
- Cron Jobs  
- Logrotate  

---

## 📊 How It Works

1. Collects system metrics (CPU, Memory, Disk)  
2. Calculates usage percentages  
3. Compares values with defined thresholds  
4. Generates formatted system health report  
5. Logs output with timestamps  
6. Runs automatically using cron  
7. Rotates logs to prevent overflow  
8. Triggers alerts when thresholds are exceeded  

---

## 🚀 Setup & Usage

1. Make Script Executable
chmod +x monitoring.sh

2. Run Script
./monitoring.sh

3.⏰ Cron Automation
Add cron job:
crontab -e
Add this line:
  */5 * * * * /root/shell_script_jan2026/monitoring.sh >> /root/shell_script_jan2026/cron.log 2>&1

👉 Runs script every 5 minutes automatically

4.📁 Logging

Logs are stored in:

~/sys_monitor.log
View logs:
cat ~/sys_monitor.log
Real-time monitoring:
tail -f ~/sys_monitor.log

5🔄 Log Rotation (Logrotate)

Configured using:

/etc/logrotate.d/sys_monitor
Sample Configuration:
/root/sys_monitor.log {
    daily
    rotate 7
    compress
    missingok
    notifempty
    create 0644 root root
}

👉 Prevents log file from growing indefinitely

6.🚨 Alerting System

Alerting is implemented using threshold-based conditions.
When CPU, Memory, or Disk usage exceeds limits:
Status changes to HIGH
Alert message is generated

💡 Alerting was tested by temporarily reducing thresholds to simulate high usage.

📸 Screenshots
🧾 Monitoring Script
▶️ Execution & Output
📊 Logging & Real-Time Monitoring
⏰ Cron Automation
🔄 Log Management (Logrotate)
🚨 Alerting System

