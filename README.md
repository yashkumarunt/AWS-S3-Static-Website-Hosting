# 🌐 AWS S3 Static Website Hosting

This project demonstrates hosting a static portfolio website using Amazon S3.
It highlights key AWS services, permissions, and website hosting skills required for a Cloud Engineer.

---

## 📌 Project Overview
- **Service:** Amazon S3
- **Region:** us-east-1 (N. Virginia)
- **Website Type:** Static (HTML, CSS, Images)
- **Access:** Public read-only via bucket policy
- **Cost:** AWS Free Tier (5 GB free storage, sufficient for this project)

---

## 🚀 Steps Performed

### 1️⃣ Create S3 Bucket
Created bucket `yash-portfolio-hostingstaticwebsite` in `us-east-1`.

![01 – Bucket created](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/01-bucket-created.png)

---

### 2️⃣ Upload Website Files
Uploaded `final.html` and `profile_face.jpg`.

![02 – Uploaded files](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/02-uploaded-files.png)

---

### 3️⃣ Configure Public Access
Disabled “Block all public access”.
Allowed objects to be read publicly.

![03 – Block public access](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/03-block-public-access.png)

---

### 4️⃣ Enable Static Website Hosting
Enabled static hosting under bucket properties.
Index document: final.html.

![04 – Static hosting enabled](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/04-static-hosting-enabled.png)

---

### 5️⃣ Apply Bucket Policy
Applied a JSON bucket policy to grant public read-only access to all objects.

![05 – Bucket policy](https://github.com/yashkumarunt/AWS-S3-Static-Website-Hosting/blob/main/05%20Bucket%20Policy.png)

**###6️⃣ Website Endpoint**
Retrieved the website endpoint from bucket properties.

![06 – Website endpoint URL](https://raw.githubusercontent.com/yashkumarunt/AWS-S3-Static-Website-Hosting/main/06-website-url.png)

**###7️⃣ Test Website**
Opened the endpoint in browser.
Verified final.html and the image render correctly.

![07 – Website open](https://raw.githubusercontent.com/yashkumarunt/AWS-S3-Static-Website-Hosting/main/07-website-open.png)

**🧹 Clean-Up**
Deleted the bucket after demo to avoid ongoing storage charges.
AWS Free Tier covers 5 GB, so safe for small portfolio hosting.

**🛠️ Skills Demonstrated**
Amazon S3 bucket provisioning and configuration
Static website hosting setup
Public access management (Block Public Access, Bucket Policy)
Testing via AWS-provided website endpoint
Cost awareness and clean-up practices
GitHub documentation with screenshots and JSON configs

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

