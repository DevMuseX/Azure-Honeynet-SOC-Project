# 🌐 Building a SOC + Honeynet in Azure (Live Traffic)  
![Project Banner](https://github.com/ibmancodin23/Azure-Honeynet-SOC-Project/assets/19808403/85dc5588-8bde-45a0-b7f4-230116331359)

---

## 🛡️ Introduction  

This project demonstrates the construction of a **honeynet** in Azure, coupled with a **Log Analytics workspace** to monitor and analyze live traffic. Using **Microsoft Sentinel**, I developed attack maps, activated alerts, and generated incidents. The key objectives included:  

- Assessing security metrics in an insecure environment over 24 hours.  
- Implementing security controls and reevaluating metrics for an additional 24 hours.  

**Highlighted Metrics:**  
- `SecurityEvent`: Windows Event Logs  
- `Syslog`: Linux Event Logs  
- `SecurityAlert`: Log Analytics Alerts Triggered  
- `SecurityIncident`: Incidents created by Sentinel  
- `AzureNetworkAnalytics_CL`: Malicious Flows allowed into the honeynet  

---

## 🎯 Objective  

The primary goal was to deploy intentionally vulnerable virtual machines within Azure to:  
1. Attract and analyze **cyber-attacks** for insights into attack techniques.  
2. Showcase rapid incident response capabilities.  

---

## ⚙️ Components Deployed  

- **Networking**: Virtual Network (VNet), Network Security Group (NSG)  
- **Compute**: Virtual Machines (2x Windows, 1x Linux)  
- **Security & Monitoring**:  
  - Log Analytics Workspace  
  - Microsoft Sentinel (SIEM)  
  - Azure Key Vault  
  - Microsoft Defender for Cloud  
- **Management Tools**:  
  - Azure CLI  
  - PowerShell  
  - Kusto Query Language (KQL)  
- **Compliance**:  
  - [NIST SP 800-53 Rev 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)  
  - [NIST SP 800-61 Rev 2](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final)  

---

## 🖼️ Architecture  

### Before Hardening  
![Architecture Before](https://i.imgur.com/aBDwnKb.jpg)  

**Key Characteristics:**  
1. **Public Exposure**: All resources were openly accessible from the internet.  
2. **Minimal Restrictions**: NSGs and firewalls allowed unrestricted traffic.  
3. **Public Endpoints**: No private endpoints were configured.  

### After Hardening  
![Architecture After](https://i.imgur.com/YQNa9Pp.jpg)  

**Enhancements:**  
1. **Reinforced NSGs**: Strict access rules permitting only trusted IPs.  
2. **Improved Firewalls**: Fine-tuned configurations to reduce the attack surface.  
3. **Private Endpoints**: Sensitive resources were isolated from public access.  

---

## 🗺️ Attack Maps  

### Before Hardening  
- **Unsecured NSG**: Malicious traffic flooded the environment.  
  ![Malicious Allowed](https://github.com/ibmancodin23/Azure-Honeynet-SOC-Project/assets/19808403/ec8ae96d-030f-4208-8eb8-ca9623d22b8c)  

- **Linux Server Attacks**: Syslog authentication failures detected.  
  ![Syslog Auth Fail](https://github.com/ibmancodin23/Azure-Honeynet-SOC-Project/assets/19808403/706314f4-38ca-45c1-ad0c-c787538231a8)  

- **Windows Server Attacks**: RDP and SMB authentication failures identified.  
  ![Windows Auth Fail](https://github.com/ibmancodin23/Azure-Honeynet-SOC-Project/assets/19808403/d5d6d41c-a4f9-47c3-bef4-7bf72d5e0d4e)  

### After Hardening  
**No malicious activity** was detected due to robust security measures.

---

## 📊 Metrics Comparison  

| **Metric**                | **Before Hardening** | **After Hardening** |
|---------------------------|----------------------|---------------------|
| `SecurityEvent`           | 41,042              | 14,127             |
| `Syslog`                  | 5,439               | 290                |
| `SecurityAlert`           | 2                   | 0                  |
| `SecurityIncident`        | 219                 | 0                  |
| `AzureNetworkAnalytics_CL`| 412                 | 0                  |

---

## 🏁 Conclusion  

The project highlights the critical role of security controls in mitigating threats. By comparing pre- and post-hardening metrics, it is evident that:  
- Malicious activity was significantly reduced.  
- Implemented controls aligned with **NIST** standards improved overall security posture.  

This project showcases my ability to design, deploy, and secure Azure environments while effectively analyzing and mitigating cyber threats.

---

Thank you for exploring my project! Feel free to connect for further discussions.
