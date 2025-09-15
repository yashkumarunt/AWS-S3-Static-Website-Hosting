# 🌐 AWS S3 Static Website Hosting

This project demonstrates hosting a **static portfolio website** using **Amazon S3**.  
It covers S3 bucket creation, static hosting setup, permissions, and public access configuration.

---

## 📌 Project Overview
- **Service:** Amazon S3
- **Region:** us-east-1 (N. Virginia)
- **Website Type:** Static (HTML, CSS, Images)
- **Access:** Public read access
- **Cost:** AWS Free Tier

---

## 🚀 Steps Performed

### 1️⃣ Create S3 Bucket
Created bucket `yash-portfolio-hostingstaticwebsite` in `us-east-1`.

[](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/01-bucket-created.png)

---

### 2️⃣ Upload Website Files
Uploaded `final.html` and `profile_face.jpg`.

![Uploaded files](screenshots/02-uploaded-files.png)

---

### 3️⃣ Configure Public Access
Unblocked public access.

![Block public access](screenshots/03-block-public-access.png)

---

### 4️⃣ Enable Static Website Hosting
Enabled hosting with index document `final.html`.

![Static hosting enabled](screenshots/04-static-hosting-enabled.png)

---

### 5️⃣ Apply Bucket Policy
Granted public read-only access.

![Bucket policy](screenshots/05-bucket-policy.png)

**bucket-policy.json:**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForStaticWebsite",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::yash-portfolio-hostingstaticwebsite/*"
    }
  ]
}
