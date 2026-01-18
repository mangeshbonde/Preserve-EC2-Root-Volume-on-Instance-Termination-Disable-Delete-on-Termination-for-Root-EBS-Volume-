# Preserve EC2 Root Volume on Instance Termination  
_Disable Delete-on-Termination for Root EBS Volume_

## 📌 Overview

By default, when an Amazon EC2 instance is terminated, its **root EBS volume** is also deleted automatically.  
In some use cases—such as **data recovery, forensics, backups, or auditing**—you may want the root volume to **persist even after instance termination**.

This guide explains how to **disable the “Delete on termination” option** for the EC2 root volume during instance creation.

---

## 🎯 Objective

- Automatically create a root EBS volume with the EC2 instance
- Prevent the root volume from being deleted when the instance is terminated
- Verify that the volume still exists after termination

---

## 🛠️ Prerequisites

- AWS account
- IAM permissions to:
  - Launch EC2 instances
  - Manage EBS volumes
- Access to the AWS Management Console

---

## 🚀 Steps to Preserve EC2 Root Volume

### Step 1: Launch an EC2 Instance
- Go to **AWS Management Console**
- Navigate to **EC2 → Launch an instance**

---

### Step 2: Configure Storage Settings
- In the **Configure Storage** section:
  - Click **Advanced**
  - Select **Show details**

---

### Step 3: Disable Delete-on-Termination
- Locate the **Root volume (AMI / root)**
- Set **Delete on termination** to **NO**
- Save the changes

✅ This ensures the root EBS volume will not be deleted when the instance is terminated.

---

### Step 4: Create the Instance
- Launch the instance
- Example instance name: `boat-instance`

---

## 🔍 Verification Steps

### Step 5: Verify Volume Creation
- After the instance launches:
  - Go to **EC2 → Volumes**
  - Confirm the root EBS volume is created and attached

---

### Step 6: Terminate the Instance
- Terminate the EC2 instance
- Do **not** delete the volume manually

---

### Step 7: Confirm Volume Persistence
- Navigate again to **EC2 → Volumes**
- Verify that the root EBS volume still exists

✅ Result: The root volume remains available even after instance termination.

---

## ✅ Outcome

- EC2 instance terminated successfully
- Root EBS volume preserved
- Data remains intact and reusable

---

## 📦 Use Cases

- Data recovery
- Backup & restore workflows
- Security audits
- Incident investigations
- AMI creation from preserved volumes

---

## ⚠️ Important Notes

- Preserved volumes **continue to incur EBS charges**
- Always delete unused volumes to avoid unnecessary costs
- You can reattach the preserved volume to another EC2 instance if needed

---

## 📚 Reference

This README is based on the documented procedure for preserving EC2 root volumes by disabling the **Delete-on-Termination** setting during instance launch :contentReference[oaicite:1]{index=1}

---

## ✨ Author

Created for AWS learning, documentation, and GitHub portfolio usage.
