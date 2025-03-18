# Deploying a Static Website from GitHub to Vercel and GoDaddy

## **Overview**
This guide explains how to deploy a static website from **GitHub** to **Vercel**, and then connect it to a **GoDaddy** custom domain.

---

## **1. Push Your Project to GitHub**
If your project is not on GitHub yet, follow these steps:

### **1.1 Create a GitHub Repository**
1. Go to [GitHub](https://github.com/) and log in.
2. Click on **"New repository"**.
3. Name your repository (e.g., `my-static-site`) and select **Public** or **Private**.
4. Click **"Create repository"**.

### **1.2 Push Local Code to GitHub**
Run the following commands in your terminal:

```sh
cd /path/to/your-project

# Initialize Git
git init

# Add remote GitHub repository
git remote add origin https://github.com/YOUR_USERNAME/my-static-site.git

# Add and commit files
git add .
git commit -m "Initial commit"

# Push code to GitHub
git branch -M main
git push -u origin main
```
✅ Your project is now on **GitHub**!

---

## **2. Deploy GitHub Repository to Vercel**
### **2.1 Sign in to Vercel**
- Go to [Vercel](https://vercel.com/) and log in with **GitHub**.

### **2.2 Import and Deploy the Repository**
1. Click **"New Project"** → Select **"Import Git Repository"**.
2. Choose your repository (`my-static-site`).
3. Select the correct framework (for a static site, choose **"Other"**).
4. Click **"Deploy"**.

Once the deployment is complete, you will get a **Vercel URL** (e.g., `my-static-site.vercel.app`).

✅ Your project is now live on **Vercel**!

---

## **3. Connect Vercel to GoDaddy**

### **3.1 Add Your Custom Domain in Vercel**
1. Go to **Vercel Dashboard** → **"Settings" → "Domains"**.
2. Enter your **GoDaddy domain** (e.g., `example.com`) and click **"Add"**.

### **3.2 Update GoDaddy DNS Settings**
1. Log in to [GoDaddy](https://www.godaddy.com/).
2. Go to **"My Products" → "Manage Domains"**.
3. Click **"DNS Settings"** for your domain.
4. Add these DNS records:

   **For root domain (`example.com`)**:
   - Type: `A`
   - Name: `@`
   - Value: `76.76.21.21` (Vercel’s IP address)

   **For subdomain (`www.example.com`)**:
   - Type: `CNAME`
   - Name: `www`
   - Value: `cname.vercel-dns.com`

### **3.3 Verify in Vercel**
1. Go to **Vercel Domains Settings** and click **"Verify"**.
2. Wait for **DNS propagation** (can take a few minutes to 24 hours).

✅ Your custom **GoDaddy domain** is now linked to your **Vercel deployment**!

---

## **4. Updating Your Site**
1. Make changes to your local project.
2. Push changes to GitHub:

```sh
git add .
git commit -m "Updated content"
git push origin main
```
3. Vercel will automatically redeploy the latest version.

✅ Your website will be updated automatically!

---

## **Troubleshooting**
- If your domain is not working, wait for **DNS propagation** (can take up to 24 hours).
- Check Vercel's **"Domains"** settings to ensure it's correctly linked.
- Make sure GoDaddy’s DNS settings have the correct `A` and `CNAME` records.

---

### **🚀 Congratulations! Your website is live on GoDaddy via Vercel!**
