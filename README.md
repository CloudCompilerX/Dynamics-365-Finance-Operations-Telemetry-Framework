# 🚀 Dynamics 365 Finance & Operations Telemetry Framework

### Azure Application Insights · Dynamics 365 F&O · X++ · Azure Data Explorer · Telemetry Analytics

---

## 📌 Overview

This repository provides a **telemetry framework and sample implementations for Dynamics 365 Finance & Operations (D365 F&O)**, enabling organizations to capture, monitor, and analyze application performance and business process telemetry using **Azure Application Insights**.

The framework includes reusable base classes, telemetry extensions, and dashboards to support **performance monitoring, diagnostics, analytics, and operational intelligence**.

---

## 🎯 Key Objectives

* Enable telemetry logging in Dynamics 365 Finance & Operations
* Monitor business processes and batch jobs
* Track Data Management Framework (DMF) operations
* Capture custom application events, metrics, and traces
* Support performance monitoring and diagnostics
* Provide integration with Azure Application Insights and Azure Data Explorer

---

## ✨ Features

* 📊 Batch job monitoring and analytics
* 🔄 Data Management Framework (DMF) import/export tracking
* 📈 Business event telemetry tracking
* ⚡ Performance and execution time monitoring
* 🧩 Custom telemetry framework using reusable base classes
* 📡 Azure Application Insights integration
* 📉 Azure Data Explorer dashboards for visualization
* 🔍 Custom event, trace, and metric logging

---

## 🏗️ Architecture Overview

| Component                  | Description                              |
| -------------------------- | ---------------------------------------- |
| Dynamics 365 F&O           | Source system generating telemetry       |
| Telemetry Framework        | Custom X++ classes for telemetry logging |
| Azure Application Insights | Telemetry storage and monitoring         |
| Azure Data Explorer        | Data visualization and analytics         |
| Custom Extensions          | Capture telemetry for business processes |

---

## 📂 Project Structure

```
FinOps-Telemetry/
├── src/
│   └── xpp/
│       └── Metadata/
│           └── ISMModel/        # Telemetry framework model
├── Dashboards/                  # Azure Data Explorer dashboards
├── documentation/               # Supporting documentation
├── notebooks/                   # Analytics and telemetry exploration
├── README.md                   # Project documentation
```

---

## ⚙️ Prerequisites

Before installing, ensure the following requirements are met:

* Dynamics 365 Finance & Operations environment
* Visual Studio 2019 or later
* Azure Application Insights resource
* Azure subscription
* Access to LCS or Unified Development Environment (UDE)

---

## 🚀 Installation

### Step 1: Clone Repository

```bash
git clone https://github.com/yourusername/finops-telemetry-framework.git
```

---

### Step 2: Install Model

Copy the telemetry model into your Dynamics 365 environment:

```
PackagesLocalDirectory/
```

Refresh models in Visual Studio and build the project.

---

### Step 3: Enable Monitoring Feature

Enable the following feature in Dynamics 365:

```
Feature Management → Monitoring and Telemetry
```

---

## ⚙️ Configure Azure Application Insights

1. Open:

```
Monitoring and Telemetry Parameters
```

2. Add:

* Application Insights Connection String OR Instrumentation Key
* Environment ID

3. Select telemetry events to track

---

## 📊 Telemetry Types Supported

The framework supports three telemetry types:

| Telemetry Type | Application Insights Table | Description                |
| -------------- | -------------------------- | -------------------------- |
| Events         | customEvents               | Business process telemetry |
| Traces         | traces                     | Diagnostic tracing         |
| Metrics        | customMetrics              | Performance metrics        |

---

## 🧠 Example: Custom Telemetry Implementation

### Create Telemetry Class

```x++
class ISMTelemetryGeneric extends ISMTelemetryBase
{
    public void new()
    {
        super();
        this.eventId = ISMTelemetryEventIds::ISMEvent;
    }

    protected boolean shouldLogEvent()
    {
        return true;
    }
}
```

---

### Track Business Process Execution

```x++
ISMTelemetryGeneric telemetry = new ISMTelemetryGeneric();

next runPrintMgmt();

telemetry.processEvent("CustomerStatement");
```

---

## 📈 Captured Telemetry Data Includes

* Execution time
* Event name
* Custom properties
* Environment details
* Process performance metrics

---

## 📊 Analytics and Monitoring

Telemetry data can be analyzed using:

* Azure Application Insights
* Azure Data Explorer
* Log Analytics Workspace
* Power BI dashboards

This enables:

* Performance monitoring
* Root cause analysis
* System diagnostics
* Business intelligence reporting

---

## 💼 Enterprise Use Cases

This project supports:

* ERP system monitoring
* Business process performance tracking
* Production diagnostics
* Data engineering observability pipelines
* Cloud telemetry analytics
* DevOps monitoring and logging

---

## 🛠️ Technology Stack

* Dynamics 365 Finance & Operations
* X++
* Azure Application Insights
* Azure Data Explorer
* Azure Monitor
* Visual Studio
* Log Analytics

---

## 📉 Benefits

* Improves system observability
* Enables proactive issue detection
* Supports enterprise monitoring strategies
* Enhances performance optimization
* Enables data-driven operational insights

---

## 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Submit pull request

---

## ⚠️ Disclaimer

This project is provided for educational and development purposes. Use in production environments after proper testing and validation.

---

## 📄 License

This project is licensed under the terms specified in the LICENSE file.
