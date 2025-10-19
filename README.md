# 🚀 CloudVault — Secure Cloud Secrets Management Simulator

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg?logo=python&logoColor=white)  
![Tool](https://img.shields.io/badge/Secrets-Manager-FF5252.svg?logo=key)  
![Features](https://img.shields.io/badge/Features-Rotation%20Audit-4CAF50.svg?logo=shield)  
![Reports](https://img.shields.io/badge/Reports-JSON-2196F3.svg?logo=json)  
![CI/CD](https://img.shields.io/badge/CI/CD-Ready-2088FF.svg?logo=githubactions)  
![Dependencies](https://img.shields.io/badge/Dependencies-None-green.svg?logo=python)

**CloudVault** is a **Python 3** tool designed to simulate a cloud-secrets management system. It tracks secrets, evaluates their age and rotation status, flags stale or overdue secrets, and generates audit reports. It’s built for cloud security engineers, DevSecOps teams, and anyone interested in secrets governance.

------

## 🛠 Tech & Languages

| Layer        | Tech / Format                    | Purpose                                     |
|--------------|----------------------------------|---------------------------------------------|
| Language     | **Python 3.10+**                 | Main codebase                               |
| Core Logic   | JSON handling + hashlib + datetime | Track secrets, hash values, compute ages     |
| Reports      | **JSON**                         | Audit results summary                        |
| Execution    | Script / Colab / Notebook        | Flexible runtime environment                 |
| Logging      | Console output + file write      | Real-time summary + persisted audit          |

---

## 🌐 Architecture

Flow:  
1. Step 1 – Load `secrets_store.json` simulating stored cloud secrets.  
2. Step 2 – For each secret: check if active, compute age since last rotation.  
3. Step 3 – If active and age > rotation threshold, flag as “rotation overdue.”  
4. Step 4 – Aggregate totals (active, inactive, stale) and build a `failures` list.  
5. Step 5 – Write `secrets_audit_report.json` with audit summary for CI/CD or dashboards.

---

## ▶️ Run CloudVault

```bash
python cloudvault.py --input data/secrets_store.json --output data/secrets_audit_report.json
