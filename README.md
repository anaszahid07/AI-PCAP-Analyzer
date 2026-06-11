# AI-PCAP Analyzer 

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![React](https://img.shields.io/badge/frontend-React_%7C_Vite-61DAFB)
![Node](https://img.shields.io/badge/backend-Node.js-339933)
![Python](https://img.shields.io/badge/AI-Python_%7C_Scikit_Learn-3776AB)

**A Next-Generation Network Forensic Analysis Tool powered by Machine Learning.**

---

## 📖 Overview

**AI-PCAP Analyzer** is a robust digital forensics dashboard designed to automate the ingestion and analysis of network traffic captures (PCAP files). By combining traditional packet parsing with a pre-trained Random Forest Machine Learning model, this tool allows security analysts to visualize network behavior and automatically detect malicious patterns such as DDoS attacks, Botnet activity, and unauthorized intrusions.

This project bridges the gap between raw data and actionable intelligence, providing a modern, web-based interface for network investigation.

## 🔍 Importance in Digital Forensics

In the evolving landscape of cybersecurity, manual packet analysis using tools like Wireshark—while powerful—is often time-consuming and prone to human error, especially with large datasets. The AI-PCAP Analyzer addresses critical needs in modern forensics:

* **Automated Anomaly Detection:** Traditional forensics relies heavily on signature-based detection. This tool leverages **Machine Learning** to identify behavioral anomalies (e.g., erratic packet timing, size variations) that static signatures might miss.
* **Rapid Triage:** Instead of manually sifting through thousands of packets, the tool provides an immediate "Malicious Confidence Score," allowing analysts to prioritize high-risk captures.
* **Visual Context:** Features like **Geographic Mapping** and **Protocol Distribution** graphs allow investigators to instantly visualize the "who, what, and where" of an attack, significantly reducing the Mean Time To Understand (MTTU).
* **Evidence Presentation:** The integrated reporting feature simplifies the creation of forensic reports, translating technical packet data into readable summaries for stakeholders.

---

## 🌟 Key Features

* **📂 Drag-and-Drop Analysis:** Seamlessly upload `.pcap` or `.pcapng` files for instant backend processing.
* **🤖 AI-Driven Threat Prediction:** Uses a Random Forest Classifier trained on network flows to predict attack types (DDoS, Probe, etc.).
* **📊 Interactive Dashboard:**
    * **Traffic Volume:** Time-series charts showing packet frequency.
    * **Protocol Breakdown:** Visual distribution of TCP, UDP, and ICMP traffic.
    * **Geo-Spatial Intelligence:** Interactive map pinpointing the physical origin of IP addresses.
* **🚨 IOC Explorer:** detailed table of Indicators of Compromise (IOCs) with severity ratings.
* **📑 Reporting:** (In Progress) Generate PDF summaries of forensic findings.

---

## 🛠️ Tech Stack

### **Frontend**
* **Framework:** React 18 (TypeScript)
* **Build Tool:** Vite
* **Styling:** Tailwind CSS + Shadcn UI
* **Visualization:** Recharts (Graphs), React-Leaflet (Maps)

### **Backend**
* **Runtime:** Node.js
* **Framework:** Express.js
* **API:** RESTful endpoints for file handling and data bridging.

### **AI & Analysis Engine**
* **Language:** Python 3.x
* **Libraries:** Pandas, Scikit-learn, NumPy, Scapy
* **Model:** Random Forest (`best_random_forest_model.pkl`)

---

## 🚀 Installation & Setup

Follow these steps to set up the environment locally.

### Prerequisites
* **Node.js** (v18+)
* **Python** (v3.10+)
* **npm** or **yarn**

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ai-pcap-analyzer.git
cd ai-pcap-analyzer
bash
```

### 2. Install Node Dependencies
```
npm install
```
### 3. Install Python Dependencies

Set up the Python environment for the AI engine. It is recommended to use a virtual environment.

### Navigate to the models directory
cd models

### (Optional) Create a virtual environment
```
python -m venv venv
```
### Windows:
```
venv\Scripts\activate
```
### Mac/Linux:
```
source venv/bin/activate
```
### Install requirements
```
pip install -r requirements.txt
```

# Note: Ensure scapy, pandas, scikit-learn, and numpy are installed.

# 🏃‍♂️ Usage

Start the Development Server:
```
npm run dev
```

Access the Dashboard: Open your browser and navigate to http://localhost:5000 (or the port specified in your terminal).

Upload a File: Click the upload area and select a PCAP file.

View Results: Wait for the analysis to complete. The dashboard will populate with the attack prediction, charts, and map data.

## 📂 Project Structure
```
ai-pcap-analyzer/
├── client/                 # React Frontend
│   ├── src/
│   │   ├── components/     # UI Components (Charts, MapView, IOCTable)
│   │   ├── pages/          # Dashboard & Landing Page
│   │   └── lib/            # Utility functions
├── server/                 # Express Backend
│   ├── routes.ts           # API Routes
│   └── pcap-analyzer.ts    # Logic to spawn Python process
├── models/                 # AI Engine
│   ├── pcap_parser.py      # Main script for parsing & inference
│   ├── best_random_forest_model.pkl  # Trained ML Model
│   └── RF_Parser.ipynb     # Jupyter Notebook for training
└── package.json            # Project Dependencies
```
# 🤝 Contributing

Contributions to improve the detection accuracy or dashboard UI are welcome!

Fork the Project

Create your Feature Branch (git checkout -b feature/NewFeature)

Commit your Changes (git commit -m 'Add NewFeature')

Push to the Branch (git push origin feature/NewFeature)

Open a Pull Request

# 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
