# Dynatrace Core Components: OneAgent, ActiveGate, and Davis AI  

Dynatrace provides full-stack observability using three main components: **OneAgent**, **ActiveGate**, and **Davis AI**.  
These work together to collect, process, and analyze monitoring data.  

---

## 🔹 OneAgent  

### What is OneAgent?  
- **OneAgent** is Dynatrace’s lightweight monitoring agent.  
- It is installed on hosts (VMs, physical servers, containers, or Kubernetes nodes).  
- Automatically **discovers applications, services, processes, and dependencies** without manual configuration.  

### Key Features  
- **Full-stack monitoring**: Host, processes, services, network, and user experience.  
- **Auto-discovery**: Detects applications and their dependencies automatically.  
- **APM support**: Captures traces, request timings, and code-level insights.  
- **Container & K8s monitoring**: Provides pod-level visibility.  
- **Zero-configuration**: Minimal manual setup required.  

### Installation  
- Single command install (Linux/Windows).  
- Deployable as a **DaemonSet** in Kubernetes.  
- Updates automatically (managed by Dynatrace).  

---

## 🔹 ActiveGate  

### What is ActiveGate?  
- **ActiveGate** is a Dynatrace component that acts as a **gateway/proxy** between monitored environments and Dynatrace SaaS/Managed clusters.  
- It’s not required for all setups, but recommended for scalability, security, and special use cases.  

### Key Use Cases  
1. **Secure Communication**: Acts as a proxy for agents in private networks.  
2. **Cloud Monitoring**: Required for monitoring AWS, Azure, GCP services.  
3. **Synthetic Monitoring**: Runs browser-based synthetic tests.  
4. **Remote Monitoring**: Collects metrics/logs from remote networks.  
5. **Scaling**: Reduces direct load on the Dynatrace SaaS/Managed endpoint.  

### Types of ActiveGate  
- **Environment ActiveGate** → For cloud integration, remote monitoring, synthetic tests.  
- **Cluster ActiveGate** → Used in Dynatrace Managed deployments for cluster communication.  

---

## 🔹 Davis AI  

### What is Davis AI?  
- **Davis AI** is Dynatrace’s **AI engine** for root cause analysis and anomaly detection.  
- It processes huge amounts of monitoring data and identifies **problems automatically**.  

### Key Features  
- **Root Cause Detection**: Pinpoints the exact service, process, or dependency causing issues.  
- **Anomaly Detection**: Learns baselines for metrics and detects deviations.  
- **Event Correlation**: Connects metrics, traces, and logs into one problem report.  
- **Noise Reduction**: Avoids alert fatigue by grouping related issues into a single incident.  
- **Predictive Analytics**: Forecasts potential issues before they impact users.  

### Benefits  
- Reduces MTTR (Mean Time to Resolution).  
- Eliminates false positives from static thresholds.  
- Provides **explainable AI** insights instead of just alerts.  

---

## ✅ Summary  

| Component   | Purpose                                                                 | Example Use Case                                      |
|-------------|-------------------------------------------------------------------------|-------------------------------------------------------|
| **OneAgent** | Auto-discovery agent for apps, hosts, containers, and services.        | Install on Kubernetes nodes to monitor pods & services |
| **ActiveGate** | Acts as a proxy/gateway for secure data transfer and integrations.   | Monitor AWS CloudWatch via Dynatrace                  |
| **Davis AI** | AI engine for root cause detection, anomaly detection, and analytics. | Identify which microservice caused latency in EKS     |

---
