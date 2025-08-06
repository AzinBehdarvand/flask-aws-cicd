# 🚀 Flask AWS CI/CD Pipeline with GitHub Actions

This project demonstrates a real-world Continuous Integration and Deployment (CI/CD) pipeline for a Python Flask application using **GitHub Actions** and **AWS EC2**.

---

## 🎯 Project Goal

To automatically test and deploy a Python Flask app to an AWS EC2 instance whenever changes are pushed to the `main` branch simulating a real production scenario similar to how deploy 10+ times a day.

---

## 🧱 Tech Stack

- ✅ **Python 3 / Flask** — Simple web app
- ✅ **GitHub Actions** — For CI/CD automation
- ✅ **AWS EC2 (Ubuntu 22.04)** — As deployment target
- ✅ **Shell scripting + SCP + SSH** — For remote execution

---

## 🔁 CI/CD Pipeline Steps

1. **Code pushed to `main`**
2. GitHub Actions:
   - Checks out code
   - Creates virtualenv
   - Installs dependencies
   - Runs pytest
3. If tests pass:
   - Deploys code to EC2 using `scp`
   - Restarts Flask app using `ssh`

---

## 📁 Project Structure
```text
flask-aws-cicd/
├── app.py
├── requirements.txt
├── tests/
│   └── test_app.py
├── .github/
│   └── workflows/
│       └── deploy.yml
├── README.md
```


---

## ⚙️ How to Reproduce

1. Launch Ubuntu EC2 on AWS
2. Open ports `22` and `5000` in Security Group
3. Set up SSH password access (if needed)
4. Add these GitHub secrets:
   - `EC2_HOST` – Your EC2 public IP
   - `EC2_USER` – e.g. `ubuntu`
   - `EC2_PASSWORD` – Your EC2 password
5. Push to `main` branch

---

## 🌍 Live Test

After pushing to GitHub, you can access:

http://<your-ec2-ip>:5000

If it shows ✅, your pipeline worked!
---
📌 Why This Matters
This simulates real deployment workflows used by DevOps & Platform teams. In fact, companies rely on GitHub Actions or Jenkins to deploy their product dozens of times per day and this is the first step to building such platforms.
