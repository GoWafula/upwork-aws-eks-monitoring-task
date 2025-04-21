# 🚀 Monitoring & Alerting on AWS EKS (Spot Instances + CloudWatch)

This project demonstrates a cost-efficient solution for monitoring Kubernetes pods on Amazon EKS using native AWS services. It focuses on detecting pods not in a `Running` state and sending email notifications using CloudWatch and SNS all while running on Spot Instances to optimize cost.

---

## 📌 Objective

Detect non-running Kubernetes pods and send email alerts using:
- CloudWatch Logs Insights
- Metric Filters & Alarms
- Amazon SNS
- Spot Instances
- Cluster Autoscaler

---

## 🧱 Architecture

**Services Used:**
- Amazon EKS (with Spot Instances)
- CloudWatch Logs & Insights
- CloudWatch Metric Filters
- CloudWatch Alarms
- Amazon SNS (for email)
- Cluster Autoscaler (to manage Spot nodes)

**Workflow:**
1. Pod logs are pushed to CloudWatch.
2. Insights queries identify pods not in `Running` state.
3. Custom metrics are created from logs.
4. Alarms watch these metrics.
5. Email alerts are triggered via SNS.

---

## ✅ Benefits

- **💸 Cost-efficient**: Spot Instances lower compute spend.
- **🧰 Zero external tools**: 100% AWS-native.
- **📉 Auto-scale**: Cluster Autoscaler shuts down unused nodes.
- **📍 Pod-level visibility**: Early issue detection.

---

## ⚠️ Known Limitations

- ⏱️ **Latency**: Logs → Metrics → Alerts introduces delay (~minutes).
- 📩 **False positives**: Pending pods may trigger alerts unnecessarily.
- ⚡ **Spot volatility**: 2-minute warning before EC2 eviction.
- 💵 **CloudWatch costs**: Ingestion, storage, and custom metric pricing.
- 🧵 **Not multi-cluster friendly**: Lacks centralized observability.

---
