![WhatsApp Image 2026-03-30 at 21 52 03](https://github.com/user-attachments/assets/b860ce78-872a-426e-881d-fa69b9fbe1d4)


<h1 align="center">🚀 PegasusLog Website</h1>
<p align="center">

<div align="center">
<a href="https://trendshift.io/repositories/14638" target="_blank"><img src="https://trendshift.io/api/badge/repositories/14638" alt="HKUDS%2FAI-Researcher | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>
</div>

  <div align="center">
  <img src="https://img.shields.io/badge/PegasusLog-FF6B6B?style=for-the-badge&logo=github&logoColor=white" alt="PegasusLog Banner">
  <br>
  <img src="https://img.shields.io/badge/Version-1.0.0-blue?style=flat-square">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square">
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square">
  <img src="https://img.shields.io/badge/Made%20with-%E2%9D%A4%EF%B8%8F-red?style=flat-square">
</div>

</p>

<p align="center">
  
<img width="1919" height="898" alt="Screenshot 2026-03-30 214506" src="https://github.com/user-attachments/assets/49a50101-4a95-402e-94fa-c8d3ae31167f" />

---

## ✨ Features

### 🎯 Core Features
- **Real-Time Log Monitoring** - Live log streaming with WebSocket integration
- **Advanced Filtering** - Filter logs by severity, source, date, and custom keywords
- **Visual Analytics** - Beautiful charts and graphs for log analysis
- **Multi-Format Export** - Export logs to JSON, CSV, or PDF formats

### 🔒 Security
- **JWT Authentication** - Secure user authentication system
- **Role-Based Access** - Admin, Moderator, and Viewer roles
- **Audit Trail** - Complete logging of all user actions
- **Encrypted Storage** - AES-256 encryption for sensitive log data

### 🎨 User Experience
- **Dark/Light Mode** - Eye-friendly theme switching
- **Responsive Design** - Fully functional on desktop, tablet, and mobile
- **Keyboard Shortcuts** - Power user shortcuts for efficiency
- **Custom Dashboards** - Personalized dashboard layouts

---

## 🛠️ Technology Stack

### Frontend
```mermaid
graph TB
    subgraph "Python Processing Layer"
        A[FastAPI Server] --> B[Log Ingestion]
        B --> C[Async Processing]
        C --> D[Pattern Analysis]
        D --> E[ML Anomaly Detection]
        E --> F[Real-time Dashboard]
    end
    
    subgraph "Data Storage"
        G[(PostgreSQL)] --> H[Log Storage]
        I[(Redis)] --> J[Cache Layer]
        K[(Elasticsearch)] --> L[Search Index]
    end
    
    C --> G
    C --> I
    D --> K
