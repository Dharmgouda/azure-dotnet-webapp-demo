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

<img width="1918" height="1022" alt="image" src="https://github.com/user-attachments/assets/7e6a4bb0-593a-4561-bebf-a995d91255e0" />

---

## 🧱 Azure Resources Used

| Resource | Type | Description |
|----------|------|-------------|
| ASPplandemo | App Service Plan | Basic (B1) hosting plan |
| newwebapp477488 | App Service | Production web application |
| staging | Deployment Slot | Staging/testing environment |
| dgouda.com | App Service Domain | Purchased custom domain |
| dgouda.com | DNS Zone | DNS management for the domain |

<img width="1871" height="601" alt="image" src="https://github.com/user-attachments/assets/07235503-c574-49d8-b68d-3bf3d38e097e" />


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
   
<img width="1784" height="878" alt="image" src="https://github.com/user-attachments/assets/d99e5e7f-96f9-483e-b21b-cd727f634a91" />

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
   
<img width="1075" height="505" alt="image" src="https://github.com/user-attachments/assets/ad0a69c3-ae3d-4b50-897a-77d891e73ccb" />

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

<img width="1096" height="621" alt="image" src="https://github.com/user-attachments/assets/8867fdca-e5fe-493a-8a2a-5cb1c5febcdc" />


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
