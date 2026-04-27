# aws-ec2-tag-policy-enforcement

## 📌 Project Overview
In an enterprise AWS environment, resource tracking is critical for billing, security, and governance.  
This project implements a Cloud Governance strategy using an IAM policy to ensure that no EC2 instance can be launched without mandatory tags.

---

## 🎯 Mandatory Tags Enforced

| Tag Key   | Example Value        |
|-----------|---------------------|
| Name      | Pratiksha           |
| emailID   | user@example.com    |
| phoneNo   | 98XXXXXXXX          |
| Place     | Pune                |

---

## 🛠️ IAM Enforcement Policy (JSON)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyEC2WithoutRequiredTags",
      "Effect": "Deny",
      "Action": "ec2:RunInstances",
      "Resource": [
        "arn:aws:ec2:*:*:instance/*",
        "arn:aws:ec2:*:*:volume/*",
        "arn:aws:ec2:*:*:network-interface/*"
      ],
      "Condition": {
        "Null": {
          "aws:RequestTag/Name": "true",
          "aws:RequestTag/emailID": "true",
          "aws:RequestTag/phoneNo": "true",
          "aws:RequestTag/Place": "true"
        }
      }
    }
  ]
}

## 🚀 Step-by-Step Implementation

---

### 🔹 Step 1: Accessing IAM Policies

<img width="1919" height="865" alt="01_Policy_List" src="https://github.com/user-attachments/assets/e2a54958-a6f1-4cf5-944e-6e0521be5ca8" />

**Explanation:**  
Navigated to the IAM Console and initiated the **Create Policy** process.

---

### 🔹 Step 2: Implementing JSON Logic

<img width="1918" height="858" alt="02_JSON_Editor_Start" src="https://github.com/user-attachments/assets/5d2c4977-d3d7-4b64-b846-b6485caa2abd" />

**Explanation:**  
Entered the custom JSON policy script to enforce mandatory tagging requirements.

---

### 🔹 Step 3: Policy Finalization

<img width="1919" height="868" alt="Policy Finalization" src="https://github.com/user-attachments/assets/7996b314-47c8-431a-8bab-e7253f64558a" />

**Explanation:**  
Reviewed the policy permissions and named it **EC2-Require-Tags-Policy**.

---

### 🔹 Step 4: User & Permission Setup

<img width="1919" height="867" alt="07_User_Details" src="https://github.com/user-attachments/assets/9bfbdadc-9864-41ef-b6bb-773668c4b5b0" />

**Explanation:**  
Created a test user named **EC2-Tag-Test-User** and attached:
- AmazonEC2FullAccess (standard policy)  
- Custom tagging enforcement policy  

---

### 🔹 Step 5: Credential Generation

<img width="1919" height="866" alt="10_Login_Credentials" src="https://github.com/user-attachments/assets/cabfdbf0-2f3c-4a17-96ef-776c607fbb0c" />

**Explanation:**  
Generated the console sign-in URL and temporary credentials for the test user for validation testing.

## 🧪 Phase 2: Testing & Validation (User Side)

The following steps verify the IAM policy enforcement by logging in as the restricted user.

---

### 🔹 Step 6: Login & Security Protocol

<img width="1919" height="1023" alt="updated test_user_pass" src="https://github.com/user-attachments/assets/4a229431-6599-4d88-8134-6278cc354d63" />

**Explanation:**  
Signed in as the test user and updated the password as per AWS security requirements.

---

### 🔹 Step 7: Verification – Launch Failure (Test Case 1)

❌ **EC2 Instance Launch Failed**

**Explanation:**  
Attempted to launch an EC2 instance without adding mandatory tags.  
The request was denied by IAM policy enforcement with an **Authorization Failure** message.

---

### 🔹 Step 8: Applying Mandatory Tags

<img width="1919" height="912" alt="10_Adding_Mandatory_Tags" src="https://github.com/user-attachments/assets/ba3aa76b-24ac-4e88-95d5-f98cebf4c83c" />

**Explanation:**  
Added all required tags during EC2 instance configuration:
- Name  
- emailID  
- phoneNo  
- Place  

---

### 🔹 Step 9: Verification – Launch Success (Test Case 2)

<img width="1919" height="898" alt="11_Launch_Success" src="https://github.com/user-attachments/assets/d0179a0f-8812-4243-b1e9-4360afedd1ca" />

**Explanation:**  
SUCCESS: After applying mandatory tags, the IAM policy condition was satisfied and the EC2 instance was successfully launched.

---

## 🧠 Skills Demonstrated

- AWS IAM Policy Management  
- EC2 Instance Lifecycle Management  
- Cloud Governance & Compliance  
- Tag-Based Access Control (ABAC Concept)  
- AWS Security Best Practices  
- JSON Policy Writing  
- Troubleshooting AWS Permission Errors  

---

## 👤 Author

**Pratiksha Lavand**  
Master of Computer Applications (MCA)  
Savitribai Phule Pune University  
Aspiring Cloud & DevOps Engineer
