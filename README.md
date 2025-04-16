# 🔔 Serverless Slack Alerts with AWS CloudWatch & Lambda

This project demonstrates a real-time alerting system that integrates **AWS CloudWatch Alarms** with **Slack** using a serverless **AWS Lambda** function. When a CloudWatch alarm is triggered (e.g., high CPU usage), the Lambda function automatically sends a message to a Slack channel using a webhook.

---

## 🛠️ Tech Stack

- AWS Lambda (Python)
- Amazon CloudWatch
- Slack Webhook Integration
- IAM Roles
- Python `requests` library

---

## 🚀 Project Highlights

✅ Sends real-time alerts to Slack when a CloudWatch alarm triggers  
✅ Fully serverless and event-driven — no polling or manual checks  
✅ Helps DevOps teams respond to incidents faster  

---

## 📁 Folder Structure

serverless-slack-alerts/ ├── lambda_function/ # Lambda handler and logic │ └── lambda_function.py ├── screenshots/ # Sample Slack messages and AWS console output ├── requirements.txt # Python dependencies (requests) ├── .gitignore └── README.md


---

## ⚙️ How It Works

1. A CloudWatch Alarm is triggered (e.g., EC2 CPU > 70%)
2. It triggers a Lambda function
3. The Lambda function parses the event and sends a formatted alert to Slack using a webhook

---

## 📦 Deployment Steps

### 1. Prepare the Lambda Package

```bash
mkdir lambda_function
cd lambda_function

# Copy your lambda_function.py file into this folder

# Install required dependency
pip3 install requests -t .

# Zip the contents
zip -r ../lambda_slack_notification.zip .
```

### 2. Deploy on AWS Console

- Go to **AWS Console → Lambda → Create Function**
- Choose runtime as **Python 3.x**
- Upload the `lambda_slack_notification.zip` file
- Under the **"Configuration" tab → Environment Variables**, add:
Key: SLACK_WEBHOOK_URL
Value: https://hooks.slack.com/services/your/webhook/url



