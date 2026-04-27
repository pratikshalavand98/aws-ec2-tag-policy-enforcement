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


---

## 🛠️ AWS Services Used
- AWS IAM (Identity & Access Management)
- Amazon EC2
- JSON Policy Engine

---

## 🔐 IAM Policy Logic
- Uses Explicit Deny
- Validates `aws:RequestTag`
- Ensures all mandatory tags are present
- Blocks EC2 launch if tags are missing

---

## 🚀 Step-by-Step Implementation

---

### 🔹 Step 1: IAM Policy Creation

<img width="1919" height="865" alt="01_Policy_List" src="https://github.com/user-attachments/assets/e2a54958-a6f1-4cf5-944e-6e0521be5ca8" />

---

### 🔹 Step 2: JSON Policy Setup

<img width="1918" height="858" alt="02_JSON_Editor_Start" src="https://github.com/user-attachments/assets/5d2c4977-d3d7-4b64-b846-b6485caa2abd" />

---

### 🔹 Step 3: Policy Finalization

<img width="1919" height="868" alt="Policy Finalization" src="https://github.com/user-attachments/assets/7996b314-47c8-431a-8bab-e7253f64558a" />

---

### 🔹 Step 4: IAM User Setup

<img width="1919" height="867" alt="07_User_Details" src="https://github.com/user-attachments/assets/9bfbdadc-9864-41ef-b6bb-773668c4b5b0" />

---

### 🔹 Step 5: Credential Generation

<img width="1919" height="866" alt="10_Login_Credentials" src="https://github.com/user-attachments/assets/cabfdbf0-2f3c-4a17-96ef-776c607fbb0c" />

---

## 🧪 Phase 2: Testing & Validation

---

### 🔹 Step 6: Login & Security Setup

<img width="1919" height="1023" alt="updated test_user_pass" src="https://github.com/user-attachments/assets/4a229431-6599-4d88-8134-6278cc354d63" />

---

### 🔹 Step 7: EC2 Launch Failure (Test Case 1)

❌ EC2 launch failed due to missing mandatory tags.

IAM policy correctly denied the request.

---

### 🔹 Step 8: Applying Mandatory Tags

<img width="1919" height="912" alt="10_Adding_Mandatory_Tags" src="https://github.com/user-attachments/assets/ba3aa76b-24ac-4e88-95d5-f98cebf4c83c" />

---

### 🔹 Step 9: EC2 Launch Success (Test Case 2)

<img width="1919" height="898" alt="11_Launch_Success" src="https://github.com/user-attachments/assets/d0179a0f-8812-4243-b1e9-4360afedd1ca" />

✔ EC2 instance launched successfully after applying mandatory tags.

---

## 🧠 Skills Demonstrated
- AWS IAM Policy Writing  
- EC2 Instance Management  
- Cloud Security & Governance  
- Attribute-Based Access Control (ABAC)  
- JSON Policy Design  
- AWS Best Practices  
- Troubleshooting IAM Errors  

---

## 🎯 Real-World Use Case
This type of tagging enforcement is used in:

- Enterprise AWS environments  
- FinOps (Cost Management) teams  
- DevOps governance pipelines  
- Cloud security compliance systems  

👉 Ensures **no untagged resource enters production**

---

## 🏁 Conclusion
This project demonstrates **AWS Cloud Governance using IAM policies**, ensuring strict enforcement of mandatory EC2 tagging for security, cost control, and resource tracking.

---

## 👤 Author
**Pratiksha Lavand**  
MCA | Savitribai Phule Pune University  
Aspiring Cloud & DevOps Engineer
