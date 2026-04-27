# 🚀 AWS EC2 Tag Policy Enforcement

![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![IAM](https://img.shields.io/badge/IAM-Security-blue)
![EC2](https://img.shields.io/badge/EC2-Compute-green)
![Service](https://img.shields.io/badge/AWS-IAM%20%26%20EC2-yellow)
![Type](https://img.shields.io/badge/Project-Cloud%20Security-purple)
![Level](https://img.shields.io/badge/Level-Intermediate-lightgrey)
![Status](https://img.shields.io/badge/Project-Completed-success)


## 📌 Project Overview

In enterprise cloud environments, maintaining proper tagging of resources is critical for:

- 💰 Cost tracking
- 🔐 Security governance
- 📊 Resource management
- 📑 Billing allocation

This project enforces an **IAM-based tagging policy** that prevents EC2 instance creation unless mandatory tags are provided.

---

## 🎯 Mandatory Tags

| Tag Key   | Example Value     |
|-----------|------------------|
| Name      | Pratiksha        |
| emailID   | user@example.com |
| phoneNo   | 98XXXXXXXX       |
| Place     | Pune             |

---
IAM User → IAM Policy Enforcement → EC2 Service
│
└── If tags missing → ❌ DENY instance launch
└── If tags present → ✅ ALLOW instance launch
---

👉 Flow:
- User requests EC2 launch  
- IAM checks mandatory tags  
- Policy evaluates request  
- Decision: Allow / Deny  

---

## 🛠️ AWS Services Used

- AWS IAM (Identity & Access Management)
- Amazon EC2
- AWS Policy Simulator (Conceptually)
- JSON Policy Engine

---

## 🔐 IAM Policy Logic

- Uses **Explicit Deny**
- Condition based on `aws:RequestTag`
- Enforces all mandatory tags at launch time

---

## 🚀 Implementation Steps

### Step 1: IAM Policy Creation
Create custom IAM policy with tag enforcement logic.

### Step 2: Attach Policy to User
Attach policy to `EC2-Tag-Test-User`.

### Step 3: Login as Test User
Validate restricted permissions.

---

## 🧪 Phase 2: Testing & Validation

### 🔹 Step 6: Login & Security
User logs in and updates password.

---

### 🔹 Step 7: Launch Failure (Negative Test)

❌ EC2 launch blocked due to missing tags.

---

### 🔹 Step 8: Apply Mandatory Tags
User adds required tags during instance configuration.

---

### 🔹 Step 9: Launch Success (Positive Test)

✅ EC2 instance launched successfully after compliance.

---

## 🧠 Skills Demonstrated

- AWS IAM Policy Writing
- EC2 Instance Management
- Cloud Security & Governance
- Attribute-Based Access Control (ABAC)
- JSON Policy Design
- AWS Best Practices
- Error Handling & Debugging

---

## 🎯 Real-World Use Case

This type of enforcement is used in companies like:

- FinTech organizations (cost control)
- Cloud governance teams
- DevOps automation pipelines
- Enterprise AWS landing zones

👉 Ensures **no untagged resources enter production**

---

## 🏁 Conclusion

This project successfully demonstrates **policy-based cloud governance using AWS IAM**, ensuring strict compliance for EC2 resource tagging and improving cost visibility and security.

---

## 👤 Author
**Pratiksha Lavand**  
Master of Computer Applications (MCA)  
Savitribai Phule Pune University  
Aspiring Cloud & DevOps Engineer  

---

## 🏗️ Architecture Diagram
