# 🌐 .NET 9 Web Application — Azure App Service Deployment

![Banner](https://img.shields.io/badge/.NET-9.0-blueviolet?style=for-the-badge)
![Azure](https://img.shields.io/badge/Hosted%20on-Azure%20App%20Service-0089D6?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

This repository contains a simple **.NET 9 web application** deployed to **Microsoft Azure App Service**.  
It demonstrates how to create, configure, and deploy a web app using **Visual Studio**, with optional support for custom domains, SSL certificates, deployment slots, and GitHub Actions CI/CD.

---

## 🌐 Live Application

**Production URL:**  
https://newwebapp477488-aqh7hybbf6g4aebk.centralindia-01.azurewebsites.net/

**Custom Domains (if mapped):**  
https://dgouda.com  
https://www.dgouda.com

<img width="1889" height="1022" alt="image" src="https://github.com/user-attachments/assets/4c11bba1-828b-4bfb-adf8-29f16098c411" />


---

## 🧱 Azure Resources Used

| Resource | Type | Description |
|----------|------|-------------|
| ASPplandemo | App Service Plan | Basic (B1) hosting plan |
| newwebapp477488 | App Service | Production web application |
| staging | Deployment Slot | Staging/testing environment |
| dgouda.com | App Service Domain | Purchased custom domain |
| dgouda.com | DNS Zone | DNS management for the domain |

<img width="1868" height="594" alt="image" src="https://github.com/user-attachments/assets/82a3cca0-67b6-48e6-9b0e-b1157b51d8fc" />

---

## 🛠️ Technologies Used

- **.NET 9**
- **Azure App Service**
- **Azure DNS**
- **C#**
- **Visual Studio Publish**
- **Deployment Slots**

---

## 🏗️ Creating the Web App in Azure

### 1️⃣ Create an App Service
1. Open **Azure Portal → App Services → Create**
2. Configure:
   - **Runtime:** .NET 9  
   - **Operating System:** Windows  
   - **App Service Plan:** Basic (B1)
3. Click **Review + Create**
   
<img width="1858" height="896" alt="image" src="https://github.com/user-attachments/assets/be33915d-8826-41b3-8dda-bfde923b144c" />


---

## 🌐 Custom Domain & SSL Setup

### ✔️ Add Custom Domains
1. Go to **App Service → Custom Domains**
2. Add:
   - `dgouda.com`
   - `www.dgouda.com`
3. Create required **A** and **CNAME** records in Azure DNS Zone.

### ✔️ Enable HTTPS (SSL)
1. Go to **TLS/SSL Settings**
2. Upload or generate an SSL certificate
3. Bind HTTPS to both custom domains.

---

## 🔁 Deployment Slot Workflow

1. Go to **App Service → Deployment Slots**
2. Create a **staging** slot
3. Deploy updates to staging first
4. Swap staging ↔ production after testing.
   
<img width="1875" height="323" alt="image" src="https://github.com/user-attachments/assets/228c8550-bfcd-4317-83d3-e00870d9f598" />


---

## 📦 Deployment Options

### ✔️ Primary Deployment Method — Visual Studio (Used in This Project)

This application is deployed to Azure App Service using **Visual Studio Publish**.

#### **Steps to Deploy:**
1. Open the project in **Visual Studio**
2. Right-click the project → **Publish**
3. Choose **Azure App Service (Windows)**
4. Select a target:
   - **Production** slot  
   - **Staging** slot  
5. Click **Publish**

<img width="902" height="326" alt="image" src="https://github.com/user-attachments/assets/6e30a90d-aafc-4d73-a97a-52547d8c5481" />



Visual Studio builds and deploys the application directly to Azure.  
This method is ideal for **learning**, **quick deployments**, and **testing**.

---

### ✔️ Optional: CI/CD via GitHub Actions

Although Visual Studio was used for deployment, you can optionally enable **GitHub Actions CI/CD** to automate future deployments.

Benefits include:
- Automatic deployment on every commit  
- Consistent and repeatable deployments  
- Ideal for team development  

A sample GitHub Actions workflow can be added if needed.

---

## 🖥️ Running the Project Locally

```bash
dotnet restore
dotnet build
dotnet run
