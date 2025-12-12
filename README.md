# #Static Website Hosting on Amazon S3

A fully deployed static website hosted on **Amazon S3**, configured with Static Website Hosting, Bucket Policies, and Public Access settings.  
This project demonstrates real-world AWS cloud deployment skills suitable for beginner and intermediate cloud engineers.

---

##  Project Overview

This project showcases how to deploy a static website using:

- **Amazon S3** (Static Web Hosting)
- **IAM User Permissions**
- **Bucket Policy for Public Access**
- **Website Endpoint for Browser Access**


---

##  Architecture Diagram
Local Machine → S3 Bucket → Public Website Endpoint
(Optional) → Global Users
---


---

##  Features

- Static website hosting using S3
- Public read access enabled using Bucket Policy
- Fast and scalable website hosting
- Fully serverless, no backend required
- Optional CloudFront CDN integration

---

##  Technologies Used

- **Amazon S3**
- **AWS IAM**
- **HTML, CSS**
  

---

#  Step-by-Step Deployment Guide

## **1️ Create an S3 Bucket**
1. Open **AWS Console**
2. Go to **S3**
3. Click **Create Bucket**
4. Bucket name example:  
   `static-website-2022`
5. Choose region (recommended: `ap-east-1`)
6. **Uncheck Block All Public Access**
7. Confirm the warning → Create bucket

<img width="1918" height="819" alt="image" src="https://github.com/user-attachments/assets/1ec3d474-0647-411d-863c-32b5d831b55a" />


---

## **2️ Enable Static Website Hosting**
1. Open the bucket
2. Go to **Properties**
3. Scroll to **Static Website Hosting**
4. Enable hosting:
   - Index Document → `index.html'
 5. Save

<img width="1906" height="818" alt="image" src="https://github.com/user-attachments/assets/9805f995-17ee-4e86-83a9-7cc7301ca316" />


---

## **3️ Upload the Website Files**
1. Open your bucket → **Upload**
2. Add:
   - `index.html`

<img width="1903" height="833" alt="image" src="https://github.com/user-attachments/assets/1f989f41-1ce2-4df6-b9bb-0b3b0329ca01" />


3. Click **Upload**

---

## **4️ Make the Bucket Public**
Go to:

**Permissions → Bucket Policy → Edit**

Paste this policy (replace bucket name):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::website-hosting-2022/*"
    }
  ]
}
```
<img width="1903" height="828" alt="image" src="https://github.com/user-attachments/assets/43f4ba13-6185-4682-a12b-925bb4b1ecff" />

---

# 5️ Access the Live Website

Go to:

Properties → Static Website Hosting → Endpoint
```
http://website-hosting-2022.s3-website-us-east-1.amazonaws.com
```
----

<img width="1904" height="1022" alt="image" src="https://github.com/user-attachments/assets/da6e4b00-e422-4f6f-9b40-307bea48f944" />

---

# 6 Conclusion 
 This project successfully demonstrates how to host a complete static website using **Amazon S3**, 
By completing this project, you now have hands-on experience with:
 - Cloud deployment  
- Static web hosting  
- AWS IAM & S3 permissions  
- Real-world DevOps workflows 
---






